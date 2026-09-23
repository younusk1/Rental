# Rental Platform Pakistan (Rent Asan) - Project Context

## Project Overview

Rent Asan is a verification-first, direct-to-owner rental marketplace for Pakistan. The platform aims to connect property owners and renters directly, eliminating the need for brokers by providing trustworthy, verifiable, and easy-to-use transaction workflows.

### Core Product Thesis

Eliminate the economic need for a broker by making direct owner-to-renter transactions trustworthy, verifiable, and easy.

### Status

The project is in the **foundation stage**. The repository currently contains architectural, product, and security documentation. Application implementation has not yet begun.

## Guiding Principles

1. **Verification before high-value visibility.**
2. **Explainable trust signals** instead of opaque scores.
3. **Privacy by default;** do not expose raw identity or ownership documents.
4. **Direct-to-owner by default,** while supporting explicitly authorized representatives.
5. **Provider independence** for identity and property verification.
6. **Automation with human escalation** and auditable decisions.

## Repository Layout

- `apps/`: Future user-facing applications (web, API).
- `packages/`: Shared domain logic, verification services, messaging, and moderation.
- `infrastructure/`: Deployment and operational definitions.
- `docs/`: Product, architecture, security, and decision records (ADRs).
- `tests/`: Future cross-application and E2E tests.

## Development & Implementation

As of September 2026, the project has no implementation code.

### Immediate Next Steps (TODOs)

Before implementation, the following artifacts must be defined:

- Product Requirements Document (PRD)
- Verification state model
- Threat model
- Data model
- API boundary definitions

## Key Architectural Drivers

- Protect sensitive identity and ownership evidence.
- Make verification decisions explainable and auditable.
- Keep identity and property-verification providers replaceable.
- Ensure every listing is linked to an ownership claim.
- Decouple payments and rental agreements from the listing core until regulatory requirements are solidified.

## Documentation References

- [Architecture](docs/Architecture.md)
- [Product Context](docs/context-v2.md)
- [MVP Scope](docs/product/MVP-Scope.md)
- [Architecture Decision Records](docs/decisions/README.md)
