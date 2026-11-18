---
type: provider
id: coinbase
title: Coinbase
summary: 'Coinbase for Agents: a remote MCP with OAuth for allowlisted clients, or a local CLI with an API key. Coinbase enforces trade limits, and a dedicated portfolio is optional.'
provider: Coinbase
page_status: current
last_verified: '2026-11-18'
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
limits: 'Maximum trade size in USD, a 24-hour volume limit and an auto-stop after a set percentage loss, set in the Coinbase app or on the web and enforced by Coinbase. Amounts are chosen by each user'
notifications: unknown
notes: The dedicated portfolio is optional; the main account can also be used. Isolated agent portfolios are spot-crypto only. Per-order confirmation depends on the AI client and, in ChatGPT, on which Coinbase connection you use.
field_sources:
  status: [cb-01, cb-07]
  can_place_orders: [cb-01]
  approval_model: [cb-01, cb-03, cb-07]
  assets: [cb-01]
  auth: [cb-01, cb-04]
  endpoint: [cb-01, cb-04]
  transport: [cb-01]
  reads_portfolio: [cb-01]
  limits: [cb-10]
---

# Coinbase

## Can an AI agent trade at Coinbase?

Yes. Coinbase for Agents connects AI apps to a Coinbase account for crypto, equities and derivatives trading, portfolio management and [x402](../glossary.md#x402) payments.[^cb-01] It launched on 2026-06-11 with an [MCP](../glossary.md#mcp) server and a [CLI](../glossary.md#cli). At launch, crypto spot and derivatives were enabled and stocks were described as coming.[^cb-07] The current docs list eligible US stocks.[^cb-01]

There are two ways in: a remote MCP server at `https://agents.coinbase.com/mcp` using [OAuth](../glossary.md#oauth), and a local CLI that uses a CDP [API key](../glossary.md#api-key).[^cb-01]

The CDP CLI/MCP for the developer platform is a separate product for wallets and payments, not consumer account access.[^cb-05]

## What can an AI agent do at Coinbase?

| Feature | Value | Sources |
|---|---|---|
| Read portfolio | Yes | [^cb-01] |
| Place orders | Yes, with a known limitation on some hosted clients (see below) | [^cb-01] |
| Order types | unknown | |
| Assets | Crypto spot, US derivatives (futures), eligible US equities | [^cb-01] |
| Payments | x402 payments for premium data from a USDC balance | [^cb-01] |
| Limits (size, spend) | Maximum trade size in USD, a 24-hour volume limit and an auto-stop after a set percentage loss, enforced by Coinbase. Trade-size and spend rules were announced as coming soon at launch | [^cb-10][^cb-07] |
| Notifications | unknown | |
| Paper or sandbox | unknown | |

## How does Coinbase's agent connection work?

- **Endpoint:** `https://agents.coinbase.com/mcp`, for example `claude mcp add coinbase --transport http https://agents.coinbase.com/mcp`.[^cb-01]
- **Auth:** OAuth with `login.coinbase.com` as the authorization server.[^cb-04] [Dynamic Client Registration](../glossary.md#dynamic-client-registration) and [Client ID Metadata Documents](../glossary.md#client-id-metadata-documents) are supported, but Coinbase still [allowlists](../glossary.md#allowlist) clients.[^cb-01]
- **[Scopes](../glossary.md#scopes) advertised:** include `mcp:orders:create`, `mcp:trades:create`, `mcp:transfers:create` and `mcp:portfolios:update`.[^cb-04]
- **Account boundary:** you choose which portfolios the agent can reach on the OAuth approval screen.[^cb-03] Isolated agent portfolios are spot crypto only; US derivatives work only in the default portfolio.[^cb-01]
- **CLI:** runs locally with a CDP API key; Coinbase calls it the most reliable way to execute trades across models.[^cb-01]
- **Agent feedback:** official docs have a Send feedback section. They say you or your agent can send feedback about the Coinbase MCP through the `coinbase_feedback_submit` tool, that the team reads submitted feedback every day, that feedback is limited to 2,000 characters or less, and that each user can send up to 6 submissions per day. A tool table on the same page also says submissions are screened. The official docs describe this MCP tool and a local CLI command `coinbase feedback`; they do not document an HTTP path named `/feedback`.[^cb-09]

## What guardrails and risks apply at Coinbase?

| Guardrail | Where it is enforced | Sources |
|---|---|---|
| Dedicated portfolio chosen at sign-in | Server side (broker), optional | [^cb-03][^cb-07] |
| Main account access is also allowed | | [^cb-07] |
| Client allowlisting, including DCR clients | Server side (broker) | [^cb-01] |
| Maximum trade size and 24-hour volume limit | Server side (broker). Announced as "soon" at launch;[^cb-07] documented as available on 2026-11-11 | [^cb-10][^cb-07] |
| Auto-stop after a set percentage portfolio loss | Server side (broker). The agent stops placing trades until you turn trading back on in the Coinbase app | [^cb-10] |
| Product permissions (crypto, equities, derivatives) | Marked "coming soon" by Coinbase, so not available yet | [^cb-10] |
| Per-order confirmation | Client side. Coinbase documents that Claude previews and asks to confirm, while ChatGPT creates the order in one turn.[^cb-01] The official Coinbase plugin for ChatGPT shows Coinbase confirmation cards instead, and the custom MCP connection trades without per-trade approval | [^cb-09] |
| KYT transaction monitoring on payments | Server side (broker) | [^cb-07] |

The advertised scopes include transfers, so check which tools your client exposes before connecting a funded account.[^cb-04]

## What are Coinbase's Agent Controls?

Agent Controls are limits you set in the Coinbase app or on the web, from your logged-in account. They run on Coinbase's servers, not inside your agent, so the agent cannot bypass or change them.[^cb-10]

- **Maximum trade size:** a limit in USD for each trade.[^cb-10]
- **24-hour volume limit:** a cap on the total the agent can trade over 24 hours. A trade that would exceed it does not go through.[^cb-10]
- **Auto-stop:** a percentage-loss threshold for a portfolio. If the portfolio falls below it, the agent stops placing trades until you turn trading back on in the Coinbase app.[^cb-10]
- **Product permissions:** a choice of which product categories the agent can trade, such as crypto, equities and derivatives. Coinbase marks this "coming soon".[^cb-10]

Coinbase's post does not say whether auto-stop cancels open orders, so that is unknown.[^cb-10]

## What does the official ChatGPT plugin change?

Coinbase now offers an official plugin for ChatGPT, available to US Coinbase users. Coinbase confirmation cards cover placing, editing and cancelling orders and USD–USDC conversions. Read-only requests do not use cards, and ChatGPT's own tool permissions are separate.[^cb-09]

Coinbase says a custom MCP connection is the option for automated trading without approving each trade, and the only option that supports x402 and Global Derivatives. The ChatGPT trading integration does not expose x402 tools.[^cb-09]

## How do you connect an agent to Coinbase?

1. Create and fund a dedicated portfolio with only what the agent may use, then pick only that portfolio on the approval screen.[^cb-03]
2. Add the remote MCP in your client, or use the CLI with a CDP API key for terminal agents.[^cb-01]
3. If your agent only previews orders on a hosted client, ask it to execute explicitly or use the CLI, as Coinbase suggests.[^cb-01]
4. Set Agent Controls in the Coinbase app or on the web before you let the agent trade.[^cb-10]

Coinbase publishes an agent-readable [llms.txt](../glossary.md#llmstxt) at `https://docs.cdp.coinbase.com/llms.txt`, which lists Coinbase for Agents materials.[^cb-06]

See [Connect an MCP client](../build/connect-an-mcp-client.md).

## What is still unknown about Coinbase?

- Order types: unknown.
- Whether auto-stop cancels open orders, and when product permissions arrive: unknown.[^cb-10]
- [Paper trading](../glossary.md#paper-trading) for the consumer agent product: unknown. A news report's "separate sandbox" describes running the agent outside the main account, which reads like the isolated portfolio rather than paper trading.[^cb-08]
- Agent terms of use: not yet reviewed here.

Every fact on this page links to a source card; "unknown" means no source we cite confirms it.

## What changed on this page?

- 2026-11-18: Added Coinbase's Agent Controls (trade size, 24-hour volume, auto-stop) and the official ChatGPT plugin's confirmation cards.[^cb-10][^cb-09]
- 2026-11-14: Cited the official CDP docs llms.txt index.[^cb-06]
- 2026-11-13: Added the official `coinbase_feedback_submit` feedback tool, from Coinbase MCP docs.[^cb-09]
- 2026-11-12: First version of this page.

## Sources

[^cb-01]: [Coinbase MCP - Coinbase Developer Documentation](../sources/cb-01.md). Coinbase Developer Platform, official, retrieved 2026-11-12.
[^cb-07]: [Coinbase for Agents: Your AI Agent Can Now Trade and Pay with Coinbase](../sources/cb-07.md). Coinbase, official, retrieved 2026-11-12.
[^cb-05]: [CDP MCP - Coinbase Developer Documentation](../sources/cb-05.md). Coinbase Developer Platform, official, retrieved 2026-11-12.
[^cb-10]: [Coinbase for Agents introduces new Agent Controls](../sources/cb-10.md). Coinbase, official, retrieved 2026-11-18.
[^cb-04]: [Coinbase for Agents MCP: OAuth protected-resource metadata](../sources/cb-04.md). Coinbase (endpoint metadata), official, retrieved 2026-11-12.
[^cb-03]: [Coinbase for Agents setup skill (skill.md)](../sources/cb-03.md). Coinbase Developer Platform, official, retrieved 2026-11-12.
[^cb-09]: [Coinbase MCP - Coinbase Developer Documentation](../sources/cb-09.md). Coinbase Developer Platform, official, retrieved 2026-11-18.
[^cb-06]: [Coinbase Developer Platform docs llms.txt](../sources/cb-06.md). Coinbase Developer Platform, official, retrieved 2026-11-12.
[^cb-08]: [Coinbase’s new tool can help agents trade and pay for premium research - TechCrunch](../sources/cb-08.md). TechCrunch, third-party, retrieved 2026-11-12.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20providers%2Fcoinbase.md&body=Page%3A%20providers%2Fcoinbase.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
