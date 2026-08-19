---
name: Connect to Revnu and inspect a store
description: Attach an agent to the Revnu MCP server, authenticate with a dashboard-issued
  bearer key, and read the store's current state — products, connections and KPIs —
  before changing anything.
api: mcp/revnu-mcp.yml
operations:
- get_context
- list_products
- get_kpis
- get_stripe_status
generated: '2026-08-13'
method: generated
source: https://auth.revnu.app/docs/mcp
---

# Connect to Revnu and inspect a store

Revnu exposes one agent surface: a remote MCP server over streamable HTTP. Every
tool below is a real tool from Revnu's published tool reference.

## 1. Get a key

The operator generates the key in the Revnu dashboard under **CLI → API Keys &
MCP**. Keys are prefixed `rev_cli_` or `rev_`. There is no OAuth flow, no scopes
and no key-provisioning API — an agent cannot mint its own key.

## 2. Point at the endpoint that answers

Revnu's docs, its MCP server card and its `/.well-known/api-catalog` all publish
`https://revnu.app/api/mcp`. That host 308-redirects to `https://revnu.com`,
where every `/api/*` path returns an HTML 404, so the published config fails.

Use the host that actually serves the server:

```json
{
  "mcpServers": {
    "revnu": {
      "type": "streamable-http",
      "url": "https://auth.revnu.app/api/mcp",
      "headers": { "Authorization": "Bearer YOUR_REVNU_KEY" }
    }
  }
}
```

An anonymous `tools/list` against that URL returns
`401 {"code":-32001,"message":"Unauthorized: Missing or invalid Bearer token"}` —
that response is how you confirm you have reached the real server rather than the
marketing site.

## 3. Read before you write

1. Call `get_context` first. It returns the store, its products, its connected
   services (Stripe, Discord, GitHub) and the remaining onboarding steps. Do not
   create anything until you have seen it — `create_store` on an account that
   already has a store is not idempotent.
2. Call `list_products` to see what is already sellable. Products are `draft`
   until they sync to Stripe, then `active`.
3. Call `get_stripe_status`. Without a connected Stripe account, nothing can be
   sold and product creation is wasted work.
4. Call `get_kpis` for MRR, ARR, active members, total members and total sales.

## 4. Rules that apply to every later call

- **No idempotency.** Revnu documents no idempotency key. A retried create is a
  second record. Re-read with the matching `list_*` tool before retrying.
- **Money is integer minor units.** `price` and `amountCents` are cents; `2999`
  is $29.99.
- **Currency is sticky.** A store's currency cannot change once products exist,
  and a product's currency cannot change after Stripe sync.
- **Errors are `{"error": "...", "message": "..."}`** — not RFC 9457. Match the
  literal `error` string. A `405` comes back with an empty body.
- **No published rate limits.** Nothing in Revnu's docs states a limit and no
  `RateLimit-*` or `Retry-After` header is returned. Back off on your own.

See `conventions/revnu-conventions.yml` and `errors/revnu-problem-types.yml`.
