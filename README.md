# Boulevard (boulevard)

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
