---
name: Meter usage and bill a customer
description: Create a customer, record metered usage, then generate and issue an invoice with the Drip API.
api: openapi/drippay-openapi-original.json
operations: [createCustomer, recordUsage, listUsageEvents, generateInvoice, issueInvoice, markInvoicePaid]
---

# Meter usage and bill a customer

Use the Drip API usage-based billing flow. Base URL `https://api.drippay.dev`.

## Auth
Send `Authorization: Bearer sk_live_...` (or `sk_test_...` for non-billing test flows). Keys are server-side only; read from the `DRIP_API_KEY` env var.

## Conventions
- Pass an `idempotencyKey` on every write (`recordUsage`, `generateInvoice`) so retries never double-record or double-bill.
- List calls use cursor pagination (`cursor`, `limit`).
- Errors return `{ error, code, details[] }`; `429` means back off and retry.

## Steps
1. `createCustomer` — provide at least `externalCustomerId` (or an on-chain address). Save the returned customer `id`.
2. `recordUsage` — post usage events with `customerId`, a `meter` name, and `quantity`. Use `recordInternalUsage` first if you want to track without billing.
3. `listUsageEvents` — confirm the events landed for the customer before invoicing.
4. `generateInvoice` — roll recorded usage into a draft invoice for the customer.
5. `issueInvoice` — finalize and issue the invoice.
6. `markInvoicePaid` — record payment once settled (or let the Stripe integration reconcile it).

## Verify
Fetch the customer `getCustomerBalance` and confirm the invoice via `getInvoice`.
