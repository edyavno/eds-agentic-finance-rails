---
type: provider
id: coinbase
title: Coinbase
summary: Coinbase for Agents. Remote MCP with OAuth (allowlisted clients) or a local CLI with an API key. Agents can be limited to a dedicated portfolio chosen on the approval screen.
provider: Coinbase
page_status: current
last_verified: '2026-11-12'
status: official-mcp
can_place_orders: ['yes']
approval_model: [separate-account]
assets: [crypto spot, US derivatives (futures), eligible US equities, x402 payments]
order_types: unknown
auth: OAuth via login.coinbase.com for the remote MCP; Dynamic Client Registration and Client ID Metadata Documents supported, but clients are allowlisted; the local CLI uses a CDP API key
endpoint: https://agents.coinbase.com/mcp
transport: [remote-http, cli]
reads_portfolio: 'yes'
paper_trading: unknown
limits: unknown
notifications: unknown
notes: The dedicated portfolio is optional; the main account can also be used. Isolated agent portfolios are spot-crypto only. Per-order confirmation depends on the AI client.
field_sources:
  status: [cb-01, cb-07]
  can_place_orders: [cb-01]
  approval_model: [cb-01, cb-03, cb-07]
  assets: [cb-01]
  auth: [cb-01, cb-04]
  endpoint: [cb-01, cb-04]
  transport: [cb-01]
  reads_portfolio: [cb-01]
---

# Coinbase

> Every fact below links to a source card; "unknown" means no source in the current batch confirms it.

## Overview and current status

Coinbase for Agents connects AI apps to a Coinbase account for crypto, equities and derivatives trading, portfolio management and x402 payments.[^cb-01] It launched on 2026-06-11 with an MCP server and a CLI. At launch, crypto spot and derivatives were enabled and stocks were described as coming.[^cb-07] The current docs list eligible US stocks.[^cb-01]

There are two ways in: a remote MCP server at `https://agents.coinbase.com/mcp` using OAuth, and a local CLI that uses a CDP API key.[^cb-01] The CDP CLI/MCP for the developer platform is a separate product for wallets and payments, not consumer account access.[^cb-05]

## Feature matrix

| Feature | Value | Sources |
|---|---|---|
| Read portfolio | Yes | [^cb-01] |
| Place orders | Yes, with a known limitation on some hosted clients (see below) | [^cb-01] |
| Order types | unknown | |
| Assets | Crypto spot, US derivatives (futures), eligible US equities | [^cb-01] |
| Payments | x402 payments for premium data from a USDC balance | [^cb-01] |
| Limits (size, spend) | unknown. Trade-size and spend rules were announced as coming soon | [^cb-07] |
| Notifications | unknown | |
| Paper or sandbox | unknown | |

## Implementation details

- **Endpoint:** `https://agents.coinbase.com/mcp`, for example `claude mcp add coinbase --transport http https://agents.coinbase.com/mcp`.[^cb-01]
- **Auth:** OAuth with `login.coinbase.com` as the authorization server.[^cb-04] Dynamic Client Registration and Client ID Metadata Documents are supported, but Coinbase still allowlists clients.[^cb-01]
- **Scopes advertised:** include `mcp:orders:create`, `mcp:trades:create`, `mcp:transfers:create` and `mcp:portfolios:update`.[^cb-04]
- **Account boundary:** you choose which portfolios the agent can reach on the OAuth approval screen.[^cb-03] Isolated agent portfolios are spot crypto only; US derivatives work only in the default portfolio.[^cb-01]
- **CLI:** runs locally with a CDP API key; Coinbase calls it the most reliable way to execute trades across models.[^cb-01]

## Guardrails and risks

| Guardrail | Where it is enforced | Sources |
|---|---|---|
| Dedicated portfolio chosen at sign-in | Server side (broker), optional | [^cb-03][^cb-07] |
| Main account access is also allowed | | [^cb-07] |
| Client allowlisting, including DCR clients | Server side (broker) | [^cb-01] |
| Maximum trade size and spend rules | Announced as "soon", not shipped in the sources | [^cb-07] |
| Per-order confirmation | Client side. Coinbase documents that Claude previews and asks to confirm, while ChatGPT creates the order in one turn | [^cb-01] |
| KYT transaction monitoring on payments | Server side (broker) | [^cb-07] |

The advertised scopes include transfers, so check which tools your client exposes before connecting a funded account.[^cb-04]

## How to build against it

1. Create and fund a dedicated portfolio with only what the agent may use, then pick only that portfolio on the approval screen.[^cb-03]
2. Add the remote MCP in your client, or use the CLI with a CDP API key for terminal agents.[^cb-01]
3. If your agent only previews orders on a hosted client, ask it to execute explicitly or use the CLI, as Coinbase suggests.[^cb-01]

See [Connect an MCP client](../build/connect-an-mcp-client.md).

## Unknown so far

- Order types and limits: unknown.
- Paper trading for the consumer agent product: unknown. A news report's "separate sandbox" describes running the agent outside the main account, which reads like the isolated portfolio rather than paper trading.[^cb-08]
- Agent terms of use: not yet in the source batch.

## Changelog

- 2026-11-12: Page drafted from source batch 1.

## Sources

[^cb-01]: [Coinbase MCP - Coinbase Developer Documentation](../sources/cb-01.md). Coinbase Developer Platform, official, retrieved 2026-11-12.
[^cb-07]: [Coinbase for Agents: Your AI Agent Can Now Trade and Pay with Coinbase](../sources/cb-07.md). Coinbase, official, retrieved 2026-11-12.
[^cb-05]: [CDP MCP - Coinbase Developer Documentation](../sources/cb-05.md). Coinbase Developer Platform, official, retrieved 2026-11-12.
[^cb-04]: [Coinbase for Agents MCP: OAuth protected-resource metadata](../sources/cb-04.md). Coinbase (endpoint metadata), official, retrieved 2026-11-12.
[^cb-03]: [Coinbase for Agents setup skill (skill.md)](../sources/cb-03.md). Coinbase Developer Platform, official, retrieved 2026-11-12.
[^cb-08]: [Coinbase’s new tool can help agents trade and pay for premium research - TechCrunch](../sources/cb-08.md). TechCrunch, third-party, retrieved 2026-11-12.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20providers%2Fcoinbase.md&body=Page%3A%20providers%2Fcoinbase.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
