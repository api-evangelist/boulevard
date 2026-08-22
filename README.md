# Boulevard (boulevard)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Boulevard is a client experience platform purpose-built for appointment-based self-care businesses - hair salons, spas, medspas, barbershops, and nail salons. The platform covers self-scheduling, CRM, marketing, payments (as a certified PayFac), and reporting. Boulevard exposes its integration surface as GraphQL - a Client API for building custom booking experiences and an Admin API for syncing business operations data (clients, appointments, staff, locations, memberships, gift cards) - plus a separate Tokenization API for PCI-scope-reducing card capture. API access is gated to the Enterprise tier and provisioned through a developer sandbox (business ID + API key) via the Boulevard Developer Portal.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/boulevard/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/boulevard/refs/heads/main/apis.yml)

## Tags

- Salon Software
- Spa Software
- Med Spa
- Appointment Scheduling
- GraphQL
- CRM
- Payments
- Self-Care

## Timestamps

- **Created:** 2026-07-03
- **Modified:** 2026-07-03

## APIs

### Boulevard Admin API - Clients & CRM

Query and mutate client (customer) records synced from Boulevard's CRM - profiles, contact details, custom fields, loyalty point balances, and appointment history. Third parties such as Klaviyo and Extole use this domain's `updateClient` mutation to write loyalty and referral state back into Boulevard.

