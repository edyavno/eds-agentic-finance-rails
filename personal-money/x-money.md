---
type: personal-money
id: x-money
title: X Money
summary: X Money is a US money account inside the X app, run by X Payments LLC with Cross River Bank. Through the Grok Bot plugin, an agent can read the balance and history, and send or pay with approval per action.
page_status: current
last_verified: '2026-11-18'
kind: payment-credential
operator: X Payments LLC, with Cross River Bank holding the deposit accounts
agent_can: Through the Grok Bot plugin and X Money's hosted MCP server, view the balance and transaction history, use the X Money card for purchases, and send or request money with users on X. X Money decides which of these actions each account gets
user_controls: Connect with a code or QR code approved with a passkey in the X Money app, and revoke at X > Money > Settings > Connections. Every action that moves money needs its own Approve or Cancel, X Money refuses calls that were not approved, agents have separate limits, and higher-risk transfers stay in the X app
mcp_server: 'yes'
endpoint: https://mcp.money.x.com/mcp
availability: Rolling out in the US since 2026-07-27, first to Premium and Premium+ subscribers. X's pages now say it is available to select users who are 18 or older and live in the 50 states or DC. Interest is not available in New York
field_sources:
  operator:
  - xm-04
  - xm-05
  agent_can:
  - xm-01
  user_controls:
  - xm-01
  mcp_server:
  - xm-01
  endpoint:
  - xm-01
  availability:
  - xm-03
  - xm-04
  - xm-08
---

# X Money

X Money is a money account inside the X app for people in the United States. An agent connected through the Grok Bot plugin can read the balance and transactions, pay with the X Money card, and send or request money, but each action that moves money needs your approval.[^xm-01]

## What is X Money?

- **An account in the X app.** X describes a financial services app with instant payments to users on X, direct deposit, wires, mailed checks and the X Card, a Visa card.[^xm-03][^xm-04]
- **Who holds the money.** X says X Payments LLC is not an FDIC-insured bank and that deposit accounts are held at Cross River Bank, Member FDIC.[^xm-04] A US regulator's database lists the product as an active digital wallet or P2P account, with Cross River Bank as issuer and X Payments LLC as program manager.[^xm-06] Cross River says it powers X Money.[^xm-02]
- **Licenses.** X's license page says X Payments LLC is licensed to transmit money in the listed US jurisdictions, is registered with FinCEN as a money services business, and is not a bank.[^xm-05] New York's financial regulator recorded its approval as a money transmitter effective 2026-07-23.[^xm-07]
- **Launch.** X Money's official account said on 2026-07-27 that it was rolling out to US Premium and Premium+ subscribers starting that day.[^xm-08] X's pages now say it is available to select users who are 18 or older and to residents of the 50 states and DC, and that interest is not currently available to New York residents.[^xm-03][^xm-04]
- **Sign-in security.** X says a passkey is required to sign in, and card and transfer limits are set in the Money tab under Settings > Limits.[^xm-04]

## What agent features does it have?

