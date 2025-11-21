# BOCA Claude KMP

**Production-ready Claude Code plugin for Kotlin Multiplatform ERP development**

A specialized Claude Code plugin designed for professional KMP (Kotlin Multiplatform) ERP development, featuring 25 specialized commands and 9 AI agents optimized for mobile (Android/iOS) and backend development workflows.

## Features

- **25 Production Commands** organized by workflow
- **9 Specialized AI Agents** for architecture, security, and optimization
- **Mobile-First** support for Android & iOS with Compose Multiplatform and SwiftUI
- **Backend Integration** with Supabase, FastAPI, Express, Django REST, and Spring Boot
- **Security-Focused** with OWASP scanning and compliance checking
- **Test-Driven Development** workflows with comprehensive TDD commands

## Installation

```bash
# Install from Claude Code marketplace
claude plugin install boca-claude-kmp
```

Or manually clone this repository:

```bash
git clone https://github.com/Ianboc17/boca-claude-kmp.git
cd boca-claude-kmp
claude plugin install .
```

## Commands

### API Development (2 commands)

#### `/api-scaffold`
Create REST API endpoints with validation and error handling.

**Example:**
```bash
/api-scaffold
# Creates: Controllers, routes, validation schemas, error handlers
# Supports: FastAPI, Express, Django REST, Spring Boot
```

#### `/api-mock`
Generate mock APIs for testing and development.

**Example:**
```bash
/api-mock
# Creates: Mock data generators, fake endpoints, test fixtures
```

### Database & Migrations (1 command)

#### `/db-migrate`
Create and manage database migrations with zero-downtime strategies.

**Example:**
```bash
/db-migrate
# Creates: Migration files, rollback scripts, data transformation logic
# Supports: PostgreSQL, MySQL, SQLite, MongoDB
```

### Data Processing (1 command)

#### `/data-pipeline`
Design ETL/ELT pipelines for data import and processing.

**Example:**
```bash
/data-pipeline
# Creates: Data extractors, transformers, loaders, scheduling logic
```

### Testing (4 commands)

#### `/test-harness`
Generate comprehensive test suites (unit, integration, e2e).

**Example:**
```bash
/test-harness
# Creates: Unit tests, integration tests, e2e tests, fixtures
# Supports: JUnit, Kotest, Espresso, XCTest
```

#### `/tdd-red`
Create failing tests for test-driven development.

**Example:**
```bash
/tdd-red
# RED phase: Write failing tests first
```

#### `/tdd-green`
Implement minimal code to pass tests.

**Example:**
```bash
/tdd-green
# GREEN phase: Make tests pass with minimal code
```

#### `/tdd-refactor`
Refactor code while maintaining passing tests.

**Example:**
```bash
/tdd-refactor
# REFACTOR phase: Improve code quality without breaking tests
```

### Dependencies & Configuration (3 commands)

#### `/deps-audit`
Audit dependencies for security vulnerabilities.

**Example:**
```bash
/deps-audit
# Scans: CVE databases, outdated packages, license compliance
```

#### `/deps-upgrade`
Upgrade and update dependency versions.

**Example:**
```bash
/deps-upgrade
# Updates: Dependencies with compatibility checks
```

#### `/config-validate`
Validate configuration and environment variables.

**Example:**
```bash
/config-validate
# Validates: Required env vars, config schema, secrets management
```

### Debugging & Error Analysis (1 command)

#### `/error-trace`
Debug production errors with detailed analysis.

**Example:**
```bash
/error-trace
# Analyzes: Stack traces, error logs, root cause identification
```

### Code Migration (1 command)

#### `/code-migrate`
Migrate code between versions and platforms.

**Example:**
```bash
/code-migrate
# Migrates: API versions, library updates, platform changes
```

### Documentation (1 command)

#### `/doc-generate`
Generate API and code documentation.

**Example:**
```bash
/doc-generate
# Generates: KDoc, OpenAPI/Swagger specs, README files
```

### Technical Debt (1 command)

#### `/tech-debt`
Analyze technical debt and prioritize refactoring.

**Example:**
```bash
/tech-debt
# Analyzes: Code complexity, duplication, outdated patterns
```

### Accessibility (1 command)

#### `/accessibility-audit`
Audit accessibility compliance (WCAG, mobile accessibility).

**Example:**
```bash
/accessibility-audit
# Checks: WCAG 2.1 AA/AAA, mobile accessibility, screen readers
```

### Security (2 commands)

#### `/security-scan`
Perform OWASP vulnerability assessment.

**Example:**
```bash
/security-scan
# Scans: OWASP Top 10, injection flaws, authentication issues
```

#### `/compliance-check`
Check regulatory compliance (GDPR, HIPAA, etc.).

**Example:**
```bash
/compliance-check
# Validates: GDPR, HIPAA, SOC 2, PCI-DSS compliance
```

### Code Quality (2 commands)

#### `/code-explain`
Generate detailed code explanations.

**Example:**
```bash
/code-explain
# Explains: Code logic, design patterns, architecture decisions
```

#### `/refactor-clean`
Clean up and refactor code for better quality.

**Example:**
```bash
/refactor-clean
# Refactors: Code smells, design patterns, best practices
```

### Supabase Integration (2 commands)

#### `/edge-function-new`
Create new Supabase Edge Functions (Deno backend).

