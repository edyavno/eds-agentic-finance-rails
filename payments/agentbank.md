---
type: payment
id: agentbank
title: AgentBank
summary: An MCP server that lets an AI agent collect, hold, convert and send money, including to bank accounts in local currency, using crypto rails. The owner confirms every payment, and an approval threshold adds an extra check.
page_status: current
last_verified: '2026-11-19'
kind: payment-mcp
operator: AgentBank, operated by Thinking Horizon, Inc.
agent_can: Collect payments, convert between currencies and crypto assets, pay bank, QR or wallet recipients in local currency, and pay x402 services, through an MCP server
user_controls: The owner confirms the recipient, amounts, fees and expiry of every payment before it is created. An approval threshold sets when a payment needs an extra approval. ChatGPT and Claude connections can also have a spending limit, and the owner can disconnect an agent at any time
mcp_server: 'yes'
endpoint: https://mcp.useagentbank.com
availability: unknown
field_sources:
  operator:
  - ag-02
  agent_can:
  - ag-01
  user_controls:
  - ag-01
  - ag-02
  - ag-03
  - ag-07
  - ag-08
  mcp_server:
  - ag-01
  endpoint:
  - ag-01
---

# AgentBank

AgentBank is an [MCP](../glossary.md#mcp) server that lets an AI agent collect money, hold it, convert it and send it to bank accounts in local currency, within limits and approvals its owner sets.[^ag-01] It describes itself as crypto banking services for AI agents, not a bank.[^ag-03]

## How an agent connects

- **Remote MCP** at `https://mcp.useagentbank.com`, for hosted assistants. It uses [OAuth](../glossary.md#oauth) 2.1 with [PKCE](../glossary.md#pkce) and [Dynamic Client Registration](../glossary.md#dynamic-client-registration).[^ag-01]
- **Local MCP**, a [stdio](../glossary.md#stdio) server run with `npx`, for coding agents and desktop clients.[^ag-01]
- Agents do not open accounts themselves. Onboarding returns a browser link for the owner to approve.[^ag-01]
- Hosted connections expose balance, spending limit, payment, account reference and tracking tools, and show approval and progress cards in ChatGPT and Claude.[^ag-01]

## What an agent can do

- Collect money with one-time bank or QR instructions, and check whether it was paid.[^ag-01]
- Convert between supported currencies and crypto assets.[^ag-01]
- Pay a bank, QR or wallet recipient in local currency, and track the payment.[^ag-01]
- Pay [x402](../glossary.md#x402) services after the owner reviews the service, amount and payee.[^ag-01]

## What you control

AgentBank lists these controls.[^ag-02]

- **Payment confirmation.** The agent shows the recipient, amounts, fees and expiry, and you confirm before the payment is created.
- **Approval threshold.** Payments above it need an extra approval step. Several payments can be approved together as one payment plan.[^ag-03]
- **Spending limit.** On ChatGPT and Claude connections, a limit on the crypto funding you can choose to use for a confirmed payment.
- **Identity checks** decide which payment routes you can use.
- **Disconnect** an agent at any time.

How you disconnect depends on the connection.[^ag-07]

- **ChatGPT and Claude:** revoke the connection in AgentBank's connection settings, or remove the plugin or connector in the AI app's settings.
- **Local agents:** ask the agent to disconnect from AgentBank. After you confirm, that installation's access and wallet authorization stop working and its stored AgentBank credentials are cleared. Reconnecting needs a new browser authorization.
- **Lost device or unavailable agent:** manage access at app.useagentbank.com, or contact support.
- Revoking stops that agent's access. It does not cancel or refund a payment already funded.

You view or change an agent's payment-approval threshold at app.useagentbank.com. The threshold helps decide which payments can go ahead without an extra World ID step, and AgentBank may still ask for approval under the payment and account policy. Local MCP connections can also ask the agent to read or change the threshold, with the proposed change shown before it is applied; AgentBank says not to assume these tools exist in ChatGPT or Claude. Changing the threshold does not replace payment review, verification or a separate wallet-funding confirmation.[^ag-08]

Signing in does not approve every payment, and approving a payment does not automatically fund it.[^ag-02]

## How do I connect AgentBank from my AI app?

AgentBank's developer page lists ChatGPT, Claude, Meta Muse, Poke, Cursor, Grok, Gemini CLI and any host that calls an HTTPS MCP server for the remote server, and Codex, Claude Code, Claude Desktop, OpenClaw and Hermes for the local one.[^ag-01] Its docs give these steps:

| App | How to connect | Sources |
|---|---|---|
| ChatGPT (remote) | Turn on Developer mode in Settings → Security and login (availability depends on your account and workspace policy). In ChatGPT Plugins, select +, name it AgentBank, enter `https://mcp.useagentbank.com` under Connection and create it. Sign in to AgentBank in the browser, then add AgentBank from the tools menu in a new chat and check the connected account is yours | [^ag-05] |
| Claude (remote) | Open Customize → Connectors, select +, then Add custom connector. Name it AgentBank, enter `https://mcp.useagentbank.com`, select Add, then Connect and sign in. Claude supports remote connectors on Free, Pro, Max, Team and Enterprise; Free accounts are limited to one custom connector. On Team and Enterprise, an owner adds AgentBank in Organization settings first, and each member connects their own AgentBank account | [^ag-06] |
| Codex (local) | Run `codex mcp add agentbank -- npx -y agent-bank-mcp@latest` | [^ag-04] |
| Claude Code (local) | Run `claude mcp add agentbank -- npx -y agent-bank-mcp@latest` | [^ag-04] |
| Claude Desktop (local) | Add an `agentbank` server running `npx -y agent-bank-mcp@latest` to `claude_desktop_config.json`, then fully quit and reopen Claude Desktop | [^ag-04] |
| OpenClaw (local) | Add the server under `mcp.servers` in `~/.openclaw/openclaw.json`, then check it with `openclaw mcp doctor agentbank --probe` | [^ag-04] |
| Hermes (local) | Run `hermes mcp add agentbank --command npx --args -y agent-bank-mcp@latest`, then `/reload-mcp` | [^ag-04] |

For a remote connection, use the URL exactly, without adding `/mcp`.[^ag-05][^ag-06] For a local agent, restart the app and ask it to connect to your AgentBank account without creating a payment, then open the link it gives you and finish the account and wallet authorization in your browser. AgentBank says not to paste wallet keys, sign-in tokens or World ID proofs into chat.[^ag-04]

## Who runs it

AgentBank says it is operated by Thinking Horizon, Inc., a Delaware corporation registered with FinCEN as a Money Services Business. It says it does not take custody of wallet funds; Privy provides the wallet infrastructure.[^ag-02]

## Unknown

Which countries and currencies are live for a given user, fees, and its stage of availability. No cited source confirms it, so the wiki says unknown.

The approval threshold amounts are also unknown.

All programs: [Payments](README.md).

## Sources

[^ag-01]: [Connect your AI agent to real-world money - AgentBank](../sources/ag-01.md). AgentBank, official, retrieved 2026-11-19.
[^ag-03]: [AgentBank FAQ: banking for AI agents - AgentBank](../sources/ag-03.md). AgentBank, official, retrieved 2026-11-15.
[^ag-02]: [Security and wallet control - AgentBank](../sources/ag-02.md). AgentBank, official, retrieved 2026-11-15.
[^ag-07]: [Account revocation - AgentBank docs](../sources/ag-07.md). AgentBank, official, retrieved 2026-11-19.
[^ag-08]: [Configure thresholds - AgentBank docs](../sources/ag-08.md). AgentBank, official, retrieved 2026-11-19.
[^ag-05]: [Connect ChatGPT - AgentBank docs](../sources/ag-05.md). AgentBank, official, retrieved 2026-11-19.
[^ag-06]: [Connect Claude - AgentBank docs](../sources/ag-06.md). AgentBank, official, retrieved 2026-11-19.
[^ag-04]: [Connect your agent - AgentBank docs](../sources/ag-04.md). AgentBank, official, retrieved 2026-11-19.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20payments%2Fagentbank.md&body=Page%3A%20payments%2Fagentbank.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
