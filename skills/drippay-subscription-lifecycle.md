---
name: Create a plan and manage a subscription
description: Define a pricing plan, subscribe a customer, then update, pause, or cancel the subscription with the Drip API.
api: openapi/drippay-openapi-original.json
operations: [createPricingPlan, attachPlanToCustomer, createSubscription, updateSubscription, pauseSubscription, resumeSubscription, cancelSubscription]
---

# Create a plan and manage a subscription

Base URL `https://api.drippay.dev`. Auth: `Authorization: Bearer sk_live_...`.

## Conventions
- Include `idempotencyKey` on `createPricingPlan` and `createSubscription`.
- `429` = rate limited; retry with backoff. Errors: `{ error, code, details[] }`.

## Steps
1. `createPricingPlan` — define pricing tied to billable metrics / unit types. Save the plan `id`.
2. `attachPlanToCustomer` — associate the plan with a customer (`POST /v1/customers/{id}/attach-plan`).
3. `createSubscription` — start the subscription for the customer against the plan.
4. `updateSubscription` — change quantities or plan version as needed.
5. Lifecycle control: `pauseSubscription` / `resumeSubscription` for temporary holds, `cancelSubscription` to end it.

## Verify
`getSubscription` for status, and `getUpcomingInvoice` (`/v1/subscriptions/{id}/upcoming-invoice`) to preview the next charge.
