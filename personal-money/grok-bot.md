---
type: personal-money
id: grok-bot
title: Grok Bot
summary: Grok Bot can read balances, spending and investments from accounts you link through Plaid, read-only. It can also pay with a Link one-time card or X Money, with a prompt to approve each purchase.
page_status: current
last_verified: '2026-11-21'
kind: personal-agent
operator: xAI
agent_can: Through its Finance integration, answer questions about balances, spending, subscriptions and investments from bank, card and investment accounts linked through Plaid, read-only. Separately, pay at checkout with Stripe Link or X Money, with an approval step for each purchase
user_controls: You choose whether to link accounts and can unlink them anytime. A financial connection is read-only. A Link purchase shows the amount to Allow or Deny, and every X Money action that moves money needs its own approval. After a bank or brokerage connector returns data, the Bot asks before sharing it anywhere else
mcp_server: 'yes'
endpoint: https://connectors-gateway.grok.com/gateway/v1/finance/mcp
availability: The Finance integration was announced on 2026-09-26 and needs Grok Bot 0.49 or newer. Plans and regions for it are unknown
field_sources:
  operator:
  - gb-02
  agent_can:
  - gb-01
  - gb-02
  - gb-05
  user_controls:
  - gb-01
  - gb-02
  - gb-05
  mcp_server:
  - gb-02
  endpoint:
  - gb-02
  availability:
  - gb-01
  - gb-02
---

# Grok Bot

Grok Bot can read your balances, spending and investments from accounts you link through Plaid, and it can pay at checkout with Stripe Link or X Money. Reading accounts is read-only, and each purchase waits for your approval.[^gb-01][^gb-02][^gb-05]

## How does Grok Bot connect to your accounts?

- **The announcement.** On 2026-09-26 Grok Bot's official X account said the Bot now connects to your finances: you link bank, card and investment accounts with the new Finance integration, then ask Bot to help with spending and investments.[^gb-01]
- **Plaid does the linking.** The follow-up post says accounts connect through Plaid, access is read-only, Grok Bot never sees your logins, and you can unlink anytime.[^gb-01] Plaid is a [data aggregator](../glossary.md#data-aggregator). [How a Plaid connection works](plaid.md#how-does-a-plaid-connection-work) explains the steps.
- **What is shared.** The plugin's README lists contact details, account and balance information, transactions, credit and loans, and investments. It says Grok syncs and stores linked account data, which the connector needs in order to work, and that Grok Bot's privacy mode still controls whether conversations are stored or used for training.[^gb-02]
- **An MCP server.** The Finance plugin connects the Bot to a remote [MCP](../glossary.md#mcp) server hosted by xAI at the address in the header. The README says it needs no sign-in prompt in the client, because the Grok account linked to the caller is used.[^gb-02]
- **A caution in the README.** The README repeats a general warning that third-party connectors are not built or maintained by xAI and that people should review permissions before connecting.[^gb-02]

## What can it do with money?

- **Read.** Ask about balances, recent spending, subscriptions and investments across linked accounts.[^gb-02]
- **Not move money.** The README says a financial connection is read-only, so it cannot be used to move money into or out of bank accounts.[^gb-02]
- **Pay.** Grok Bot's changelog says that from v0.30.0 (2026-08-28) a Bot that wants to buy something shows a card with the amount to Allow or Deny, and Link then completes the payment. From v0.70.2 (2026-10-11), Bots can pay with X Money or Stripe Link.[^gb-05] See [Link wallet for agents](../payments/link-wallet-for-agents.md) and [X Money](x-money.md).
- **Wallets in settings.** Grok Bot's Vault page lists payment accounts, which are wallets you can connect such as Link, X Money or Shop Pay, and a default payment method that the Bot pays with first.[^gb-03]

## What do you control?

- You choose whether to link accounts, and the README says you can unlink or remove them from the Finance page on cursor.com.[^gb-02]
- After a bank or brokerage connector returns data, the Bot asks before sharing it anywhere else.[^gb-05]
- Grok Bot's approval system checks each action and shows an approval card with the operation and its inputs when one needs your OK. xAI recommends setting explicit boundaries for purchases and financial transfers.[^gb-04]

## Can Grok Bot connect to Coinbase?

Yes. Coinbase lists Grok Bot as a supported app for its remote [MCP](../glossary.md#mcp), which lets an AI app work with your Coinbase account.[^cb-09] This is separate from the read-only Finance integration above: Coinbase says its connection covers trading, portfolio management and x402 payments.[^cb-09] See [Coinbase](../providers/coinbase.md#how-do-i-connect-coinbase-from-my-ai-app) for the steps in the other apps Coinbase lists.

- **How to add it.** Click Marketplace, search for Coinbase, click Add, and sign in with your Coinbase account if prompted.[^cb-09]
- **A Grok connection carries over.** If you already connected Coinbase in Grok, it should also appear in your Grok Bot account.[^cb-09]
- **How much it is used there.** In Coinbase's own chart, Grok Bot was the largest AI app by [notional trading volume](../glossary.md#notional-volume) on Coinbase for Agents, at 40.4%.[^cb-13] Coinbase's post says "for now". Dollar totals are unknown. Period: 11/09 - 11/15 (the video does not show a year; 2026 is inferred from the post date).[^cb-13] See [the table](../providers/coinbase.md#which-ai-apps-trade-the-most-on-coinbase).
- **Connectors are account-wide.** A connector added by one Bot is available to all of your Bots. Coinbase says to limit access by selecting a dedicated portfolio on its approval screen.[^cb-09]

## Unknown

- Which plans and countries can use the Finance integration. The posts and README do not say.
- Which banks and card issuers can be linked. xAI's pages do not list them.
- Whether Plaid's access token is held by xAI or by another party inside the connector. The sources do not say.
- Whether Grok Bot's own pages describe the Finance integration in the docs. The three Grok Bot docs pages read for this record do not have a Finance section.

All pages: [Personal money agents](README.md).

## Sources

[^gb-01]: [Grok Bot on X: "Grok Bot now connects to your finances" (with follow-up post)](../sources/gb-01.md). Grok Bot (@bot on X), official, retrieved 2026-11-18.
[^gb-02]: [Finance plugin README (cursor/plugins, third_party/finance)](../sources/gb-02.md). cursor/plugins (GitHub), official, retrieved 2026-11-18.
[^gb-05]: [Grok Bot changelog](../sources/gb-05.md). xAI, official, retrieved 2026-11-18.
[^gb-03]: [Vault and secure sign-in (Grok Bot docs)](../sources/gb-03.md). xAI Docs, official, retrieved 2026-11-18.
[^gb-04]: [Approvals, security, and privacy (Grok Bot docs)](../sources/gb-04.md). xAI Docs, official, retrieved 2026-11-18.
[^cb-09]: [Coinbase MCP - Coinbase Developer Documentation](../sources/cb-09.md). Coinbase Developer Platform, official, retrieved 2026-11-19.
[^cb-13]: [Coinbase on X: "Which AI agent is the most popular on Coinbase?" (with video chart)](../sources/cb-13.md). Coinbase (@coinbase on X), official, retrieved 2026-11-21.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20personal-money%2Fgrok-bot.md&body=Page%3A%20personal-money%2Fgrok-bot.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
