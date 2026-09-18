# Architecture and System Boundaries

## Documented Architecture

The existing public documentation describes a web-based internal admin application: Laravel/PHP for application logic, MySQL for structured storage, Blade for server-rendered views, Docker for local development, and Git for versioning. These descriptions are consistent across the reviewed repository and saved README. They are not a verification of current production versions or deployment configuration.

## Conceptual Responsibilities

| Responsibility | Business purpose | Public boundary |
|---|---|---|
| Operational entry | Capture information needed by the workflow | No real forms, customer records or production screenshots |
| Application rules | Interpret entries and their effect on connected workflows | No source fragments, routes or unverified algorithm claims |
| Structured records | Keep related business information available for later use | No table names, private schema or database contents |
| Admin/reporting views | Make payment and outstanding-balance information understandable | Synthetic examples only; no operational exports |

These are conceptual responsibilities, not claims about separate deployed services, API endpoints or exact internal component boundaries.

## Invoice / Payment / Reporting Relationship

![Conceptual synthetic flow](../assets/diagrams/invoice-payment-flow.svg)

For one synthetic invoice of 1,000 illustrative units, an applied payment of 400 leaves 600 outstanding. The report needs to express those three values consistently. This explains a business invariant, not the private implementation of persistence, calculation or reconciliation.

## Decisions and Trade-offs

- A server-rendered internal interface is the approach described in the existing documentation. No comparison benchmark against other frameworks is claimed.
- Related operational events should be considered together when reviewing totals. The public evidence does not establish transaction isolation, concurrency control, immutable audit logs or idempotency.
- Synthetic workflow evidence protects the operational system while making the reasoning reviewable. It cannot independently demonstrate current production behavior.

## Not Verified in This Update

Exact release/module versions, database relationships, API integrations, authentication/authorization rules, hosting topology, backups, recovery behavior, rounding policy and automated test coverage. These are omitted as implementation claims. Docker's documented local-development use must not be read as proof of containerized production deployment.

See [evidence register](evidence-register.md) and [validation scenarios](validation-scenarios.md).
