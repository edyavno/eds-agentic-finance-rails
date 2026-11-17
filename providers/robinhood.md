---
type: provider
id: robinhood
title: Robinhood
summary: Remote Trading MCP with OAuth. Agents read all Robinhood accounts but trade only in a dedicated agentic (MCP) account; per-order approval is an optional toggle.
provider: Robinhood
page_status: current
last_verified: '2026-11-14'
status: official-mcp
can_place_orders: ['yes']
approval_model: [separate-account, per-order-confirm]
assets: [long equities, options (single-leg only), 'crypto (not in some states, including New York)']
order_types: [market (share-based), market (dollar-based), limit, stop limit, stop market]
auth: OAuth to the remote MCP server; protected-resource metadata lists the scope "internal"; an independent test reports PKCE and dynamic client registration
endpoint: https://agent.robinhood.com/mcp/trading
transport: [remote-http]
reads_portfolio: 'yes'
paper_trading: unknown
limits: unknown
notifications: Push notification whenever the agent makes a trade, plus a real-time activity feed and P&L in the app
notes: Trade approvals are off by default for MCP accounts and still rolling out. Built-in Robinhood Agents are a separate product.
field_sources:
  status: [rh-01, rh-10, rh-13]
  can_place_orders: [rh-01, rh-04]
  approval_model: [rh-01, rh-04, rh-10]
  assets: [rh-04]
  order_types: [rh-04]
  auth: [rh-13, rh-02]
  endpoint: [rh-01, rh-13]
  transport: [rh-01]
  reads_portfolio: [rh-01]
  notifications: [rh-10]
---

# Robinhood

## Can an AI agent trade at Robinhood?

