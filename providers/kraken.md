---
type: provider
id: kraken
title: Kraken
summary: 'Kraken ships a local MCP server with its CLI. It runs on your own machine, can trade live only when you turn on trading services, and asks you to approve each order, withdrawal or transfer.'
provider: Kraken
page_status: current
last_verified: '2026-11-19'
status: official-mcp
can_place_orders: ['yes']
approval_model: [per-order-confirm]
assets: [crypto spot, xStocks (tokenized US stocks and ETFs), forex, perpetual futures, inverse and fixed-date futures, earn and staking]
order_types: [market, limit]
auth: 'API key and secret in environment variables, or a stored key: a browser sign-in key from kraken auth login (restricted, no withdrawal rights, expires after 90 days by default) or a key you created, stored with kraken setup'
endpoint: null
endpoint_note: The MCP server, kraken-mcp, runs locally over stdio and is not exposed as a network service. There is no Kraken-hosted MCP endpoint.
transport: [local-stdio, cli]
reads_portfolio: 'yes'
paper_trading: 'yes'
limits: Position size limits and pair allowlists can be set on the API key in Kraken's settings
notifications: unknown
notes: Dangerous tools ask for approval on every call through MCP elicitation; a client that cannot show the prompt relies on its own tool-approval setting, and --allow-dangerous turns the gate off. The kraken CLI itself places orders without a confirmation prompt.
field_sources:
  status: [kr-01, kr-03]
  can_place_orders: [kr-01, kr-03]
  approval_model: [kr-01]
  assets: [kr-02]
  order_types: [kr-02]
  auth: [kr-01, kr-02]
  endpoint: [kr-01]
  transport: [kr-01, kr-02]
  reads_portfolio: [kr-01]
  paper_trading: [kr-01, kr-02]
  limits: [kr-01]
---

# Kraken

## Can an AI agent trade at Kraken?

Yes, through a server that runs on your own machine. Kraken's [CLI](../glossary.md#cli), kraken-cli, includes an [MCP](../glossary.md#mcp) server, kraken-mcp, that runs over [stdio](../glossary.md#stdio). It serves 152 of the CLI's 188 commands as MCP tools for Claude, Cursor, GitHub Copilot, Windsurf and other MCP clients.[^kr-01] The server is not exposed as a network service, and Kraken does not host an MCP endpoint.[^kr-01]

One install covers crypto spot, xStocks (tokenized equities), forex, perpetual and fixed-date futures, and earn and staking.[^kr-02] Kraken's GitHub page says the tokenized US stocks and ETFs are for non-US customers.[^kr-03]

Live trading only happens when you start the server with a trading service, such as `trade` for spot orders. Kraken's quickstart set, `kraken-mcp -s market,paper,feedback`, needs no credentials, and no tool in it can trade live or move funds.[^kr-01]

## What can an AI agent do at Kraken?

