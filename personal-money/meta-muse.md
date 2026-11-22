---
type: personal-money
id: meta-muse
title: Meta Muse
summary: Meta's personal AI agent. Its finance features use Plaid so people can connect bank, card, investment and mortgage accounts for personalized money guidance.
page_status: current
last_verified: '2026-11-22'
kind: personal-agent
operator: Meta
agent_can: Give personalized money guidance from accounts you connect through Plaid, such as balances, transactions, investment holdings and mortgage information. Separately, with your approval each time, buy online using Link by Stripe or a card saved in its Secure Credential Store
user_controls: You choose whether to connect accounts, and you can manage Plaid-powered connections in Plaid Portal. Muse always asks for your approval before completing a purchase, and you can disconnect a Connector at any time in Settings
mcp_server: unknown
endpoint: unknown
availability: Launched 2026-09-08 with Plaid-powered account connections in its finance features
field_sources:
  operator:
  - pb-01
  - pb-03
  agent_can:
  - pb-01
  - mm-01
  user_controls:
  - pb-01
  - mm-01
  - mm-02
  availability:
  - pb-01
---

# Meta Muse

Muse is Meta's personal AI agent. It launched on 2026-09-08 with Plaid-powered account connections in its finance features.[^pb-01]

## What it does with money

- People can connect financial accounts through Plaid to share balances, transactions, investment holdings, mortgage information and more.[^pb-01] Plaid is a [data aggregator](../glossary.md#data-aggregator).
- Plaid says Muse gives personalized guidance and helps people take steps toward their financial goals.[^pb-01]
- A CNBC report says people who gave Muse access to bank and card statements used it as a budgeting coach and to cancel unneeded subscriptions.[^pb-03]

## How does Muse pay for things?

- **With your approval.** Meta says Muse can help you make purchases online and always asks for your approval before completing one.[^mm-01]
- **Link by Stripe.** Meta recommends paying with Link by Stripe, which issues a one-time card number for each purchase so your real card number stays private.[^mm-01] Stripe says Meta integrated Link's wallet for agents with Muse for US consumers, and that you approve the transaction total in the chat.[^sp-01] See [Link wallet for agents](../payments/link-wallet-for-agents.md). Stripe's chief economist, writing on a personal account on 2026-11-20, says Link's agent wallet powers payments for personal agents including Muse, Instinct, and Grok, and that daily spend on Link Agent Wallet was nearly 80-fold higher in mid-November than at the start of September, measured as a [seven-day rolling average](../glossary.md#seven-day-rolling-average). The figures are for Link agent spend as a whole, not for Muse alone.[^sp-04] See [How much are agents spending?](../payments/link-wallet-for-agents.md#how-much-are-agents-spending).
- **A saved card.** Muse can also log in with credentials saved in its Secure Credential Store and pay with a saved credit card. Meta says you are responsible for all transactions Muse makes on your behalf.[^mm-01]
- **Bank accounts.** Meta's payments help page names only Link by Stripe and a saved credit card. It does not say Muse can pay from a bank account.[^mm-01]

## What you control

- You choose whether to connect an account, and you can manage Plaid-powered connections in Plaid Portal.[^pb-01] [How a Plaid connection works](plaid.md#how-does-a-plaid-connection-work) and [what you can do in Plaid Portal](plaid.md#what-can-you-control-in-plaid-portal) explain the steps.
- Muse checks with you before sensitive actions such as sending an email or making a purchase, and shows an audit trail of what it has done and plans to do.[^mm-03]
- By default Muse will not take many important actions without your approval, and you can disconnect a Connector at any time in Settings. Information Muse already used may remain in its memories and your conversation history.[^mm-02]

## How banks reacted (news reports)

- CNBC says bank stocks fell in September when Muse topped the app download charts, on fears that people would use agents to move money to higher-yield accounts.[^bl-01]
- POLITICO says JPMorgan's CEO urged customers not to give their passwords to Meta.[^pb-04]

More on this: [Banks and outside agents](banks-and-outside-agents.md).

## Unknown

Whether Muse can pay bills or send money from a bank account (Meta's payments page names only Link by Stripe and a saved credit card), and whether it has an official MCP server or other developer access. No cited source confirms it, so the wiki says unknown. Meta's Connectors help page does not name a financial or Plaid connector, so how Muse's Plaid connection appears in Settings is also unknown.

All pages: [Personal money agents](README.md).

## Sources

[^pb-01]: [Plaid powers Meta's new AI agent, Muse - Plaid](../sources/pb-01.md). Plaid, official, retrieved 2026-11-12.
[^pb-03]: [Meta's Muse is attacking one of economy's most profitable weak spots](../sources/pb-03.md). CNBC, third-party, retrieved 2026-11-12.
[^mm-01]: [How Muse works with payments (Meta Help Center)](../sources/mm-01.md). Meta, official, retrieved 2026-11-18.
[^sp-01]: [Stripe helps Meta Muse shop with Link](../sources/sp-01.md). Stripe, official, retrieved 2026-11-18.
[^sp-04]: [Ernie Tedeschi on X: "The agentic story on the eve of the 2026 holiday season"](../sources/sp-04.md). Ernie Tedeschi (@ernietedeschi on X), Stripe's chief economist, personal account, third-party, retrieved 2026-11-22.
[^mm-03]: [Introducing Muse (Meta newsroom)](../sources/mm-03.md). Meta, official, retrieved 2026-11-18.
[^mm-02]: [How Muse works with Connectors (Meta Help Center)](../sources/mm-02.md). Meta, official, retrieved 2026-11-18.
[^bl-01]: [JPMorgan blocks outside AI agents like Muse, Instinct from account access](../sources/bl-01.md). CNBC, third-party, retrieved 2026-11-12.
[^pb-04]: [AI agents scramble banks' fight with fintechs](../sources/pb-04.md). POLITICO, third-party, retrieved 2026-11-12.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20personal-money%2Fmeta-muse.md&body=Page%3A%20personal-money%2Fmeta-muse.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
