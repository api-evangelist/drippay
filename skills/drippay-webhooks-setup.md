---
name: Register and verify webhooks
description: Discover event types, register a webhook endpoint, test it, rotate its signing secret, and inspect deliveries with the Drip API.
api: openapi/drippay-openapi-original.json
operations: [listWebhookEventTypes, createWebhook, testWebhook, rotateWebhookSecret, listWebhookDeliveries, retryWebhookDelivery]
---

# Register and verify webhooks

Base URL `https://api.drippay.dev`. Auth: `Authorization: Bearer sk_live_...`.

## Steps
1. `listWebhookEventTypes` — `GET /v1/webhooks/events` to see subscribable events (e.g. `invoice.paid`, `usage.recorded`, `charge.failed`, `customer.spending.exceeded`).
2. `createWebhook` — `POST /v1/webhooks` with your HTTPS endpoint URL and the event types to subscribe. Store the returned signing secret.
3. `testWebhook` — `POST /v1/webhooks/{id}/test` to send a sample delivery and confirm your receiver validates the HMAC signature.
4. `rotateWebhookSecret` — `POST /v1/webhooks/{id}/rotate-secret` on a cadence; update your verifier with the new secret.
5. `listWebhookDeliveries` / `retryWebhookDelivery` — inspect delivery history and replay failed deliveries.

## Conventions
- Verify the HMAC signature on every inbound delivery before trusting the payload.
- Respond `2xx` quickly; the endpoint is marked unhealthy (`webhook.endpoint.unhealthy`) after repeated failures.
- Errors return `{ error, code, details[] }`.
