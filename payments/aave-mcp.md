---
type: payment
id: aave-mcp
title: Aave MCP
summary: 'Aave''s official MCP server for Aave V3 and V4. An agent can read markets and positions, including health factor, simulate an action, and prepare an unsigned transaction. The user''s wallet signs every state change.'
page_status: current
last_verified: '2026-11-23'
kind: payment-mcp
operator: Aave
agent_can: Read V3 and V4 markets and a wallet's positions, including health factor, and preview and prepare supply, borrow, withdraw, repay and related actions as unsigned transactions or EIP-712 typed data
user_controls: The user's wallet signs every state change. The server never holds keys or signs. Only submit_signed_order and cancel_order relay orders the user has already signed
mcp_server: 'yes'
endpoint: https://mcp.aave.com
availability: No API key and no sign-in. The docs say the endpoint needs no key today, and that clients should handle 401 and 429 responses; numeric limits are unknown.
notes: 'The hosted server is a shared service. Fees, audits of the MCP, and usage numbers are unknown. The npm package @aave/mcp is version 1.0.0 under the Business Source License; the plugin repository is MIT.'
field_sources:
  operator:
  - aa-01
  - aa-03
  agent_can:
  - aa-01
  - aa-03
  - aa-05
  user_controls:
  - aa-01
  - aa-03
  - aa-04
  mcp_server:
  - aa-02
  - aa-03
  endpoint:
  - aa-01
  - aa-02
  - aa-03
  availability:
  - aa-02
  - aa-03
---

# Aave MCP

Aave MCP is Aave's official [MCP](../glossary.md#mcp) server for Aave V3 and V4. An agent can look up markets, inspect a wallet's positions, including the health factor (how close a borrowing position is to liquidation), simulate an action, and prepare a transaction. Nothing goes on chain until the user's own wallet signs it.[^aa-01][^aa-03]

## How an agent connects

- The hosted server is at `https://mcp.aave.com`, over Streamable HTTP. `/mcp` is an alias of the same endpoint.[^aa-02][^aa-03]
- There is no API key and no sign-in. Aave says there is nothing to install and no key to manage for this remote server.[^aa-02][^aa-03]
- The docs say the endpoint needs no key today, and that it is a shared service. Clients should handle 401 and 429 responses; the numeric limits are unknown.[^aa-02]

Aave also publishes a plugin repository with five skills, listed below. Any MCP client can skip the plugin and point at the URL.[^aa-06]

## What the agent can read and prepare

- **Markets and positions.** The agent can retrieve supported chains, reserves, rates, and a wallet's supplies, borrows, health factor, activity and rewards. The same server covers V3 and V4. USD prices are Aave's oracle prices, read from Chainlink price feeds.[^aa-01][^aa-03][^aa-05]
- **Simulate, then build.** `preview_*` tools, including `preview_action`, simulate an action and commit nothing. `prepare_*` tools, including `prepare_action` and `prepare_order`, return an unsigned transaction or [EIP-712](../glossary.md#eip-712) typed data for the user to sign. The docs say not to skip the simulation before a borrow, a withdraw, or certain V4 orders.[^aa-01][^aa-03][^aa-05]
- **Specialized tools.** The inventory also covers token swaps, V4 position swaps and leverage, Savings GHO, rewards, and Aave DAO governance. The live tool list on the endpoint is the authority if it disagrees with the docs.[^aa-01][^aa-05]

## Who approves what

The user's wallet is the last gate before anything reaches a chain.[^aa-04]

- Read tools have no side effects. Preparing a transaction commits nothing.[^aa-01][^aa-04]
- The server never holds private keys and never signs. It returns unsigned transactions or EIP-712 typed data, and it relays swap and leverage orders only after the user signs them.[^aa-01][^aa-03][^aa-04]
- Only two tools change state on the server's side: `submit_signed_order` and `cancel_order` relay an order or cancellation the user has already signed. Neither can create or sign anything of its own.[^aa-03][^aa-04]

## The five skills

Aave's `aave/skills` repository, licensed MIT, ships five skills an agent can use with the server:[^aa-06]

- `safe-transactions` — for a supply, borrow, withdraw or repay: read, simulate, then hand over an unsigned transaction with the health factor after.
- `deleverage` — compare routes that would lift a health factor, then recommend one.
- `account-activity` — a wallet's Aave history and position over time.
- `yield-analysis` — supply and borrow rates across chains and versions, ranked on rates a user can actually enter.
- `tx-confirmation` — confirm what a signed transaction did from the position it left.

The plugin repository is the manifest only; it points at the hosted server, whose implementation is licensed separately. The npm package `@aave/mcp` is published as version 1.0.0 under the Business Source License (BUSL).[^aa-06][^aa-07]

The server also carries five ready-made prompts (`check_health`, `best_stablecoin_yield`, `prepare_supply`, `gho_savings`, and `review_position`). Those are prompts on the server, not the five skills above.[^aa-02]

## What is recorded

The server's llms.txt says calls are counted for product analytics: tool name, MCP method, protocol version, chain id, and client name and version. A call that names a wallet is counted under a keyed hash of it, so no wallet address is recorded. No keys, signatures, transaction content or prompt text are collected.[^aa-03]

## Unknown

Fees, numeric rate limits, audits of the MCP server, and how many people use it are not in the pages cited here, so they are unknown.

## Related

- [Payments](README.md)
- [Agent payments](../rails/agent-payments.md)

## Sources

[^aa-01]: [Aave MCP](../sources/aa-01.md). Aave, official, retrieved 2026-11-23.
[^aa-03]: [Aave MCP llms.txt](../sources/aa-03.md). Aave, official, retrieved 2026-11-23.
[^aa-02]: [Get Started with Aave MCP](../sources/aa-02.md). Aave, official, retrieved 2026-11-23.
[^aa-06]: [GitHub - aave/skills](../sources/aa-06.md). Aave (GitHub), official, retrieved 2026-11-23.
[^aa-05]: [Aave MCP Tools](../sources/aa-05.md). Aave, official, retrieved 2026-11-23.
[^aa-04]: [Aave MCP Safety](../sources/aa-04.md). Aave, official, retrieved 2026-11-23.
[^aa-07]: [@aave/mcp](../sources/aa-07.md). npm (package published by Aave), official, retrieved 2026-11-23.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20payments%2Faave-mcp.md&body=Page%3A%20payments%2Faave-mcp.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