Yes, in a separate agentic account. Robinhood runs an official remote Trading [MCP](../glossary.md#mcp) server for outside agents at `https://agent.robinhood.com/mcp/trading`.[^rh-01][^rh-13]

Robinhood announced Agentic Trading on 2026-05-27 as a beta that supported equities only at launch.[^rh-10] The current support pages list long equities, options and crypto.[^rh-04]

An external agent gets read access to all of your Robinhood accounts, including account numbers, positions, balances and order history, but it can only place trades in your Robinhood Agentic account.[^rh-01] The agentic account is separate from the rest of your portfolio, so the agent can only use the money you deposit into it.[^rh-10]

Robinhood also offers built-in Robinhood Agents, provided by Robinhood Labs, LLC, which says it is not a broker-dealer.[^rh-07] This page covers outside agents connecting through MCP.

The official Robinhood Agents product page describes Agent Apps, which connect an agent to additional data and tools, and Agent Loops, which that page marks as coming soon; it also repeats the dedicated-account control.[^rh-05]

A support article says Agent Apps are only available in the Robinhood mobile app, and only accessible by agents hosted by Robinhood.[^rh-12] Another support article covers setting up a built-in agent in the mobile app.[^rh-08]

TechCrunch's launch coverage on 2026-05-27 described a dedicated pre-loaded balance and reported that options, crypto, event contracts, futures, and prediction markets were planned at the time; treat current assets as the official support pages above.[^rh-11]

## What can an AI agent do at Robinhood?

| Feature | Value | Sources |
|---|---|---|
| Read portfolio | Yes. All accounts, positions, balances and transactions | [^rh-01] |
| Place orders | Yes, in the agentic (MCP) account only | [^rh-01][^rh-04] |
| Order types | Market (share-based and dollar-based), limit, stop limit, stop market | [^rh-04] |
| Assets | Long equities, single-leg options, crypto | [^rh-04] |
| Multi-leg options | No, not through an agent | [^rh-04] |
| Crypto transfers, staking, lending | No. The agent can trade crypto but not move, stake or lend it | [^rh-04] |
| Limits (size, rate) | unknown | |
| Notifications | Push notification on every agent trade, activity feed, P&L | [^rh-10] |
| Paper or sandbox | unknown | |

## How does Robinhood's agent connection work?

- **Endpoint:** `https://agent.robinhood.com/mcp/trading`, added as a remote HTTP MCP server, for example `claude mcp add robinhood-trading --transport http https://agent.robinhood.com/mcp/trading`.[^rh-01]
- **Auth:** [OAuth](../glossary.md#oauth). The [protected-resource metadata](../glossary.md#protected-resource-metadata) names the same URL as resource and authorization server, uses [bearer tokens](../glossary.md#bearer-token) in the header, and lists one [scope](../glossary.md#scopes), `internal`.[^rh-13] An independent test on 2026-09-05 reported OAuth 2.0 with [PKCE](../glossary.md#pkce), [dynamic client registration](../glossary.md#dynamic-client-registration), and 73 tools on that date.[^rh-02]
- **Tool list:** Robinhood publishes tool tables per category, including trade-approval tools such as `get_trade_approvals` and `decline_trade_approval`.[^rh-04]
- **Account boundary:** read access spans all accounts; trading is limited to the agentic account.[^rh-01]

## What guardrails and risks apply at Robinhood?

| Guardrail | Where it is enforced | Sources |
|---|---|---|
| Trading only in the agentic account | Server side (broker) | [^rh-01][^rh-10] |
| Trade approvals toggle: when on, the agent proposes and you place each order in the app | Server side (broker), optional | [^rh-04] |
| Trade approvals are **off by default** for MCP accounts and still rolling out | | [^rh-04] |
| Some trades may still need your approval with approvals off | Server side (broker) | [^rh-04] |
| Disconnect the agent at any time | Server side (broker) | [^rh-10] |

Robinhood warns that if you tell your agent to act without asking you, it can place trades without your confirmation.[^rh-01] Because the agent can read every account, treat account numbers and balances it sees as sensitive inside your agent's logs.

## How do you connect an agent to Robinhood?

1. Open a Robinhood Agentic (MCP) account and fund it only with what the agent may use.[^rh-10]
2. Add the MCP server in your client (Claude Code, Codex and others are documented) and complete OAuth.[^rh-01]
3. Decide whether to turn on Trade approvals before the first order.[^rh-04]
4. For your own client: discover OAuth metadata from `/.well-known/oauth-protected-resource`, then use bearer tokens.[^rh-13]

Robinhood also publishes a machine-readable [llms.txt](../glossary.md#llmstxt) at `https://robinhood.com/llms.txt`.[^rh-06]

See [Connect an MCP client](../build/connect-an-mcp-client.md) and [Human-in-the-loop patterns](../build/human-in-the-loop.md).

## What is still unknown about Robinhood?

- [Paper trading](../glossary.md#paper-trading) or [sandbox](../glossary.md#sandbox) for agents: unknown.
- Order size and rate limits: unknown.
- The agentic account agreement and disclosure text: not yet reviewed here.

Every fact on this page links to a source card; "unknown" means no source we cite confirms it.

## What changed on this page?

- 2026-11-14: Added official product and support pages on built-in Agents, Agent Apps and Agent Loops, plus TechCrunch launch coverage and the site llms.txt index.[^rh-05][^rh-08][^rh-12][^rh-11][^rh-06]
- 2026-11-12: First version of this page.

## Sources

[^rh-01]: [Onboarding an external agent - Robinhood](../sources/rh-01.md). Robinhood, official, retrieved 2026-11-12.
[^rh-13]: [Robinhood Trading MCP: OAuth protected-resource metadata](../sources/rh-13.md). Robinhood (endpoint metadata), official, retrieved 2026-11-12.
[^rh-10]: [Robinhood is Now Open to Agents](../sources/rh-10.md). Robinhood, official, retrieved 2026-11-12.
[^rh-04]: [Trading with your agent - Robinhood](../sources/rh-04.md). Robinhood, official, retrieved 2026-11-12.
[^rh-07]: [Robinhood Agents overview - Robinhood](../sources/rh-07.md). Robinhood, official, retrieved 2026-11-12.
[^rh-05]: [Robinhood Agents - Build Your AI Trading Agent](../sources/rh-05.md). Robinhood, official, retrieved 2026-11-12.
[^rh-12]: [Agent apps - Robinhood](../sources/rh-12.md). Robinhood, official, retrieved 2026-11-12.
[^rh-08]: [Setting up an agent - Robinhood](../sources/rh-08.md). Robinhood, official, retrieved 2026-11-12.
[^rh-11]: [Robinhood now lets your AI agents trade stocks - TechCrunch](../sources/rh-11.md). TechCrunch, third-party, retrieved 2026-11-12.
[^rh-02]: [Robinhood MCP Server: What 73 Tools and an OAuth Handshake Look Like Up Close — DeskTested](../sources/rh-02.md). DeskTested, third-party, retrieved 2026-11-12.
[^rh-06]: [robinhood.com llms.txt](../sources/rh-06.md). Robinhood, official, retrieved 2026-11-12.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20providers%2Frobinhood.md&body=Page%3A%20providers%2Frobinhood.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
