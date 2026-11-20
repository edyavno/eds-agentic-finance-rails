---
type: payment
id: stripe
title: Stripe
summary: Stripe offers shared payment tokens, which give a seller scoped, time-limited use of a customer's payment method for agent purchases, plus an official MCP server at mcp.stripe.com.
page_status: current
last_verified: '2026-11-20'
kind: payment-credential
operator: Stripe
agent_can: Grant a seller a shared payment token for a purchase. Separately, call the Stripe API and search Stripe's docs through the Stripe MCP server
user_controls: Each token has usage and expiry limits, such as currency, maximum amount and an expiry window. MCP access is granted on Stripe's OAuth consent page and can be revoked, and Stripe can require you to approve certain MCP actions in the Dashboard
mcp_server: 'yes'
endpoint: https://mcp.stripe.com
availability: Shared payment tokens are in public preview in the US, Canada and select European countries
field_sources:
  operator:
  - pm-08
  - pm-09
  agent_can:
  - pm-08
  - pm-09
  user_controls:
  - pm-08
  - pm-09
  mcp_server:
  - pm-09
  endpoint:
  - pm-09
  availability:
  - pm-08
---

# Stripe

Stripe has two agent pieces in the cited sources: shared payment tokens for agent purchases, and an official [MCP](../glossary.md#mcp) server. Stripe also co-maintains [ACP](agentic-commerce-protocol.md).[^pm-07]

## Shared payment tokens

- A shared payment token (SPT) gives a seller scoped access to a customer's payment method for a purchase an agent starts.[^pm-08] See [payment token](../glossary.md#payment-token).
- The agent grants the token to the seller's Stripe profile. Each token has usage and expiry limits.[^pm-08]
- In a [sandbox](../glossary.md#sandbox), a test helper simulates limits an agent might set, such as currency, maximum amount and expiry window.[^pm-08]
- SPTs are in public preview, for agents, customers and sellers in the US, Canada and select European countries.[^pm-08]

## Stripe MCP server

- The server gives AI agents tools to use the Stripe API and search Stripe's docs and support articles.[^pm-09]
- Address: `https://mcp.stripe.com`.[^pm-09]
- Sign-in: [OAuth](../glossary.md#oauth) for clients acting for your Stripe user account, or an agent [API key](../glossary.md#api-key) for autonomous clients. Stripe says to give an agent key only the permissions the client needs.[^pm-09]
- With OAuth you can grant access to live accounts or sandboxes, set permissions for each, and revoke a session in your Stripe settings.[^pm-09]
- Stripe labels the MCP server a public preview. OAuth sessions last at most 14 days: refreshing tokens does not extend a session beyond 14 days from your first authorization, after which you reconnect.[^pm-09]
- **API key deadline.** Stripe's docs say: "Migrate by November 30, 2026. Starting in December, Stripe MCP will stop accepting full-access secret keys and restricted API keys without the Agent tag." Stripe says to replace such keys with new agent API keys or reconnect with OAuth.[^pm-09]
- **Team control.** An administrator can turn MCP access on or off for the whole team in the Dashboard, separately for live mode and sandboxes.[^pm-09]
- **Revoking access.** Your authorized MCP clients appear under OAuth sessions in your user settings; open a client's overflow menu and select Revoke access. An administrator can revoke another team member's sessions, one at a time or with Revoke all, under Team and security. Revoking applies only to the account or organization and the environment (live mode or a sandbox) you are viewing.[^pm-09]
- **Human confirmation.** Before an agent completes certain actions for you, Stripe can require you to review and approve the request in the Dashboard, through a link the agent gives you. This is separate from your MCP client's own tool-approval setting. After you click Approve, you tell the agent to retry. A request you do not approve within 24 hours expires.[^pm-09] The tool list marks sending money from a Treasury account, transfers between Stripe balances and currency conversion as needing human confirmation; the Treasury tools are in public preview.[^pm-09]
- **Stripe's advice.** Turn on your MCP client's tool-approval setting so you can review tool calls before they run, and take care when using the Stripe MCP alongside other servers, to avoid prompt injection attacks.[^pm-09]

### How do I connect Stripe's MCP server from my AI app?

Stripe recommends its agent plugins, which set up the MCP server and Stripe's [agent skills](../glossary.md#agent-skill) and keep them up to date. After installing the Stripe CLI, run `stripe agent setup`, which detects which agents you use.[^pm-09] For manual setup, Stripe gives these steps:[^pm-18]

| App | How to connect | Sources |
|---|---|---|
| Claude Code | Run `claude mcp add --transport http stripe https://mcp.stripe.com/`, then run `/mcp` to sign in with OAuth | [^pm-18] |
| Claude (web and desktop) | Install the official Stripe connector. On Team and Enterprise accounts, an owner must add it to the workspace before members can connect their Stripe accounts | [^pm-18] |
| Codex | Run `codex mcp add stripe --url https://mcp.stripe.com`. The ChatGPT desktop app, Codex CLI and Codex IDE extension share this configuration on your computer | [^pm-18] |
| ChatGPT | Install the official Stripe plugin, then connect your Stripe account and grant permissions in the OAuth window | [^pm-18] |
| Cursor | Use Stripe's Install in Cursor button, or add a `stripe` server with the URL `https://mcp.stripe.com` to `~/.cursor/mcp.json` | [^pm-09] |
| VS Code | Use Stripe's Install in VS Code button, or add the server to `.vscode/mcp.json` in your workspace | [^pm-18] |
| Other apps | Follow your app's MCP setup steps and use `https://mcp.stripe.com` as the server URL | [^pm-18] |

If you have feedback on the MCP server, Stripe asks you to email mcp@stripe.com; the server also has a `send_stripe_feedback` tool.[^pm-09][^pm-18]

## Link wallet for agents

Stripe also runs Link, a consumer wallet that gives an agent a one-time-use card or a shared payment token for a purchase the person approves in Link. Muse, Grok Bot and Instinct use it. See [Link wallet for agents](link-wallet-for-agents.md).[^sp-02][^sp-01]

## Visa Agentic Ready

Visa lists Stripe among the initial participants in its [Agentic Ready](../glossary.md#agentic-ready) program for the acceptance ecosystem, announced 2026-11-17. Stripe says it is testing ways to recognize agent-initiated payments, strengthen merchant controls and improve approval rates.[^pm-26] Visa's release for Europe, dated 2026-11-18, also lists Stripe among its more than 85 initial acceptance participants there.[^pm-25] See [Visa Intelligent Commerce](visa-intelligent-commerce.md).

## Unknown

Fees for shared payment tokens. No cited source confirms it, so the wiki says unknown.

Also unknown: spending caps on Treasury sends and transfers made through the MCP server, and the countries where the MCP server is available.

All programs: [Payments](README.md).

## Sources

[^pm-07]: [GitHub - agentic-commerce-protocol/agentic-commerce-protocol: The Agentic Commerce Protocol (ACP) is an interaction model and open standard for connec](../sources/pm-07.md). ACP (GitHub), official, retrieved 2026-11-12.
[^pm-08]: [Shared payment tokens - Stripe Documentation](../sources/pm-08.md). Stripe Docs, official, retrieved 2026-11-12.
[^pm-09]: [Model Context Protocol (MCP) - Stripe Documentation](../sources/pm-09.md). Stripe Docs, official, retrieved 2026-11-19.
[^pm-18]: [Model Context Protocol (MCP) - Stripe Documentation (Markdown version)](../sources/pm-18.md). Stripe Docs, official, retrieved 2026-11-19.
[^sp-02]: [Giving agents the ability to pay (Stripe)](../sources/sp-02.md). Stripe, official, retrieved 2026-11-18.
[^sp-01]: [Stripe helps Meta Muse shop with Link](../sources/sp-01.md). Stripe, official, retrieved 2026-11-18.
[^pm-26]: [CORRECTING and REPLACING Visa Expands Agentic Ready to Help Scale Trusted AI Commerce Globally](../sources/pm-26.md). Visa, official, retrieved 2026-11-20.
[^pm-25]: [Visa Expands Agentic Ready to Help Scale Trusted AI Commerce across Europe](../sources/pm-25.md). Visa (Visa UK newsroom), official, retrieved 2026-11-20.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20payments%2Fstripe.md&body=Page%3A%20payments%2Fstripe.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
