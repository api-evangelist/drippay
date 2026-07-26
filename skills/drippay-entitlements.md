---
name: Assign and check entitlements
description: Create an entitlement plan, assign it to a customer, and gate features by checking entitlements with the Drip API.
api: openapi/drippay-openapi-original.json
operations: [createEntitlementPlan, createEntitlementRule, assignCustomerEntitlement, checkEntitlement, getCustomerEntitlementUsage]
---

# Assign and check entitlements

Base URL `https://api.drippay.dev`. Auth: `Authorization: Bearer sk_live_...`.

## Steps
1. `createEntitlementPlan` — define an entitlement plan (`POST /v1/entitlement-plans`). Save its `id`.
2. `createEntitlementRule` — add feature/quota rules to the plan (`POST /v1/entitlement-plans/{id}/rules`).
3. `assignCustomerEntitlement` — assign the plan to a customer (`PUT /v1/customers/{customerId}/entitlement`).
4. `checkEntitlement` — at feature-access time, call `POST /v1/entitlements/check` to authorize (returns whether the customer may use the feature/quota).
5. `getCustomerEntitlementUsage` — read consumption against entitlement limits.

## Conventions
- Errors return `{ error, code, details[] }`; `403` means the entitlement denies access.
- Use `idempotencyKey` on assignment writes.

## Verify
`getCustomerEntitlement` (`GET /v1/customers/{customerId}/entitlement`) reflects the assigned plan.