- **Human URL:** [https://developers.joinblvd.com/2020-01/admin-api/overview](https://developers.joinblvd.com/2020-01/admin-api/overview)
- **Base URL:** `https://dashboard.boulevard.io/api/2020-01/admin`

#### Tags

- Clients
- CRM
- Custom Fields
- GraphQL

#### Properties

- [Documentation](https://developers.joinblvd.com/2020-01/admin-api/overview)
- [Documentation](https://developers.joinblvd.com/2020-01/admin-api/authentication)
- [API Reference](https://developers.joinblvd.com/graphql-admin-api/api-reference/types/Business)
- [GraphQL](graphql/boulevard-graphql.md)
- [GraphQL Schema](graphql/boulevard-schema.graphql)
- [Postman Collection](collections/boulevard.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/boulevard.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Boulevard Admin API - Appointments, Staff & Locations

Read and sync appointment, staff, and location data across a business's calendar - past, current, and future appointments, professional rosters, and the physical/virtual locations services are delivered from. Backs webhook-driven integrations that react to APPOINTMENT_CREATED, APPOINTMENT_CONFIRMED, and APPOINTMENT_COMPLETED events.

- **Human URL:** [https://developers.joinblvd.com/2020-01/admin-api/overview](https://developers.joinblvd.com/2020-01/admin-api/overview)
- **Base URL:** `https://dashboard.boulevard.io/api/2020-01/admin`

#### Tags

- Appointments
- Scheduling
- Staff
- Locations
- GraphQL

#### Properties

- [Documentation](https://developers.joinblvd.com/2020-01/admin-api/overview)
- [Documentation](https://developers.joinblvd.com/2020-01/admin-api/authentication)
- [GraphQL](graphql/boulevard-graphql.md)
- [GraphQL Schema](graphql/boulevard-schema.graphql)
- [Postman Collection](collections/boulevard.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/boulevard.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Boulevard Admin API - Memberships & Packages

Access recurring membership and prepaid package data - plan status, renewal state, and entitlements. Membership lifecycle changes are also pushed outbound as MEMBERSHIP_CREATED, MEMBERSHIP_CANCELLED, and MEMBERSHIP_RENEWAL_SUCCEEDED webhook events, which downstream tools like Klaviyo consume for lifecycle marketing.

- **Human URL:** [https://developers.joinblvd.com/2020-01/admin-api/overview](https://developers.joinblvd.com/2020-01/admin-api/overview)
- **Base URL:** `https://dashboard.boulevard.io/api/2020-01/admin`

#### Tags

- Memberships
- Packages
- Subscriptions
- GraphQL

#### Properties

- [Documentation](https://developers.joinblvd.com/2020-01/admin-api/overview)
- [GraphQL](graphql/boulevard-graphql.md)
- [GraphQL Schema](graphql/boulevard-schema.graphql)
- [Postman Collection](collections/boulevard.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/boulevard.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Boulevard Admin API - Payments, Gift Cards & Vouchers

Issue and manage stored-value gift cards, service vouchers, and account credit adjustments as a certified payment facilitator. Documented mutations include `CreateGiftCard`, `vouchersCreate`, and `createAccountCreditAdjustment`, used by referral/loyalty platforms (e.g. Extole) to fulfill rewards directly inside a business's Boulevard account.

- **Human URL:** [https://developers.joinblvd.com/2020-01/admin-api/overview](https://developers.joinblvd.com/2020-01/admin-api/overview)
- **Base URL:** `https://dashboard.boulevard.io/api/2020-01/admin`

#### Tags

- Payments
- Gift Cards
- Vouchers
- Account Credit
- GraphQL

#### Properties

- [Documentation](https://developers.joinblvd.com/2020-01/admin-api/overview)
- [GraphQL](graphql/boulevard-graphql.md)
- [GraphQL Schema](graphql/boulevard-schema.graphql)
- [Postman Collection](collections/boulevard.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/boulevard.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Boulevard Client API - Booking Cart & Checkout

Build custom, on-brand self-booking experiences on top of a cart workflow - create a cart for a location, add a selected purchasable (service) item, reserve an available timeslot, attach a tokenized card as the payment method, and check out. Confirmed mutations from the official `book-sdk` and `promotion-demo` reference clients include `CreateCart`, `AddCartSelectedPurchasableItem`, `AddCartCardPaymentMethod`, and `CheckoutCart`.

- **Human URL:** [https://developers.joinblvd.com/2020-01/client-api/overview](https://developers.joinblvd.com/2020-01/client-api/overview)
- **Base URL:** `https://dashboard.boulevard.io/api/2020-01/client`

#### Tags

- Booking
- Cart
- Checkout
- GraphQL

#### Properties

- [Documentation](https://developers.joinblvd.com/2020-01/client-api/overview)
- [Documentation](https://developers.joinblvd.com/2020-01/client-api/authentication)
- [SDK](https://github.com/Boulevard/book-sdk)
- [SDK](https://github.com/Boulevard/create-booking-flow)
- [GraphQL](graphql/boulevard-graphql.md)
- [GraphQL Schema](graphql/boulevard-schema.graphql)
- [Postman Collection](collections/boulevard.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/boulevard.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Boulevard Client API - Catalog & Availability

Public-facing catalog reads that power a booking widget before a client ever creates a cart - business and location lookup, bookable service categories, staff/professional listings, and bookable dates/times for a chosen service and location. Mirrors the `book-sdk` modules `Businesses`, `Locations`, `Services`, `Staff`, and the cart's `getBookableDates` / `getBookableTimes` calls.

- **Human URL:** [https://developers.joinblvd.com/2020-01/client-api/overview](https://developers.joinblvd.com/2020-01/client-api/overview)
- **Base URL:** `https://dashboard.boulevard.io/api/2020-01/client`

#### Tags

- Services
- Staff
- Locations
- Availability
- GraphQL

#### Properties

- [Documentation](https://developers.joinblvd.com/2020-01/client-api/overview)
- [SDK](https://github.com/Boulevard/book-sdk)
- [GraphQL](graphql/boulevard-graphql.md)
- [GraphQL Schema](graphql/boulevard-schema.graphql)
- [Postman Collection](collections/boulevard.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/boulevard.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Boulevard Tokenization API

A narrow, non-GraphQL REST endpoint (`POST https://vault.blvd.co/cards/tokenize`, confirmed in the public `promotion-demo` reference client's source) used to exchange raw card details for a reusable payment token client-side, before that token is attached to a cart via the Client API's `AddCartCardPaymentMethod` mutation. Keeps merchant integrations out of PCI DSS scope by ensuring card numbers never transit the integrator's own servers.

- **Human URL:** [https://developers.joinblvd.com/2020-01/tokenization-api/overview](https://developers.joinblvd.com/2020-01/tokenization-api/overview)
- **Base URL:** `https://vault.blvd.co`

#### Tags

- Tokenization
- PCI Compliance
- Payments
- REST

#### Properties

- [Documentation](https://developers.joinblvd.com/2020-01/tokenization-api/overview)

## Common Properties

- [GitHub Organization](https://github.com/Boulevard)
- [LinkedIn](https://www.linkedin.com/company/boulevard)
- [Website](https://www.joinblvd.com/)
- [Documentation](https://developers.joinblvd.com/)
- [Plans](plans/boulevard-plans-pricing.yml)
- [Rate Limits](rate-limits/boulevard-rate-limits.yml)
- [Fin Ops](finops/boulevard-finops.yml)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
