---
description: Generate TypeScript types from Supabase database schema (for KMP backend APIs)
model: claude-sonnet-4-5
---

# Generate Supabase Database Types

Generate TypeScript types from your Supabase database schema. Use these for:
- Backend API development
- Supabase Edge Functions
- Type-safe database operations
- Contract definition between KMP frontend and backend

## Command

Run the following command to generate types:

```bash
npx supabase gen types typescript --project-id YOUR_PROJECT_ID > lib/database.types.ts
```

Or if using local Supabase:

```bash
npx supabase gen types typescript --local > lib/database.types.ts
```

## Setup for Auto-Generation

### 1. **Add to package.json**

```json
{
  "scripts": {
    "gen-types": "npx supabase gen types typescript --project-id $SUPABASE_PROJECT_ID > lib/database.types.ts",
    "gen-types:local": "npx supabase gen types typescript --local > lib/database.types.ts"
  }
}
```

### 2. **Usage in Backend Code**

```typescript
import type { Database } from '@/lib/database.types'

// Get table type
type Order = Database['public']['Tables']['orders']['Row']
type OrderInsert = Database['public']['Tables']['orders']['Insert']
type OrderUpdate = Database['public']['Tables']['orders']['Update']

// Use with Supabase client
const supabase = createClient<Database>(url, key)

// Type-safe queries
const { data } = await supabase
  .from('orders')
  .select('*')
  .single()  // data is typed as Order

// Type-safe inserts
const { data } = await supabase
  .from('orders')
  .insert({
    order_number: 'ORD-001',
    total_amount: 1000,
    status: 'pending'
  })  // TypeScript validates the shape
```

### 3. **Create Utility Types**

```typescript
// lib/database.helpers.ts
import type { Database } from './database.types'

// Extract table types
export type Tables<T extends keyof Database['public']['Tables']> =
  Database['public']['Tables'][T]['Row']

export type TableInsert<T extends keyof Database['public']['Tables']> =
  Database['public']['Tables'][T]['Insert']

export type TableUpdate<T extends keyof Database['public']['Tables']> =
  Database['public']['Tables'][T]['Update']

export type Enums<T extends keyof Database['public']['Enums']> =
  Database['public']['Enums'][T]

// Usage in Edge Functions
import type { Tables } from '@/lib/database.helpers'
type Order = Tables<'orders'>
type Customer = Tables<'customers'>
type Invoice = Tables<'invoices'>
```

### 4. **ERP-Specific Types Example**

```typescript
// types/erp.ts
import type { Database } from '@/lib/database.types'

// Domain models for ERP
export namespace ERP {
  export type Customer = Database['public']['Tables']['customers']['Row']
  export type Product = Database['public']['Tables']['products']['Row']
  export type Order = Database['public']['Tables']['orders']['Row']
  export type Invoice = Database['public']['Tables']['invoices']['Row']
  export type Inventory = Database['public']['Tables']['inventory']['Row']
  
  export type OrderStatus = Database['public']['Enums']['order_status']
  export type PaymentStatus = Database['public']['Enums']['payment_status']
}

// Use in functions
async function createOrder(order: ERP.Order) {
  const supabase = createClient<Database>(url, key)
  return supabase.from('orders').insert(order)
}
```

### 5. **When to Regenerate**

Run `npm run gen-types` after:
- Creating new tables (customers, products, invoices, etc.)
- Adding/removing columns
- Changing column types
- Modifying RLS policies
- Adding/updating enums (order_status, payment_status, etc.)

### 6. **Integration with Edge Functions**

```typescript
// supabase/functions/create-order/index.ts
import type { Database } from '../_shared/database.types'

serve(async (req: Request) => {
  const supabase = createClient<Database>(url, key)
  const { customer_id, items } = await req.json()
  
  // Fully typed query
  const { data: order, error } = await supabase
    .from('orders')
    .insert({
      customer_id,
      status: 'pending',
      total_amount: calculateTotal(items)
    })
    .select()
    .single()
  
  // TypeScript ensures order matches Order type
  return new Response(JSON.stringify({ order }), { status: 200 })
})
```

### 7. **Best Practices**

- Commit generated types to git
- Run after schema changes
- Use in all Supabase queries
- Create helper types for common patterns
- Keep types file in `lib/` or `types/`
- Don't manually edit generated file
- Don't use `any` instead of generated types

### 8. **Integration with Pre-commit Hook**

```bash
# .husky/pre-commit
#!/bin/sh
npm run gen-types
git add lib/database.types.ts
```

### 9. **Sharing Types with KMP Frontend**

Export types from your backend API for use in KMP:

```typescript
// Export for KMP
export type ApiOrder = Tables<'orders'>
export type ApiCustomer = Tables<'customers'>

// In KMP, define data classes that match these types
data class Order(
  val id: String,
  val customer_id: String,
  val status: String,
  val total_amount: Double
)
```

## Troubleshooting

**Issue**: `supabase` command not found
```bash
npm install -g supabase
```

**Issue**: Missing project ID
```bash
# Find your project ID in Supabase dashboard
# Or set in .env
SUPABASE_PROJECT_ID=your-project-id
```

**Issue**: Types not updating
```bash
# Clear cache and regenerate
rm lib/database.types.ts
npm run gen-types
```

**Issue**: Enums not generating
- Ensure enums are created in Supabase
- Run `supabase db pull` first
- Check that RLS is properly configured

Generate and use TypeScript types to catch database-related bugs at compile time instead of runtime. Keep your backend and KMP frontend in sync with type-safe contracts.
