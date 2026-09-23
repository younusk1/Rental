# Rental Platform Pakistan

Rent Asan is a verification-first rental marketplace for Pakistan where owners and renters can connect directly, without brokerage commission.

## Product goal

Help a legitimate owner and a legitimate renter move from discovery to a trustworthy rental relationship. The platform replaces the broker's practical trust functions—identity, ownership, discovery, communication, and documentation—without recreating a mandatory broker-style fee.

## MVP scope

- Verified owner and renter accounts
- Property listings linked to an ownership claim
- Property and listing verification workflow
- Search, viewing requests, direct in-app messaging, and rental interest
- Manual moderation, reporting, and audit history

Payments, escrow, advanced tenancy management, and nationwide automated land-record integrations are deliberately out of scope for the MVP.

## Repository layout

```text
apps/                 User-facing applications and API entry points
  web/                Web client
  api/                API application
packages/             Shared domain and platform packages
  domain/             Domain entities, policies, and use cases
  verification/       Provider-neutral identity and ownership verification
  messaging/          Conversation and message capabilities
  moderation/         Risk, reports, review, and enforcement workflows
  shared/             Cross-cutting types and utilities
infrastructure/       Deployment, environment, and operational definitions
docs/                 Product, architecture, security, and operating documentation
  decisions/          Architecture decision records
  product/            Product requirements and MVP artifacts
  security/           Threat model and privacy/data-flow documentation
tests/                Cross-application and end-to-end tests
```

## Documentation

- [Architecture](docs/Architecture.md)
- [Product context](docs/context-v2.md)
- [MVP scope](docs/product/MVP-Scope.md)
- [Go-to-market strategy](docs/product/Go-To-Market.md)
- [Product strategy and timeline](docs/product/Strategy-and-Timeline.md)
- [Architecture decisions](docs/decisions/README.md)

## Guiding principles

1. Verification before high-value visibility.
2. Explainable trust signals instead of opaque scores.
3. Privacy by default; do not expose raw identity or ownership documents.
4. Direct-to-owner by default, while supporting explicitly authorized representatives.
5. Provider independence for identity and property verification.
6. Automation with human escalation and auditable decisions.

## Status

This repository is in the foundation stage. The next deliverables are the PRD, verification state model, threat model, data model, and API boundary definitions before application implementation begins.
