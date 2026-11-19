---
type: provider
id: public
title: Public
summary: 'Public runs a hosted MCP server at mcp.public.com/mcp for Claude, ChatGPT, Codex, Meta Muse, Perplexity and Grok. Most apps sign in with OAuth; Muse uses a Public API key. Every trade is a real order, with no paper mode.'
provider: Public.com
page_status: current
last_verified: '2026-11-19'
status: official-mcp
can_place_orders: ['yes']
approval_model: [separate-account, per-order-confirm]
assets: [US-listed stocks and ETFs, options, crypto, bonds, prediction markets]
order_types: unknown
auth: OAuth for Claude, ChatGPT, Codex, Perplexity and Grok; a Public API key as the bearer token for Meta Muse and for the Public Agent Skill
endpoint: https://mcp.public.com/mcp
transport: [remote-http, cli]
reads_portfolio: 'yes'
paper_trading: 'no'
limits: 'Hosted server: unknown. Self-hosted server release 0.11.0: optional per-order quantity and value limits set in environment variables, off by default'
notifications: Trade confirmations in real time, per Public's MCP page
notes: approval_model lists the hosted server first (dedicated accounts are optional), then the self-hosted server from release 0.11.0, which asks you to confirm each order. Whether the hosted server confirms each order is unknown. The Claude directory connector cannot place trades; a custom connector can.
field_sources:
  status: [pu-01, pu-02]
  can_place_orders: [pu-01, pu-02]
  approval_model: [pu-01, pu-11]
  assets: [pu-01]
  auth: [pu-02, pu-13, pu-14]
  endpoint: [pu-02]
  transport: [pu-02, pu-16]
  reads_portfolio: [pu-09, pu-14]
  paper_trading: [pu-06]
  limits: [pu-11]
  notifications: [pu-01]
---

# Public

## Can an AI agent trade at Public?

