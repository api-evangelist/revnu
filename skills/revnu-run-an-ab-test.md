---
name: Run and read an A/B test on a Revnu landing page
description: Create a weighted multi-variant landing-page test, start it, read conversion
  results, and pick a winner — or hand the whole loop to Revnu's optimization agent.
api: mcp/revnu-mcp.yml
operations:
- list_abtests
- create_abtest
- start_abtest
- get_abtest_results
- pause_abtest
- stop_abtest
- generate_landing_page
- get_landing_page_status
- trigger_optimization_cycle
- get_optimization_status
generated: '2026-08-13'
method: generated
source: https://auth.revnu.app/docs/storefronts
---

# Run and read an A/B test on a Revnu landing page

Prerequisite: an authenticated MCP connection (see
`skills/revnu-connect-and-inspect-store.md`).

## Manual test

1. **`list_abtests`** — never start a second test against the same page while one
   is `running`; you will split traffic against yourself.
2. Need a variant to test? **`generate_landing_page`** with a vibe description,
   then poll **`get_landing_page_status`** until the deployment exists. Existing
   deployments in version history can also be used as variants.
3. **`create_abtest`** with:
   - at least **2 variants**, each pointing at a landing-page deployment
   - a **weight** per variant, integers `0–100` that must sum to **exactly 100**
   - `durationDays` between **1 and 90** — the test auto-completes when reached
   - `goalEvent`, default `checkout_completed`
   The test is created in `draft`. Variants and weights can only be edited while
   it is `draft`.
4. **`start_abtest`** to go live. Traffic is allocated with Thompson sampling, so
   the split will drift away from the nominal weights as evidence accumulates —
   that is expected, not a bug.
5. **`get_abtest_results`** for conversion data. Do not call it once and declare a
   winner; let the configured duration run.
6. **`pause_abtest`** to hold traffic without discarding the test.
   **`stop_abtest`** ends it and determines the winner.

## Agent-run optimization

Revnu can run the whole loop itself: **`trigger_optimization_cycle`** analyses the
current landing page, generates an improved variant, starts a test, monitors it
and picks a winner, feeding each cycle back into a knowledge base. Read progress
with **`get_optimization_status`**.

Use this when the operator wants continuous optimization rather than one
question answered. Do not trigger a cycle while a manual test is `running`.

## Cautions

- `delete_abtest` destroys the test and its results; there is no undo tool.
- Weights that do not sum to 100 are rejected — validate before calling.
- No idempotency key exists, so a retried `create_abtest` creates a second test.
  Re-check with `list_abtests`.
