# Product Strategy and Timeline

## Strategic thesis

Build the smallest trustworthy rental loop in one dense launch market:

```text
Verified owner → verified property relationship → verified renter
→ direct communication → viewing → successful rental
```

The platform's differentiator is not access to identity data. It is a safe, explainable, provider-independent trust workflow that makes a direct owner-to-renter rental practical without a broker.

## Critical identity-verification constraint

NADRA describes Verisys as an OTP-consent-based CNIC/NICOP/POC verification service, and its newer Nishan Pakistan portal as the onboarding gateway for government entities and regulated private organisations. NADRA specifically names banks, microfinance banks, EMIs, NBFIs, telecom companies, and other regulated organisations as digitally onboarded entity types. This means a rental-platform startup must treat eligibility, contracting, security review, and approval as an external dependency—not assume it can obtain a self-service developer API key. [NADRA verification services](https://www.nadra.gov.pk/verification) and [Nishan Pakistan announcement](https://www.nadra.gov.pk/media-release/nadra-unveils-nishan-pakistan-to-strengthen-secure-identity-verification-and-power-pakistans-digital-economy-4e319da8)

**Strategy implication:** apply and investigate the appropriate NADRA/Nishan Pakistan pathway early, but do not make approval a launch blocker. The MVP must operate through a privacy-preserving, manual or approved-provider verification path while that work proceeds.

## Strategic choices

| Choice | Direction | Why |
| --- | --- | --- |
| Launch market | One city and a limited set of residential property types | Marketplace liquidity and verification operations need density |
| Trust model | Explainable verification statuses, not a public numeric score | Makes trust understandable and avoids misleading certainty |
| Identity integration | Provider-neutral contract with manual-review fallback | NADRA eligibility and onboarding timing are uncertain |
| Ownership verification | Evidence review, consistency checks, and manual escalation | A verified identity alone does not prove ownership |
| Acquisition | Social media plus a small owned landing site | Social builds local awareness; the website converts and retains interest |
| Monetisation | Brokerage-free core connection; transparent optional services later | Preserves the product promise |

## Timeline

Timing starts when a product owner and a pilot team are available. Dates should be set after the launch city, team capacity, and regulatory advice are confirmed.

### Phase 0 — Validate and prepare (weeks 0–4)

**Goal:** establish a narrow, legally and operationally credible pilot.

- Select pilot city, target neighborhoods, and supported residential property categories.
- Interview owners, renters, and prospective authorized representatives; validate brokerage costs and pain points locally.
- Define acceptable ownership evidence, review criteria, rejection reasons, appeals, and document-retention requirements with qualified local legal/privacy advice.
- Start the NADRA/Nishan Pakistan eligibility and onboarding inquiry; document its required entity status, security requirements, commercial terms, and lead time.
- Publish the lightweight landing site and open owner/renter waitlists.
- Define the verification contract and manual-review workflow.

**Exit criteria:** a pilot policy exists, review responsibility is assigned, and the team can verify an owner/property relationship without an unapproved API.

### Phase 1 — Build the trust-loop MVP (weeks 5–12)

**Goal:** enable a controlled pilot with real users.

- Build accounts, role selection, consent, profile basics, property submission, secure evidence upload, and listing lifecycle.
- Build status-based identity and ownership verification, reviewer queues, audit history, reports, and restricted access controls.
- Build search, viewing requests, consent-gated messaging, and rental-interest submission.
- Run manual verification with documented service levels and quality checks.
- Begin city-specific educational social content and recruit a small cohort of owners before expanding renter acquisition.

**Exit criteria:** a controlled group can submit properties, complete review, publish verified listings, and arrange a viewing without exposing raw sensitive evidence.

### Phase 2 — Pilot and learn (weeks 13–20)

**Goal:** prove safety, conversion, and operational feasibility in one location.

- Onboard verified owners and renters in the pilot area.
- Monitor verification completion, review time, duplicate listings, broker-related reports, viewing completion, and successful rentals.
- Test the clarity of trust signals and the handoff from social inquiry to platform onboarding.
- Refine evidence requirements, fraud rules, customer communications, and reviewer guidance based on observed cases.
- Continue the NADRA pathway; assess any approved-provider option only after legal, privacy, and commercial review.

**Exit criteria:** evidence that users complete direct viewings/rentals, moderation is manageable, and the manual fallback is viable at the pilot scale.

### Phase 3 — Strengthen and prepare expansion (weeks 21–32)

**Goal:** turn pilot learning into a repeatable operating model.

- Improve automation around document intake, duplicate detection, listing freshness, and risk triage; retain human final review for ambiguous cases.
- Add structured rental applications and an agreement-generation workflow only after legal review of jurisdiction-specific templates.
- Decide whether an approved identity-verification integration is available, appropriate, and ready to activate behind the existing contract.
- Build launch playbooks for a second geographic cluster; expand only if the first location meets the success thresholds below.

**Exit criteria:** repeatable operational controls, defined expansion economics, and no unresolved critical privacy, regulatory, or safety risks.

## NADRA decision gates

| Gate | Decision | If not satisfied |
| --- | --- | --- |
| Eligibility | Is the company an eligible, approved entity or does it have a legitimate approved-provider route? | Continue manual/alternative verification; do not represent NADRA verification to users |
| Compliance | Are purpose limitation, consent, security, data minimisation, retention, and contractual controls approved? | Do not integrate or transmit identity data |
| Technical readiness | Does the provider integration meet the platform's verification contract, security model, monitoring, and audit requirements? | Keep the adapter inactive and use the fallback path |
| Operational readiness | Can support and reviewers explain outcomes, handle exceptions, and manage incidents? | Run a limited pilot only; do not scale the integration |

## Pilot success thresholds

Set numerical thresholds after the Phase 0 research, but assess at least:

- Sufficient density of active verified listings in the pilot area.
- Owner and renter verification completion rates that do not make the product unusable.
- A sustainable manual-review turnaround time.
- Meaningful viewing completion and direct-rental conversion.
- Low rates of substantiated fraud, broker misrepresentation, and stale listings.
- No critical privacy, security, or regulatory incident.

## Risks and responses

| Risk | Response |
| --- | --- |
| NADRA access is unavailable or delayed | Preserve provider independence; use documented manual review and explore lawful approved-provider routes |
| Verification creates too much friction | Stage requirements by action value; provide status visibility and human support |
| Weak supply in the launch area | Recruit verified owners first and keep the geography narrow |
| Fraud or hidden brokerage | Combine evidence review, behavioral signals, reports, manual review, and auditable enforcement |
| Sensitive-data mishandling | Minimise collection, separate evidence storage, restrict access, and define retention/deletion processes before pilot |

## Immediate next actions

1. Name the pilot city and target neighborhoods.
2. Obtain qualified Pakistani legal and privacy advice on ownership evidence, data handling, tenancy templates, and the NADRA onboarding route.
3. Create a NADRA/Nishan Pakistan inquiry pack: company details, use case, data-flow diagram, consent model, security controls, and expected verification volume.
4. Define manual-review service levels and recruit/train the initial verification operator.
5. Turn the landing site and social content plan into an owner-first pilot acquisition campaign.
