---
type: provider
id: alpaca
title: Alpaca
summary: Developer-first. Hosted Trading MCP with OAuth (live and paper) plus a local open-source MCP and a CLI using API keys. No broker-side per-order approval is documented; paper trading is built in.
provider: Alpaca
page_status: draft
reviewed_by: null
reviewed_on: null
last_verified: '2026-11-12'
status: official-mcp
can_place_orders: ['yes']
approval_model: [none]
assets: [stocks, ETFs, fractional equities, options (including multi-leg), crypto]
order_types: unknown
auth: "Hosted Trading MCP: OAuth sign-in with an Alpaca account (plugins for Cursor, Claude Code and Codex). Local Trading MCP and CLI: API key and secret in environment variables"
endpoint: https://api.alpaca.markets/mcp
endpoint_note: Paper trading uses https://paper-api.alpaca.markets/mcp. The local server runs over stdio.
transport: [remote-http, local-stdio, cli]
reads_portfolio: 'yes'
paper_trading: 'yes'
limits: unknown
notifications: unknown
notes: Earlier research could not confirm a hosted retail MCP; Alpaca's own agentic repo now documents one. The Broker API MCP (beta) is a separate B2B product for broker partners.
field_sources:
  status: [al-02, al-03, al-09]
  can_place_orders: [al-01, al-09]
  approval_model: [al-05]
  assets: [al-01, al-09]
  auth: [al-03, al-02]
  endpoint: [al-03]
  transport: [al-03, al-02, al-05]
  reads_portfolio: [al-03]
  paper_trading: [al-01, al-03]
---

# Alpaca

> Draft. Not yet reviewed. Every fact below links to a source card; "unknown" means no source in the current batch confirms it.

## Overview and current status

Alpaca is an API-first broker with several official agent options: hosted MCP servers behind OAuth, a local Trading MCP server you run with API keys, and a CLI.[^al-03] The hosted Trading MCP is at `https://api.alpaca.markets/mcp`, with a paper-trading twin at `https://paper-api.alpaca.markets/mcp`.[^al-03] Hosted access currently supports Cursor, Claude Code and Codex through plugins.[^al-03]

Agents can trade fractional equities, ETFs, crypto and multi-leg options.[^al-01] Paper mode starts with $100K in simulated funds; switching to live means changing API keys.[^al-01]

A separate Broker API MCP, in public beta since 2026-07-20, is for broker partners who build investing apps for their own customers.[^al-07][^al-08] It is not a retail path and is noted here only for context.

## Feature matrix

| Feature | Value | Sources |
|---|---|---|
| Read portfolio | Yes (account, orders, positions, portfolio, market data) | [^al-03] |
| Place orders | Yes | [^al-01][^al-09] |
| Order types | unknown | |
| Assets | Stocks, ETFs, fractional equities, options including multi-leg, crypto | [^al-01][^al-09] |
| Paper trading | Yes, separate paper endpoint and $100K simulated balance | [^al-01][^al-03] |
| Tool filtering | `ALPACA_TOOLSETS` limits which tools the local server exposes | [^al-02] |
| Limits | unknown | |
| Notifications | unknown | |

## Implementation details

- **Hosted Trading MCP:** `https://api.alpaca.markets/mcp` (live) and `https://paper-api.alpaca.markets/mcp` (paper), OAuth sign-in with an Alpaca account.[^al-03]
- **Local Trading MCP v2:** a full rewrite on FastMCP and OpenAPI; none of the v1 tools exist in v2.[^al-02] It runs over stdio with API keys and does not set up remote auth, so Alpaca warns not to expose it to the internet.[^al-02]
- **CLI:** built for agents and scripts; Alpaca says it has no confirmation prompts and every command runs immediately.[^al-05]
- **Agent skills:** Alpaca publishes SKILL.md files for its Trading and Broker APIs.[^al-04]

## Guardrails and risks

| Guardrail | Where it is enforced | Sources |
|---|---|---|
| Paper endpoint and simulated balance for testing | Server side (broker) | [^al-01][^al-03] |
| `ALPACA_TOOLSETS` tool filtering | In the local server you run | [^al-02] |
| Per-order approval | Not documented at the broker. The CLI has no confirmation prompts, so any approval step lives in your agent or MCP client | [^al-05] |
| Do not expose the local server publicly | Your deployment | [^al-02] |

## How to build against it

1. Start on the paper endpoint or a paper account.[^al-01][^al-03]
2. For hosted use, install Alpaca's plugin in Cursor, Claude Code or Codex and sign in with OAuth.[^al-03]
3. For local use, run the v2 Trading MCP over stdio with API keys and limit tools with `ALPACA_TOOLSETS`.[^al-02]
4. Add your own approval step before live orders. See [Human-in-the-loop patterns](../build/human-in-the-loop.md).

## Unknown so far

- Order types and limits for agent orders: unknown.
- Whether the hosted Trading MCP adds any broker-side confirmation: unknown.
- Agent terms of use: not yet in the source batch.

## Changelog

- 2026-11-12: Page drafted from source batch 1.

## Sources

[^al-03]: [GitHub - alpacahq/agentic: Multi-platform plugin marketplace for Alpaca APIs · GitHub](../sources/al-03.md). Alpaca (GitHub), official, retrieved 2026-11-12.
[^al-01]: [Alpaca - Trade with AI Using Alpaca's MCP Server](../sources/al-01.md). Alpaca, official, retrieved 2026-11-12.
[^al-07]: [Alpaca Launches MCP Servers in Public Beta for Broker Partners.](../sources/al-07.md). Alpaca, official, retrieved 2026-11-12.
[^al-08]: [Broker API MCP (Alpaca Docs)](../sources/al-08.md). Alpaca Docs, official, retrieved 2026-11-12.
[^al-09]: [Trading API MCP](../sources/al-09.md). Alpaca Docs, official, retrieved 2026-11-12.
[^al-02]: [GitHub - alpacahq/alpaca-mcp-server: Alpaca’s official MCP Server lets you trade stocks, ETFs, crypto, and options, run data analysis, and build strat](../sources/al-02.md). Alpaca (GitHub), official, retrieved 2026-11-12.
[^al-05]: [GitHub - alpacahq/cli: CLI for Trading API · GitHub](../sources/al-05.md). Alpaca (GitHub), official, retrieved 2026-11-12.
[^al-04]: [GitHub - alpacahq/alpaca-skills: Agent skills for Alpaca's Trading API and Broker API: drop-in SKILL.md files for AI coding assistants · GitHub](../sources/al-04.md). Alpaca (GitHub), official, retrieved 2026-11-12.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/TODO-OWNER/ed-agentic-finance-rails/issues/new?title=Correction%3A%20providers%2Falpaca.md&body=Page%3A%20providers%2Falpaca.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue; repo link is a TODO placeholder until the public repo exists)
