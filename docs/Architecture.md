# Architecture

## Purpose

This document defines the initial architectural direction for the Rental Platform Pakistan MVP. It is a boundary map, not a final technology choice. Detailed implementation should follow the product and verification artifacts listed in [MVP scope](product/MVP-Scope.md).

## Architectural drivers

- Protect sensitive identity and ownership evidence.
- Make verification decisions explainable and auditable.
- Keep identity and property-verification providers replaceable.
- Support manual review whenever automation is unavailable or inconclusive.
- Prevent a listing from being independent of an ownership relationship.
- Keep payments and agreements decoupled from the listing core until their regulatory requirements are understood.

## Context

```text
Owner / Authorized Representative ─┐
                                  ├─ Web / Mobile client ─ API boundary
Renter ───────────────────────────┘                         │
                                                             ▼
             ┌────────────────────────────────────────────────────────┐
             │ Trust marketplace                                      │
             │ Identity & verification | Property & listings          │
             │ Messaging | Viewings & applications | Moderation       │
             └───────┬─────────────────┬───────────────────┬──────────┘
                     │                 │                   │
                     ▼                 ▼                   ▼
          Verification providers   Secure document store  Notifications
          (approved, manual,       and evidence metadata  and audit log
           future integrations)
```

## Initial service boundaries

Begin as a modular application with clear domain boundaries. Splitting into independently deployed services is a later operational decision, not an MVP prerequisite.

| Boundary | Responsibility | Must not own |
| --- | --- | --- |
| Identity & Verification | User verification states, evidence intake, provider adapters, review decisions | Public display of raw identity evidence |
| Property & Listings | Properties, ownership claims, listing lifecycle, availability | Verification-provider implementation |
| Messaging | Consent-gated conversations and messages | Unnecessary identity-document access |
| Viewings & Applications | Viewing requests, scheduling, renter interest | Ownership decision-making |
| Moderation & Risk | Reports, signals, review cases, enforcement, appeals | Silent irreversible automated decisions |
| Audit & Notifications | Immutable event history and user notifications | Core business policy |

## Trust chain and invariants

```text
User → Identity verification → Owner profile → Ownership claim
     → Property → Listing → Viewing / application → Tenancy
```

- A listing requires a linked ownership claim that is verification-pending or verified.
- Only verification outcomes—not raw CNICs or documents—may be exposed as public trust signals.
- An authorized representative is explicit and linked to the verified owner/authorization evidence.
- Every moderation or verification action records actor, evidence references, rule/reason, time, and appeal status.
- The platform treats listing volume and risk signals as review triggers, not proof of brokerage.

## Data classification

| Class | Examples | Handling |
| --- | --- | --- |
| Highly sensitive | Identity documents, CNIC data, ownership evidence | Encrypted restricted storage; never public; minimal access and retention |
| Sensitive | Addresses before viewing confirmation, messages, applications | Role- and consent-controlled access |
| Internal | Risk signals, moderation cases, audit events | Restricted operational access and full audit trail |
| Public | Published listing details and explainable verification badges | Deliberate, minimal publication only |

## Verification abstraction

The verification package provides a stable application-facing contract. Provider adapters may use an approved identity provider, document checks, land-record checks where available, or manual review. No individual provider, including a possible national-identity integration, is a hard architectural dependency.

```text
Application → Verification contract → Provider adapter / manual review
                                      → outcome + evidence reference
```

## Key lifecycle states

### Listing

`Draft → Verification Pending → Verified → Published → Reserved → Rented → Archived`

Listings must periodically reconfirm availability and should expire when stale.

### Verification

`Not started → Submitted → In review → Verified | Rejected | More information required`

## Deferred domains

Rental agreements, payments, escrow, deposits, maintenance, and disputes remain separate future domains. They must not be coupled into the MVP listing and verification model until legal, regulatory, and operational requirements are defined.

## Decisions to make before implementation

1. Launch geography and the property categories supported.
2. Ownership-evidence policy and manual-review operating model.
3. Data retention, access controls, and incident response requirements.
4. Identity-verification provider and fallback process.
5. API contract, data model, and event/audit strategy.