**Example:**
```bash
/edge-function-new
# Creates: Deno Edge Functions, CORS handling, auth integration
```

#### `/types-gen`
Generate TypeScript types from Supabase schema.

**Example:**
```bash
/types-gen
# Generates: TypeScript interfaces from PostgreSQL schema
```

### Workflows (4 commands)

#### `/feature-development`
End-to-end feature implementation workflow.

**Example:**
```bash
/feature-development
# Workflow: Requirements → Design → Implementation → Testing → Deployment
```

#### `/security-hardening`
Security-first development workflow.

**Example:**
```bash
/security-hardening
# Workflow: Threat modeling → Secure coding → Vulnerability scanning → Compliance
```

#### `/performance-optimization`
System-wide performance optimization.

**Example:**
```bash
/performance-optimization
# Workflow: Profiling → Bottleneck analysis → Optimization → Benchmarking
```

#### `/full-review`
Multi-perspective code review.

**Example:**
```bash
/full-review
# Reviews: Architecture, security, performance, maintainability
```

## AI Agents

### Architecture Agents (3 agents)

#### `@system-architect`
Design scalable KMP system architecture with focus on maintainability.

**Use when:**
- Planning new system architecture
- Designing microservices or modular systems
- Making long-term technical decisions

#### `@backend-architect`
Design reliable backend systems with data integrity and security focus.

**Use when:**
- Designing API architectures
- Planning database schemas
- Implementing authentication/authorization

#### `@frontend-architect`
Create accessible mobile UIs with Compose Multiplatform and SwiftUI.

**Use when:**
- Designing mobile UI architectures
- Implementing navigation patterns
- Creating reusable component libraries

### Quality & Security Agents (2 agents)

#### `@security-engineer`
Identify vulnerabilities and ensure security standards compliance.

**Use when:**
- Performing security audits
- Implementing authentication/encryption
- Reviewing code for vulnerabilities

#### `@performance-engineer`
Optimize performance through measurement-driven analysis.

**Use when:**
- Profiling application performance
- Optimizing database queries
- Reducing memory consumption

### Code Quality Agents (1 agent)

#### `@refactoring-expert`
Improve code quality and reduce technical debt systematically.

**Use when:**
- Refactoring legacy code
- Applying design patterns
- Reducing code complexity

### Planning & Documentation Agents (3 agents)

#### `@requirements-analyst`
Transform ambiguous ideas into concrete specifications.

**Use when:**
- Defining project requirements
- Creating technical specifications
- Planning feature implementations

#### `@deep-research-agent`
Comprehensive research with adaptive strategies and intelligent exploration.

**Use when:**
- Researching new technologies
- Analyzing complex codebases
- Investigating best practices

#### `@technical-writer`
Create clear technical documentation tailored to specific audiences.

**Use when:**
- Writing API documentation
- Creating user guides
- Documenting architecture decisions

## Technology Stack Support

- **Mobile:** Kotlin Multiplatform, Compose Multiplatform, SwiftUI, Android, iOS
- **Backend:** Supabase (Deno), FastAPI, Express, Django REST, Spring Boot
- **Databases:** PostgreSQL, MySQL, SQLite, MongoDB
- **Testing:** JUnit, Kotest, Espresso, XCTest
- **Security:** OWASP, GDPR, HIPAA, SOC 2, PCI-DSS

## Use Cases

### ERP Development
Build enterprise resource planning systems with KMP for maximum code sharing between mobile platforms.

### Mobile-First Applications
Create native-quality mobile apps with shared business logic and platform-specific UIs.

### Backend API Development
Design and implement scalable RESTful APIs with security and performance best practices.

### Security-Compliant Systems
Build applications that meet regulatory requirements (GDPR, HIPAA, etc.).

## Example Workflows

### Complete Feature Development
```bash
# 1. Gather requirements
@requirements-analyst

# 2. Design architecture
@system-architect

# 3. Implement API endpoints
/api-scaffold

# 4. Create tests
/test-harness

# 5. Security audit
/security-scan

# 6. Performance optimization
@performance-engineer

# 7. Documentation
/doc-generate

# 8. Final review
/full-review
```

### TDD Workflow
```bash
# RED: Write failing test
/tdd-red

# GREEN: Make it pass
/tdd-green

# REFACTOR: Improve code
/tdd-refactor
```

### Security Hardening
```bash
# 1. Security workflow
/security-hardening

# 2. OWASP scan
/security-scan

# 3. Compliance check
/compliance-check

# 4. Dependency audit
/deps-audit
```

## Requirements

- **Claude Code CLI** version 0.1.0 or higher
- **Kotlin** 1.9+ (for KMP projects)
- **JDK** 17+ (for Kotlin/Android development)
- **Xcode** 15+ (for iOS development)

## Contributing

Contributions are welcome! Please feel free to submit issues or pull requests.

## License

MIT License - see [LICENSE](LICENSE) file for details

## Author

**Ianboc17**
- GitHub: [@Ianboc17](https://github.com/Ianboc17)

## Support

- Report issues: [GitHub Issues](https://github.com/Ianboc17/boca-claude-kmp/issues)
- Discussions: [GitHub Discussions](https://github.com/Ianboc17/boca-claude-kmp/discussions)

## Version History

See [CHANGELOG.md](CHANGELOG.md) for detailed version history.

---

**Made with Claude Code** - Empowering developers to build better KMP applications faster.