| Feature | Value | Sources |
|---|---|---|
| Read portfolio | Yes, with the `account` service: balances, orders, trade history, ledgers, positions and exports | [^kr-01] |
| Place orders | Yes, with the `trade` service (live spot orders) or the `futures` service. Each order needs your approval unless the gate is off | [^kr-01] |
| Order types | Market and limit are documented. `paper buy` defaults to a market order and `order buy` to a limit order; `--type` switches | [^kr-02] |
| Assets | Crypto spot, xStocks (tokenized equities), forex, perpetual futures, inverse and fixed-date futures, earn and staking | [^kr-02] |
| Move money | Yes, with the `funding` service (deposits, withdrawals and transfers), each call needing approval | [^kr-01] |
| [Paper trading](../glossary.md#paper-trading) | Yes. `paper` (spot) and `futures-paper` services run against live prices with no authentication | [^kr-01][^kr-02] |
| Limits (size, spend) | Position size limits and pair [allowlists](../glossary.md#allowlist) on the API key, set in Kraken's settings | [^kr-01] |
| Notifications | unknown | |

## How does Kraken's agent connection work?

- **No hosted endpoint:** kraken-mcp is a local process over stdio. It comes with the CLI install, which runs on macOS and Linux, and on Windows through WSL.[^kr-01][^kr-02]
- **Services:** `-s` chooses which command groups the server exposes. `market` (11 tools), `paper` (17), `futures-paper` (17) and `feedback` (1) need no key. `account` (18) is read-only apart from two export tools. `trade` (9), `futures` (39), `earn` (6), `funding` (10) and `subaccount` (2) are marked dangerous. `workspace` (20) holds paper and live workspaces, and `auth` (2) checks credentials. With no `-s` flag the server exposes market, account, paper, workspace and feedback.[^kr-01]
- **Feedback tool:** the `feedback` service uploads the text you give it to Kraken.[^kr-01]
- **Auth:** an API key and secret in [environment variables](../glossary.md#environment-variables) in the client's MCP configuration, or a key stored once from a terminal. `kraken auth login` signs in through the browser and saves a restricted spot [API key](../glossary.md#api-key) with no withdrawal rights that expires after 90 days by default; `--read-only` makes a key that cannot trade. You must run it yourself in a terminal; Kraken says a script or an AI agent cannot create a key. `kraken setup` stores a key you created under Settings → API.[^kr-01][^kr-02]
- **What stays in the CLI:** streams (WebSocket feeds, recording, replay), interactive commands, and the local credential commands `auth switch` and `auth reset` are not MCP tools.[^kr-01]

## What guardrails and risks apply at Kraken?

| Guardrail | Where it is enforced | Sources |
|---|---|---|
| Approval on every call to a dangerous tool (order placement, withdrawals, transfers, workspace promotion) | In the local server, through [MCP elicitation](../glossary.md#elicitation). Starting the server with `--allow-dangerous` turns it off | [^kr-01] |
| A client that cannot show an elicitation gets no prompt from the server: the call runs when the model sets `acknowledged: true` | Your AI client's own tool-approval setting is the only check | [^kr-01] |
| Choose services: the default set places no live orders and moves no funds | In the local server you start | [^kr-01] |
| Least-privilege API keys; position size limits and pair allowlists on the key | Server side (exchange), on the key | [^kr-01] |
| Sign-in key from `kraken auth login` has no withdrawal rights and expires | Server side (exchange) | [^kr-02] |
| Local only: do not expose, tunnel or share the server outside systems you control. Every connected agent uses the same Kraken account and key permissions | Your deployment | [^kr-01][^kr-03] |
| Promoting a paper workspace to live execution needs credentials and asks for confirmation | In the CLI | [^kr-02] |
| [Dead man's switch](../glossary.md#dead-mans-switch): `kraken order cancel-after 60` cancels all open orders if your process stops sending heartbeats | Set with the CLI; the docs do not say where the timer runs | [^kr-02] |
| Revoking an agent's access | unknown | |

The kraken CLI itself places orders without a confirmation prompt; the approval gate is in the MCP server.[^kr-03] Kraken's GitHub page also says to treat the MCP integration as alpha and to use least-privilege API keys.[^kr-03]

## How do you connect an agent to Kraken?

1. Install kraken-cli; kraken-mcp comes with it.[^kr-01]
2. Start with `kraken-mcp -s market,paper,feedback`, which needs no credentials.[^kr-01]
3. Add services only as your workflow needs them. Kraken says to scope services to the minimum.[^kr-01]
4. Before adding `trade`, create a least-privilege key and set position size limits and pair allowlists on it.[^kr-01]

## How do I connect Kraken from my AI app?

Every app runs the same local command. If an app reports "Failed to connect", it cannot find kraken-mcp on its PATH; set the command to the full path that `command -v kraken-mcp` prints.[^kr-01]

| App | How to connect | Sources |
|---|---|---|
| Claude Code | Install the plugin, which adds the server and the CLI's [agent skills](../glossary.md#agent-skill): `/plugin marketplace add krakenfx/kraken-cli`, then `/plugin install kraken-cli@kraken`. Or register only the server: `claude mcp add --scope user kraken -- kraken-mcp -s market,paper,feedback`. Check with `claude mcp list` | [^kr-01] |
| Claude Desktop | In `~/Library/Application Support/Claude/claude_desktop_config.json`, add a `kraken` server with command `kraken-mcp` and args `-s market,paper,feedback`, then restart Claude Desktop | [^kr-01] |
| Cursor | Add the same server entry to `~/.cursor/mcp.json` (global) or `.cursor/mcp.json` in your project, then reload the window | [^kr-01] |
| VS Code (Copilot) | Add a `stdio` server running `kraken-mcp -s market,paper,feedback` to `.vscode/mcp.json` in your workspace | [^kr-01] |
| Windsurf | Add the same server entry to `~/.codeium/windsurf/mcp_config.json`, then restart Windsurf | [^kr-01] |
| Gemini CLI | Install the extension: `gemini extensions install https://github.com/krakenfx/kraken-cli` | [^kr-01] |
| Other MCP clients | Use the same command and arguments: `kraken-mcp -s market,paper,feedback` | [^kr-01] |

The quickstart set has no live trading. To add it, Kraken's example is `-s market,paper,trade` with a least-privilege API key.[^kr-01]

## What is still unknown about Kraken?

- How to revoke an agent's access: unknown. The sign-in key expires on its own (90 days by default).[^kr-02]
- Countries where agent trading is available: unknown.
- Order types beyond market and limit through MCP: unknown.
- Notifications for agent trades: unknown.
- Agent terms of use: not yet reviewed here.

Every fact on this page links to a source card; "unknown" means no source we cite confirms it.

## What changed on this page?

- 2026-11-19: First version of this page.

## Sources

[^kr-01]: [MCP server - Kraken docs](../sources/kr-01.md). Kraken, official, retrieved 2026-11-19.
[^kr-02]: [kraken-cli - Kraken docs](../sources/kr-02.md). Kraken, official, retrieved 2026-11-19.
[^kr-03]: [GitHub - krakenfx/kraken-cli: Kraken CLI · GitHub](../sources/kr-03.md). Kraken (GitHub), official, retrieved 2026-11-19.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20providers%2Fkraken.md&body=Page%3A%20providers%2Fkraken.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
