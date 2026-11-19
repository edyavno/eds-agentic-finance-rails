---
type: provider
id: alpaca
title: Alpaca
summary: Alpaca's hosted Trading MCP uses OAuth for live and paper accounts; a local MCP and a CLI use API keys. No broker-side per-order approval is documented.
provider: Alpaca
page_status: current
last_verified: '2026-11-19'
status: official-mcp
can_place_orders: ['yes']
approval_model: [none]
assets: [stocks, ETFs, fractional equities, options (including multi-leg), crypto]
order_types: [market, limit, stop, stop-limit, trailing stop, bracket, multi-leg options]
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
  order_types: [al-09]
---

# Alpaca

## Can an AI agent trade at Alpaca?

Yes. Alpaca is an API-first broker with several official agent options: hosted [MCP](../glossary.md#mcp) servers behind [OAuth](../glossary.md#oauth), a local Trading MCP server you run with [API keys](../glossary.md#api-key), and a [CLI](../glossary.md#cli).[^al-03] The hosted Trading MCP is at `https://api.alpaca.markets/mcp`, with a [paper-trading](../glossary.md#paper-trading) twin at `https://paper-api.alpaca.markets/mcp`.[^al-03] Hosted access currently supports Cursor, Claude Code and Codex through plugins.[^al-03]

Agents can trade fractional equities, ETFs, crypto and multi-leg options.[^al-01] Paper mode starts with $100K in simulated funds; switching to live means changing API keys.[^al-01]

A separate Broker API MCP, in public beta since 2026-07-20, is for broker partners who build investing apps for their own customers.[^al-07][^al-08] It is not a retail path and is noted here for context.

## What can an AI agent do at Alpaca?

| Feature | Value | Sources |
|---|---|---|
| Read portfolio | Yes (account, orders, positions, portfolio, market data) | [^al-03] |
| Place orders | Yes | [^al-01][^al-09] |
| Order types | Documented for Alpaca's Trading MCP server: stocks and ETFs (market, limit, stop, stop-limit, trailing stop, brackets), crypto (market, limit, stop-limit), options (single-leg or multi-leg strategies) | [^al-09] |
| Assets | Stocks, ETFs, fractional equities, options including multi-leg, crypto | [^al-01][^al-09] |
| Paper trading | Yes, separate paper endpoint and $100K simulated balance | [^al-01][^al-03] |
| Tool filtering | `ALPACA_TOOLSETS` limits which tools the local server exposes | [^al-02] |
| Limits | unknown | |
| Notifications | unknown | |

## How does Alpaca's agent connection work?

- **Hosted Trading MCP:** `https://api.alpaca.markets/mcp` (live) and `https://paper-api.alpaca.markets/mcp` (paper), OAuth sign-in with an Alpaca account.[^al-03]
- **Local Trading MCP v2:** a full rewrite on FastMCP and [OpenAPI](../glossary.md#openapi); none of the v1 tools exist in v2.[^al-02] It runs over [stdio](../glossary.md#stdio) with API keys and does not set up remote auth, so Alpaca warns not to expose it to the internet.[^al-02]
- **Local server settings:** it exposes 65 tools across the Trading API and Market Data API. It defaults to paper trading; `ALPACA_PAPER_TRADE=false` with live keys switches to live trading. `ALPACA_TOOLSETS` picks toolsets from account, trading, watchlists, assets, stock-data, crypto-data, options-data, corporate-actions, news and fixed-income-data. Alpaca says never to paste API keys into chat.[^al-09]
- **CLI:** built for agents and scripts; Alpaca says it has no confirmation prompts and every command runs immediately.[^al-05]
- **[Agent skills](../glossary.md#agent-skill):** Alpaca publishes SKILL.md files for its Trading and Broker APIs.[^al-04]

## What guardrails and risks apply at Alpaca?

| Guardrail | Where it is enforced | Sources |
|---|---|---|
| Paper endpoint and simulated balance for testing | Server side (broker) | [^al-01][^al-03] |
| `ALPACA_TOOLSETS` tool filtering | In the local server you run | [^al-02] |
| Per-order approval | Not documented at the broker. The CLI has no confirmation prompts, so any approval step lives in your agent or MCP client | [^al-05] |
| Do not expose the local server publicly | Your deployment | [^al-02] |
| Local server defaults to paper trading; live needs `ALPACA_PAPER_TRADE=false` and live keys | In the local server you run | [^al-09] |

## How do you connect an agent to Alpaca?

1. Start on the paper endpoint or a paper account.[^al-01][^al-03]
2. For hosted use, install Alpaca's plugin in Cursor, Claude Code or Codex and sign in with OAuth.[^al-03]
3. For local use, run the v2 Trading MCP over stdio with API keys and limit tools with `ALPACA_TOOLSETS`.[^al-02]
4. Add your own approval step before live orders. See [Human-in-the-loop patterns](../build/human-in-the-loop.md).

## How do I connect Alpaca from my AI app?

Alpaca's hosted MCP works through plugins for Cursor, Claude Code and Codex. Each installed server finishes with a browser-based OAuth sign-in.[^al-03]

| App | How to connect | Sources |
|---|---|---|
| Cursor (hosted) | Run Open Customize from the command palette, click Browse Marketplace, then Add Marketplace → Import from GitHub with `https://github.com/alpacahq/agentic`. Install `alpaca-trading`, then start the server to sign in | [^al-03] |
| Claude Code (hosted) | Run `claude plugin marketplace add alpacahq/agentic`, install `alpaca-trading` with `/plugin`, then run `/reload-plugins` and `/mcp` to sign in | [^al-03] |
| Codex (hosted) | Run `codex plugin marketplace add alpacahq/agentic`, install the plugin, then `codex mcp login <mcp-name>` to sign in | [^al-03] |
| Claude Desktop, VS Code, Cursor, PyCharm, Claude Code, Gemini CLI (local) | Run the local Trading MCP server with your API keys; Alpaca's docs list these apps for local or remote use | [^al-09] |
| ChatGPT | ChatGPT needs a remote MCP server. The local package does not set up remote authentication, so do not expose it to the internet with your API keys | [^al-02] |

Alpaca's MCP product page also shows install buttons for Claude Desktop, Claude Mobile, ChatGPT, Cursor, Visual Studio Code, PyCharm, Claude Code, Antigravity CLI and Postman.[^al-01]

## What is still unknown about Alpaca?

- Limits for agent orders: unknown. (Order types are now documented; see the table above.)[^al-09]
- Whether the hosted Trading MCP adds any broker-side confirmation: unknown.
- Agent terms of use: not yet reviewed here.

Every fact on this page links to a source card; "unknown" means no source we cite confirms it.

## What changed on this page?

- 2026-11-19: Added order types, how to connect from each app, the local server's paper-trading default and toolsets.[^al-09][^al-03][^al-02][^al-01]
- 2026-11-12: First version of this page.

## Sources

[^al-03]: [GitHub - alpacahq/agentic: Multi-platform plugin marketplace for Alpaca APIs · GitHub](../sources/al-03.md). Alpaca (GitHub), official, retrieved 2026-11-19.
[^al-01]: [Alpaca - Trade with AI Using Alpaca's MCP Server](../sources/al-01.md). Alpaca, official, retrieved 2026-11-19.
[^al-07]: [Alpaca Launches MCP Servers in Public Beta for Broker Partners.](../sources/al-07.md). Alpaca, official, retrieved 2026-11-12.
[^al-08]: [Broker API MCP (Alpaca Docs)](../sources/al-08.md). Alpaca Docs, official, retrieved 2026-11-12.
[^al-09]: [Trading API MCP](../sources/al-09.md). Alpaca Docs, official, retrieved 2026-11-19.
[^al-02]: [GitHub - alpacahq/alpaca-mcp-server: Alpaca’s official MCP Server lets you trade stocks, ETFs, crypto, and options, run data analysis, and build strat](../sources/al-02.md). Alpaca (GitHub), official, retrieved 2026-11-19.
[^al-05]: [GitHub - alpacahq/cli: CLI for Trading API · GitHub](../sources/al-05.md). Alpaca (GitHub), official, retrieved 2026-11-12.
[^al-04]: [GitHub - alpacahq/alpaca-skills: Agent skills for Alpaca's Trading API and Broker API: drop-in SKILL.md files for AI coding assistants · GitHub](../sources/al-04.md). Alpaca (GitHub), official, retrieved 2026-11-12.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20providers%2Falpaca.md&body=Page%3A%20providers%2Falpaca.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