Yes. Public runs a hosted [MCP](../glossary.md#mcp) server that connects a Public.com brokerage account to Claude, ChatGPT, Codex, Meta Muse, Perplexity and Grok.[^pu-02] Placing a trade through any of these apps is a real order using real money in your Public account.[^pu-02] All orders are live; there is no [paper trading](../glossary.md#paper-trading) mode.[^pu-06]

Public's MCP disclosures say that connecting a third-party AI agent authorizes it to view your account data and place trades on your behalf, that trades may be executed without your direct input on each transaction, and that trades submitted through the MCP server are deemed authorized by you.[^pu-01]

The FAQ on Public's MCP page says it works with Claude, Perplexity and ChatGPT today and can support other MCP-compatible assistants as they adopt the standard.[^pu-01] Public's setup guides also cover Codex, Meta Muse and Grok.[^pu-02]

## What can an AI agent do at Public?

| Feature | Value | Sources |
|---|---|---|
| Read portfolio | Yes. Balances, positions, quotes, option chains, open orders and transaction history | [^pu-09] |
| Place orders | Yes. Run [preflight](../glossary.md#preflight) checks, then submit or cancel orders | [^pu-09] |
| Order types | Not listed for the hosted MCP; the app guides say "supported order types". Public's API guides cover equity, single-leg and multi-leg options, bracket, bond, short and prediction-market orders | [^pu-09][^pu-16] |
| Assets | US-listed stocks and ETFs, options, crypto and bonds, limited to US securities markets. Public's MCP page also lists prediction markets | [^pu-01] |
| Market data | Live during trading hours, from the same data feeds as your Public account | [^pu-01] |
| Limits (size, spend) | Hosted server: unknown. Self-hosted server 0.11.0: optional per-order quantity and value limits | [^pu-11] |
| Notifications | Trade confirmations in real time | [^pu-01] |
| Paper or sandbox | No. All orders are live | [^pu-06] |

## How does Public's agent connection work?

- **Endpoint:** `https://mcp.public.com/mcp`. You need a Public.com brokerage account and an account with the AI app you connect.[^pu-02]
- **Auth:** [OAuth](../glossary.md#oauth) for Claude, ChatGPT, Codex, Perplexity and Grok. Meta Muse uses a Public [API key](../glossary.md#api-key) instead of OAuth, and Grok can also use the Public Agent Skill with an API key.[^pu-02] The OAuth metadata lists the [scopes](../glossary.md#scopes) `trading.read`, `trading.write`, `marketdata` and `openid`.[^pu-05]
- **Account boundary:** an app uses the accounts and trading permissions you authorize when you connect, and options strategies require the appropriate approval level.[^pu-09] Public offers dedicated brokerage accounts for automated strategies, MCP connections and AI trading workflows.[^pu-01]
- **Cost:** access to the MCP endpoint is included with your Public brokerage account at no extra cost; standard trading fees may apply.[^pu-01]
- **Other ways in:** Public also documents a CLI, and [agent skills](../glossary.md#agent-skill) for OpenClaw and Perplexity Computer.[^pu-16] Its official GitHub repository, `publicdotcom-mcp-server`, is a self-hosted MCP server with tools including `place_order` and `preflight_order`; release 0.1.0 on 2026-03-11 was its "initial release of the Official Public API MCP Server".[^pu-04][^pu-08]
- **Self-hosted release 0.11.0:** on 2026-11-17 the self-hosted server added an order gate: optional per-order quantity and value limits, a preflight of the exact order, and user confirmation through [MCP elicitation](../glossary.md#elicitation).[^pu-10][^pu-11] See [Per-order confirm](../approval-models/per-order-confirm.md).
- **Changelog and index:** an official changelog entry covers Grok MCP connector setup with OAuth,[^pu-03] and Public publishes a site-wide [llms.txt](../glossary.md#llmstxt) index.[^pu-07]

## What guardrails and risks apply at Public?

| Guardrail | Where it is enforced | Sources |
|---|---|---|
| Dedicated brokerage accounts for MCP connections | Server side (broker), optional | [^pu-01] |
| Accounts and trading permissions you authorize when connecting; options need the right approval level | Server side (broker) | [^pu-09] |
| Preflight details to review before you confirm a trade | Documented as a user step; who enforces it on the hosted server is unknown | [^pu-02][^pu-06] |
| ChatGPT can require extra approval before write actions such as placing orders | Client side (ChatGPT default) | [^pu-12] |
| Claude's directory connector cannot place trades, including from Claude Code | Client side (Claude); a custom connector is needed to trade | [^pu-09] |
| Muse setup message asks Muse to use the key only for that session and never trade without your explicit confirmation | Prompt text, not a server control | [^pu-14] |
| API keys: treat the key like a password and never share it publicly | Documented advice | [^pu-13][^pu-14] |
| Self-hosted server 0.11.0: limits, preflight and confirmation on every order | In the server you run | [^pu-11] |
| Revoking an agent's access | unknown | |

## How do I connect Public from my AI app?

Public's docs give step-by-step setup for each app.[^pu-02] Before you start, you need a Public.com brokerage account.[^pu-02]

| App | How to connect | Sources |
|---|---|---|
| Claude | Go to Customize → Connectors, click + Add, choose Add custom connector and name it. Paste `https://mcp.public.com/mcp` as the Remote MCP server URL, click Add, then Connect and authorize in your browser. The Public connector in Claude's directory cannot place trades, so use the custom connector to trade. On iOS, adding connectors is in beta; a custom connector added on web or desktop appears in the iOS app the next time you sign in | [^pu-09] |
| Claude Code | First add Public as a custom connector in claude.ai or Claude Desktop and sign in. Then start `claude`, type `/mcp`, select Public, and choose Connect if it shows as not authenticated | [^pu-09] |
| ChatGPT | Click Plugins, go to Browse Directory, click Add, then Add custom MCP server. Name it Public MCP, enter `https://mcp.public.com/mcp`, select OAuth, check the server's risk box, click Create and authenticate. You may need to adjust the connector's permissions to place trades | [^pu-12] |
| Codex | Run `codex mcp add public --url https://mcp.public.com/mcp`, then `codex mcp login public` and follow the OAuth flow in your browser | [^pu-12] |
| Meta Muse | Send Muse Public's setup message, which points it at `https://mcp.public.com/mcp` with your Public API key as the bearer token. Create the key in your Public API settings, give it to Muse when prompted, then ask Muse to list your Public.com accounts | [^pu-14] |
| Perplexity | Select Plugins in the sidebar and search for Public (or go to Customize → Connectors), open the Public connector, click Connect and follow the sign-in flow. Perplexity Computer has a separate Agent Skill guide | [^pu-15] |
| Grok | Two options. MCP: open grok.com/connectors (or Plugins → Connectors → New Connector → Custom), name it Public, enter the server URL and sign in with OAuth. Agent Skill: download the Public Agent Skill ZIP, upload it at grok.com/skills, then create an API key and paste it into your first message to Grok | [^pu-13] |

## What is still unknown about Public?

- How to revoke an app's access to the hosted MCP: unknown.
- Whether the hosted server confirms each order or enforces limits the way self-hosted release 0.11.0 does: unknown.[^pu-11]
- Order types accepted through the hosted MCP: unknown.
- Agent terms of use: not yet reviewed here.

Every fact on this page links to a source card; "unknown" means no source we cite confirms it.

## What changed on this page?

- 2026-11-19: First version of this page.

## Sources

[^pu-02]: [Connect the Public Hosted MCP Server to Claude, ChatGPT, Codex, Muse, Perplexity, and Grok - AI Trading Setup](../sources/pu-02.md). Public.com API docs, official, retrieved 2026-11-19.
[^pu-06]: [How to Trade Stocks, Options & Crypto Using Claude](../sources/pu-06.md). Public.com, official, retrieved 2026-11-12.
[^pu-01]: [Public MCP Server for trading on AI platforms](../sources/pu-01.md). Public.com, official, retrieved 2026-11-19.
[^pu-09]: [Claude & Claude Code Connector for Stock & Options Trading on Public MCP](../sources/pu-09.md). Public.com API docs, official, retrieved 2026-11-19.
[^pu-16]: [Guides (Public.com API docs index)](../sources/pu-16.md). Public.com API docs, official, retrieved 2026-11-19.
[^pu-11]: [Enforce preflight and user confirmation on every order — 0.11.0 (pull request 19)](../sources/pu-11.md). Public.com (GitHub), official, retrieved 2026-11-18.
[^pu-05]: [Public MCP: OAuth protected-resource metadata](../sources/pu-05.md). Public.com (endpoint metadata), official, retrieved 2026-11-12.
[^pu-04]: [GitHub - PublicDotCom/publicdotcom-mcp-server · GitHub](../sources/pu-04.md). Public.com (GitHub), official, retrieved 2026-11-12.
[^pu-08]: [Release 0.1.0 · PublicDotCom/publicdotcom-mcp-server · GitHub](../sources/pu-08.md). Public.com (GitHub), official, retrieved 2026-11-12.
[^pu-10]: [Release v0.11.0 · PublicDotCom/publicdotcom-mcp-server](../sources/pu-10.md). Public.com (GitHub), official, retrieved 2026-11-18.
[^pu-03]: [Public Trading API Changelog - Latest Updates & Release Notes](../sources/pu-03.md). Public.com API docs, official, retrieved 2026-11-12.
[^pu-07]: [public.com llms.txt](../sources/pu-07.md). Public.com, official, retrieved 2026-11-12.
[^pu-12]: [ChatGPT & Codex Connector for Stock & Options Trading on Public MCP](../sources/pu-12.md). Public.com API docs, official, retrieved 2026-11-19.
[^pu-14]: [Meta Muse Connector for Stock & Options Trading on Public MCP](../sources/pu-14.md). Public.com API docs, official, retrieved 2026-11-19.
[^pu-13]: [Grok Connector for Stock & Options Trading on Public MCP](../sources/pu-13.md). Public.com API docs, official, retrieved 2026-11-19.
[^pu-15]: [Perplexity Connector for Stock & Options Trading on Public MCP](../sources/pu-15.md). Public.com API docs, official, retrieved 2026-11-19.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20providers%2Fpublic.md&body=Page%3A%20providers%2Fpublic.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
