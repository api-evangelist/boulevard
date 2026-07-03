# Boulevard GraphQL APIs

Boulevard exposes two distinct, confirmed GraphQL surfaces plus one adjacent REST endpoint. All three require an Enterprise-tier Boulevard account and are provisioned through the Boulevard Developer Portal with a sandbox `businessId` (URN-formatted, e.g. `urn:blvd:Business:{id}`) and `apiKey`, sent as a Bearer token in the `Authorization` header.

- **Admin API** — GraphQL, `https://dashboard.boulevard.io/api/2020-01/admin`. Business-operations data: clients, appointments, staff, locations, memberships, gift cards, vouchers, account credit. This is the surface partner integrations (Klaviyo, Extole) write back into via mutations such as `updateClient`, `CreateGiftCard`, `vouchersCreate`, and `createAccountCreditAdjustment`.
- **Client API** — GraphQL, `https://dashboard.boulevard.io/api/2020-01/client` (confirmed literal endpoint from the public `Boulevard/promotion-demo` reference client's `src/blvd.js`). Powers custom self-booking widgets through a cart workflow: `CreateCart`, `AddCartSelectedPurchasableItem`, `AddCartCardPaymentMethod`, `CheckoutCart`, plus catalog reads (`Businesses`, `Locations`, `Services`, `Staff`, bookable dates/times) mirrored from the official `book-sdk` TypeScript SDK.
- **Tokenization API** — REST, not GraphQL. `POST https://vault.blvd.co/cards/tokenize` (confirmed literal endpoint from the same `promotion-demo` source). Exchanges raw card data for a token client-side so the resulting token — never the card number — is passed to the Client API's `AddCartCardPaymentMethod` mutation, keeping the integrating merchant out of PCI DSS scope.

**Documentation:** https://developers.joinblvd.com/ (full field-level reference sits behind Developer Portal login; the public `graphql-admin-api/api-reference/types/Business` path confirms an Admin API GraphQL schema reference exists)

- Admin API overview: https://developers.joinblvd.com/2020-01/admin-api/overview
- Admin API authentication: https://developers.joinblvd.com/2020-01/admin-api/authentication
- Client API overview: https://developers.joinblvd.com/2020-01/client-api/overview
- Client API authentication: https://developers.joinblvd.com/2020-01/client-api/authentication
- Tokenization API overview: https://developers.joinblvd.com/2020-01/tokenization-api/overview
- Booking SDK (TypeScript, wraps the Client API): https://github.com/Boulevard/book-sdk
- Reference booking flow starter kit: https://github.com/Boulevard/create-booking-flow
- Reference Client API demo (source of the two confirmed endpoint URLs above): https://github.com/Boulevard/promotion-demo

## Endpoint confidence

- **Confirmed** (found literally in Boulevard's own public source code): Client API base URL, Tokenization endpoint, mutation names `CreateCart` / `AddCartSelectedPurchasableItem` / `AddCartCardPaymentMethod` / `CheckoutCart`, SDK modules `Businesses` / `Carts` / `Locations` / `Services` / `Staff` / `Appointments` / `Clients`, Admin API mutation names `CreateGiftCard` / `vouchersCreate` / `createAccountCreditAdjustment` / `updateClient` (from Extole's published integration guide), webhook event names `CLIENT_CREATED` / `APPOINTMENT_CREATED` / `APPOINTMENT_CONFIRMED` / `APPOINTMENT_COMPLETED` / `MEMBERSHIP_CREATED` / `MEMBERSHIP_CANCELLED` / `MEMBERSHIP_RENEWAL_SUCCEEDED`.
- **Modeled** (inferred from the confirmed Client API URL pattern and standard Boulevard versioning, not independently verified): the exact Admin API base URL `https://dashboard.boulevard.io/api/2020-01/admin`, and the field-level shape of the schema below - Boulevard's backend is confirmed to run on Elixir with a forked `absinthe` (the Elixir GraphQL toolkit) repository in the `Boulevard` GitHub organization, consistent with a hand-rolled GraphQL schema rather than an auto-generated one.

## Schema

See [`boulevard-schema.graphql`](boulevard-schema.graphql) for a conceptual schema modeling both the Admin and Client GraphQL surfaces from confirmed type/operation names plus reasonable, clearly-modeled supporting fields.
