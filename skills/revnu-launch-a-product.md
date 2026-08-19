---
name: Launch a product on a Revnu store
description: Create a priced product with a delivery feature, confirm Stripe is connected,
  publish the store, and verify the product went active — using Revnu's MCP tools.
api: mcp/revnu-mcp.yml
operations:
- get_context
- get_stripe_connect_url
- get_stripe_status
- create_product
- get_product
- list_products
- publish_store
- get_public_key
generated: '2026-08-13'
method: generated
source: https://auth.revnu.app/docs/cli
---

# Launch a product on a Revnu store

Prerequisite: an authenticated MCP connection (see
`skills/revnu-connect-and-inspect-store.md`).

## Steps

1. **`get_context`** — confirm the store exists, note its currency and its
   enabled product types (`web_app`, `discord`).
2. **`get_stripe_status`** — a product cannot go `active` without Stripe. If it
   is not connected, call **`get_stripe_connect_url`** and hand the URL to the
   human. Do not attempt to complete Stripe onboarding on their behalf.
3. **`create_product`** with:
   - `name`
   - `price` in **cents** (`2999` = $29.99)
   - `interval` — `one-time` (permanent access) or `monthly` (subscription)
   - `features` — the delivery method: `web_app` for SDK-gated app access,
     `discord` for role assignment on purchase
   - `maxDevices` where the product is device-limited
   Currency is inherited from the store and cannot be changed afterwards, so
   check it in step 1 rather than assuming USD.
4. **`get_product`** with the returned id and confirm `status` moved from
   `draft` to `active`. If it is still `draft`, Stripe sync has not completed —
   poll, do not create a second product.
5. **`publish_store`** once the catalogue is right. This also marks onboarding
   complete.
6. For a `web_app` product, call **`get_public_key`** and give the operator the
   `rev_pub_` key. It goes into their app as `NEXT_PUBLIC_REVNU_KEY` (Next.js),
   `VITE_REVNU_KEY` (Vite) or `REVNU_KEY` (server), and `@revnu/auth` handles the
   rest — entitlement is embedded in the RS256 session JWT, so no webhook is
   required for access control.

## Cautions

- `create_product` is not idempotent. On any ambiguous failure, call
  `list_products` and check before retrying.
- `delete_product` is destructive and has no undo tool.
- If the operator needs purchase data in their own database (CRM sync,
  notification emails), point them at the webhook surface —
  `purchase.completed`, `purchase.cancelled`, `payment.failed`,
  `plan.switched`, signed with HMAC-SHA256 in the `x-rev-signature` header. See
  `asyncapi/revnu-webhooks.yml`.
