---
type: personal-money
id: plaid
title: Plaid MCP servers
summary: 'Plaid''s MCP servers are developer tools: a hosted Dashboard MCP for diagnostics and a local sandbox MCP. They do not give agents access to users'' accounts.'
page_status: current
last_verified: '2026-11-18'
kind: aggregator-tools
operator: Plaid
agent_can: 'Developer work only: production diagnostics and analytics for a Plaid customer''s team, and a local sandbox MCP for building. No access to end users'' accounts'
user_controls: The Dashboard MCP needs a Plaid OAuth token, and the team must be approved for Production access
mcp_server: 'yes'
endpoint: https://api.dashboard.plaid.com/mcp/
availability: The Dashboard MCP is under active development. Plaid says breaking changes may occur and support is limited
field_sources:
  operator:
  - pb-02
  agent_can:
  - pb-02
  user_controls:
  - pb-02
  mcp_server:
  - pb-02
  endpoint:
  - pb-02
  availability:
  - pb-02
---

# Plaid MCP servers

Plaid is the [data aggregator](../glossary.md#data-aggregator) behind Meta Muse's account connections.[^pb-01] It also powers account connections for other assistants, listed [below](#which-assistants-connect-through-plaid). Its own [MCP](../glossary.md#mcp) servers, though, are for developers. They are not a way for an agent to reach a person's bank account.[^pb-02]

## The two servers

- **Dashboard MCP.** Hosted by Plaid at `https://api.dashboard.plaid.com/mcp/`. It gives production diagnostics and analytics: debugging Items (connected accounts), Link conversion data and usage metrics. It works with production data only, and the team must be approved for Production access.[^pb-02]
- **AI coding toolkit.** A local MCP server for development, in a [sandbox](../glossary.md#sandbox). It offers mock data, documentation search and similar tools.[^pb-02]

The Dashboard MCP uses a Plaid [OAuth](../glossary.md#oauth) token. Plaid says it is under active development, breaking changes may occur, and support is limited.[^pb-02]

## Plaid and personal agents

- Plaid says it supports connections to more than 12,000 financial institutions and financial apps in the US (company-reported).[^pb-01]
- People can manage their Plaid-powered connections in Plaid Portal.[^pb-01]

See [Meta Muse](meta-muse.md) and [Banks and outside agents](banks-and-outside-agents.md).

## How does a Plaid connection work?

When an assistant connects to your accounts through Plaid, the steps below are what Plaid's developer documentation describes. They apply to apps in general, and the assistants' own pages say which of them each one uses.

1. **Link opens.** [Plaid Link](../glossary.md#plaid-link) is the screen where you choose your bank and sign in. Plaid says using Link is mandatory for all Plaid integrations except a few products that need no end-user step, and that it is the only way to connect accounts in Production.[^pb-14]
2. **Banks that use OAuth.** For many large banks you leave Link, sign in and approve sharing on the bank's own website or app, then return. Plaid says this lets people grant access without sharing credentials with the third party, and that [OAuth](../glossary.md#oauth) support is required for US, EU and UK institutions.[^pb-15]
3. **You see what is requested.** Plaid says [Data Transparency Messaging](../glossary.md#data-transparency-messaging) tells you which data types an app requests and why. Plaid introduced it to help customers stay in compliance with the 1033 rule, and since 2024-10-31 new US and Canada customers are enrolled automatically.[^pb-16] The API only returns data for products you consented to in Link.[^pb-16][^pb-17]
4. **Tokens.** The app creates a temporary `link_token`. When you finish, Link returns a temporary `public_token`, which the app exchanges for a permanent `access_token` and an `item_id`.[^pb-14] The `public_token` expires after 30 minutes. The `access_token` does not expire but can be revoked.[^pb-18]
5. **One Item per login.** An [Item](../glossary.md#item) is a login at a financial institution, and the `access_token` corresponds to it.[^pb-18]
6. **Data.** For transactions, Plaid says an app can retrieve and refresh up to 24 months of history with merchant, geolocation and category information, and fetch updates with `/transactions/sync`.[^pb-19]
7. **Staying connected.** Plaid sends a `PENDING_DISCONNECT` webhook (US and Canada) or `PENDING_EXPIRATION` webhook (UK and EU) when access is about to expire, and the person can go through Link's update mode to renew it.[^pb-18]

Whether a particular assistant's service, such as xAI's, holds the access token or hands the data to another party is not stated in the sources, so the wiki says unknown.

## What can you control in Plaid Portal?

- **Plaid Portal.** [Plaid Portal](../glossary.md#plaid-portal) at my.plaid.com lets people see which apps have access to their financial information and the data types shared, disconnect accounts from apps, and delete their data from Plaid's systems. Plaid announced it for the US on 2022-01-25.[^pb-20]
- **Consumer help.** Plaid's help article says you can use Portal or a Privacy Request Form to change how you share data, withdraw Plaid's access and request deletion, and that Plaid may retain some information as permitted or required by law.[^pb-21]
- **Webhooks.** If you revoke permission through Plaid, such as in Portal, Plaid says it may fire a `USER_PERMISSION_REVOKED` webhook to the app. If you revoke directly at your bank, that webhook may not fire. `USER_ACCOUNT_REVOKED` is sent only for some institutions.[^pb-18]
- **Removing an Item.** An app can call `/item/remove`, after which the `access_token` is no longer valid. Plaid says an Item removed this way may still show as active in a bank's own OAuth permission manager.[^pb-18]
- **Assistants point here.** ChatGPT, Gemini, Claude and others tell people to manage access through Plaid. See [Finances in ChatGPT](chatgpt-finances.md), [Gemini with Google Wallet](gemini-google-wallet.md) and [Claude Personal Finance](claude-personal-finance.md).[^pb-11][^pb-08]

## Which assistants connect through Plaid?

| Assistant | What Plaid or the assistant's maker says |
|---|---|
| [Grok Bot](grok-bot.md) | Accounts connect through Plaid, read-only.[^gb-01] |
| [Meta Muse](meta-muse.md) | Plaid powers account connections in its finance features.[^pb-01] |
| [Finances in ChatGPT](chatgpt-finances.md) | Accounts connect through Plaid, and credit report data through Experian.[^oa-05] |
| [Claude Personal Finance](claude-personal-finance.md) | Plaid powers account connections, read-only.[^pb-10] |
| [Gemini with Google Wallet](gemini-google-wallet.md) | Accounts link to Google Wallet through Plaid, read-only.[^pb-08] |
| [Perplexity Personal CFO](perplexity-personal-cfo.md) | Plaid says it powers the connection, in the US and in 17 European countries.[^pb-12][^pb-13] |
| [Instinct](instinct.md) | Plaid powers read-only connectivity for US users.[^pb-09] |

[Claude Duet](claude-duet.md) is not on this list: Anthropic's help article says Personal Finance is not available in Duet.[^cl-01] Whether [OpenAI dots](openai-dots.md) can read Plaid-linked data is unknown.

## Plaid's own figures

These are company-reported. Plaid says more than 800 AI companies build on it. In posts about Instinct and Claude it says 75% of people who connect more than one bank account to an AI platform connect a second within 1 day, 65% within one hour, and they keep more than 95% of connections active, and that nearly two-thirds of US people connecting accounts to AI assistants through Plaid had never used a Plaid-powered personal finance app.[^pb-09][^pb-10] In a 2026-11-12 post it says it provides EU connections as a regulated account information service through Plaid B.V.[^pb-13]

## Is there a Plaid MCP for partners?

Plaid's August 2026 product updates introduced MCP for Data Partners in Early Access. It lets data partners connect an AI agent such as Claude, Cursor or Codex to Plaid to investigate and resolve integration issues. It is for partners' integration work, not for reading a person's accounts.[^pb-22]

## What else does Plaid offer for AI agents?

- **Agent Detection.** On 2026-11-16 Plaid launched [Agent Detection](../glossary.md#agent-detection), an SDK that tells banks, fintechs and other financial companies whether a session is a person or an AI agent, and which AI provider the agent is associated with. It works across login, sign-up and money movement. Plaid says it looks at thousands of signals across devices, behavior, automation patterns and network activity.[^pb-06]
- **A company-reported test.** In Plaid's own side-by-side test on live traffic, Agent Detection found 2.3x more agent sessions than competitors with no increase in false positives. That figure is Plaid's, not independent.[^pb-06]
- **Read-only access for assistants.** Plaid says it powers consumer-permissioned, read-only access for AI assistants including ChatGPT, Claude, Perplexity, Grok, Meta Muse and Google Gemini (company-reported).[^pb-06] Google's Gemini uses Plaid to link accounts to Google Wallet: see [Gemini with Google Wallet](gemini-google-wallet.md).[^pb-08]
- **Plans, not products.** Plaid says it is building toward a way for consumers to approve specific actions by an agent, and extending its Trust Index, which scores sessions for risk, to agent-driven sessions. It gives no dates.[^pb-06]

## Unknown

Whether Plaid plans an MCP for end-user account access, and when its consumer-approved path for agent actions will launch. No cited source confirms it, so the wiki says unknown.

All pages: [Personal money agents](README.md).

## Sources

[^pb-01]: [Plaid powers Meta's new AI agent, Muse - Plaid](../sources/pb-01.md). Plaid, official, retrieved 2026-11-12.
[^pb-02]: [Resources - MCP Server - Plaid Docs](../sources/pb-02.md). Plaid Docs, official, retrieved 2026-11-12.
[^pb-14]: [Link overview (Plaid Docs)](../sources/pb-14.md). Plaid Docs, official, retrieved 2026-11-18.
[^pb-15]: [Link OAuth guide (Plaid Docs)](../sources/pb-15.md). Plaid Docs, official, retrieved 2026-11-18.
[^pb-16]: [Data Transparency Messaging migration guide (Plaid Docs)](../sources/pb-16.md). Plaid Docs, official, retrieved 2026-11-18.
[^pb-17]: [Choosing how to initialize products (Plaid Docs)](../sources/pb-17.md). Plaid Docs, official, retrieved 2026-11-18.
[^pb-18]: [Items API reference (Plaid Docs)](../sources/pb-18.md). Plaid Docs, official, retrieved 2026-11-18.
[^pb-19]: [Transactions API reference (Plaid Docs)](../sources/pb-19.md). Plaid Docs, official, retrieved 2026-11-18.
[^pb-20]: [Announcing Plaid Portal: An ongoing commitment to data privacy](../sources/pb-20.md). Plaid, official, retrieved 2026-11-18.
[^pb-21]: [Can I remove app access or delete my data from Plaid? (Plaid Consumer Help Center)](../sources/pb-21.md). Plaid Consumer Help Center, official, retrieved 2026-11-18.
[^pb-11]: [ChatGPT personal finance experience, powered by Plaid](../sources/pb-11.md). Plaid, official, retrieved 2026-11-18.
[^pb-08]: [Plaid is powering personalized financial insights with Google Wallet in the Gemini app](../sources/pb-08.md). Plaid, official, retrieved 2026-11-18.
[^gb-01]: [Grok Bot on X: "Grok Bot now connects to your finances" (with follow-up post)](../sources/gb-01.md). Grok Bot (@bot on X), official, retrieved 2026-11-18.
[^oa-05]: [Finances in ChatGPT (OpenAI Help Center)](../sources/oa-05.md). OpenAI, official, retrieved 2026-11-18.
[^pb-10]: [Plaid powers financial insights in Claude](../sources/pb-10.md). Plaid, official, retrieved 2026-11-18.
[^pb-12]: [Plaid and Perplexity expand integration to power personalized financial insights](../sources/pb-12.md). Plaid, official, retrieved 2026-11-18.
[^pb-13]: [Perplexity brings Personal CFO to Europe with Plaid](../sources/pb-13.md). Plaid, official, retrieved 2026-11-18.
[^pb-09]: [Instinct gets the full financial picture with Plaid](../sources/pb-09.md). Plaid, official, retrieved 2026-11-18.
[^cl-01]: [Use Personal Finance in Claude (Claude Help Center)](../sources/cl-01.md). Anthropic, official, retrieved 2026-11-18.
[^pb-22]: [Product Updates: August 2026 (Plaid)](../sources/pb-22.md). Plaid, official, retrieved 2026-11-18.
[^pb-06]: [Introducing Agent Detection: building trust in the age of agentic finance](../sources/pb-06.md). Plaid, official, retrieved 2026-11-18.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20personal-money%2Fplaid.md&body=Page%3A%20personal-money%2Fplaid.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