- **A hosted MCP server.** The Grok Bot plugin connects agents to X Money through X Money's hosted [MCP](../glossary.md#mcp) server, at the address in the header.[^xm-01]
- **What the plugin lists.** Use your X Money card, send money to users on X, manage your finances, view your balance and browse transaction history. The README adds that X Money decides which actions are available for each account.[^xm-01]
- **Connecting.** Sign-in is [OAuth](../glossary.md#oauth). Grok Bot opens a "Connect Grok Bot to X Money" page that shows a connection code and a QR code. You enter the code in the X Money app, or scan the QR code, and approve with your [passkey](../glossary.md#passkey). The code is valid for about 5 minutes.[^xm-01]
- **Approval on every money move.** Before sending money, requesting money or paying a merchant, the agent shows an Approve or Cancel prompt that says who, how much and what for. Each action needs its own approval, and X Money refuses any such call that was not approved.[^xm-01]
- **Limits.** Agent calls pass the same checks as the app plus separate limits for agents. When X Money refuses an action, the agent relays the reason and does not retry. Higher-risk transfers stay in the X app and are not available to agents.[^xm-01]
- **What the agent does not see.** The README says the agent never sees your X Money password, passkey or bank credentials, and that card details used for a purchase go straight to the merchant checkout and are not shown in chat.[^xm-01]
- **Revoking.** You can revoke the connection at any time from X > Money > Settings > Connections.[^xm-01]
- **Live money.** The README says payments made through the plugin are live and move real money.[^xm-01]

## How does Grok Bot use X Money?

- **As a wallet at checkout.** Grok Bot's Vault page lists X Money, Link and Shop Pay as wallets you can connect, and a default payment method that Grok Bot pays with first.[^gb-03] The changelog says that from v0.70.2 (2026-10-11) Bots can pay with X Money or Stripe Link.[^gb-05]
- **Connecting.** The changelog says X Money connects in one tap from a chat, the connector page or checkout (v0.75.2, 2026-10-22). From v0.75.5 (2026-10-23) connecting X also connects X Money through the same account, and asking about your X Money balance, activity or card installs X Money. If X Money is not set up on your X account, the Bot links the Money tab on X (v0.77.0, 2026-10-26).[^gb-05]
- **After you revoke.** A revoked X Money connection stays signed out until you tap Connect in the app, and saying yes in chat does not reconnect it (v0.79.3, 2026-11-06).[^gb-05]
- **When the card is off.** If X Money card payments are not enabled for your account, the Bot says so and offers the same order with another payment method (v1.2.0, 2026-11-16).[^gb-05]

More: [Grok Bot](grok-bot.md), [Link wallet for agents](../payments/link-wallet-for-agents.md).

## Unknown

- Whether agents other than Grok Bot can connect. The README describes a Grok Bot plugin; X's own pages say nothing about agents.
- What the separate agent limits are, and which transfers count as higher-risk. No source gives amounts or a list.
- Whether X's help center documents agent access. The X Money overview, FAQ and license pages read for this record do not mention agents, Grok Bot or MCP.
- A full list of the tools the hosted MCP server offers. The README describes them in plain terms only.
- Whether X Money works with agents outside the United States. X Money itself is US-only.

All pages: [Personal money agents](README.md).

## Sources

[^xm-01]: [X Money plugin README (cursor/plugins, third_party/x-money)](../sources/xm-01.md). cursor/plugins (GitHub), official, retrieved 2026-11-18.
[^xm-03]: [X Money overview (payments.x.com)](../sources/xm-03.md). X Corp, official, retrieved 2026-11-18.
[^xm-04]: [X Money Frequently Asked Questions](../sources/xm-04.md). X Corp, official, retrieved 2026-11-18.
[^xm-06]: [X Money Stored Value Account (CFPB prepaid account agreements database)](../sources/xm-06.md). Consumer Financial Protection Bureau, third-party, retrieved 2026-11-18.
[^xm-02]: [Cross River Powers X Money: The First P2P Payments Experience Built Into a U.S. Social Media Platform](../sources/xm-02.md). Cross River Bank, third-party, retrieved 2026-11-18.
[^xm-05]: [X Payments Money Transmitter Licenses](../sources/xm-05.md). X Corp, official, retrieved 2026-11-18.
[^xm-07]: [Weekly Banking Bulletin, July 24, 2026 (New York DFS)](../sources/xm-07.md). New York State Department of Financial Services, third-party, retrieved 2026-11-18.
[^xm-08]: [X Money on X: "𝕏 Money is rolling out to U.S. Premium and Premium+ subscribers starting today"](../sources/xm-08.md). X Money (@XMoney on X), official, retrieved 2026-11-18.
[^gb-03]: [Vault and secure sign-in (Grok Bot docs)](../sources/gb-03.md). xAI Docs, official, retrieved 2026-11-18.
[^gb-05]: [Grok Bot changelog](../sources/gb-05.md). xAI, official, retrieved 2026-11-18.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20personal-money%2Fx-money.md&body=Page%3A%20personal-money%2Fx-money.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
