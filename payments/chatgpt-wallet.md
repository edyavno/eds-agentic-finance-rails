---
type: payment
id: chatgpt-wallet
title: ChatGPT Wallet
summary: OpenAI's wallet that lets an agent in ChatGPT pay for you. You approve each purchase with a biometric check, and the card network supplies a payment token so the agent and merchant never see your real card number.
page_status: current
last_verified: '2026-11-19'
kind: payment-credential
operator: OpenAI, built with American Express, Mastercard and Visa
agent_can: Complete a purchase at a merchant's normal checkout with a one-purchase payment token, after you approve it
user_controls: You review the items, total and card, then approve each purchase with a biometric check such as Face ID. The terms also allow granting ChatGPT authority to approve purchases in advance
mcp_server: unknown
endpoint: unknown
availability: Rolling out from 2026-11-13 in dots, to ChatGPT Pro users in the US aged 18 or older with eligible US-issued American Express, Chase, Mastercard and Visa cards
field_sources:
  operator:
  - oa-01
  agent_can:
  - oa-01
  - oa-04
  user_controls:
  - oa-01
  - oa-02
  - oa-03
  availability:
  - oa-01
  - oa-02
---

# ChatGPT Wallet

ChatGPT Wallet lets an agent in ChatGPT pay a merchant for you, without the agent or the merchant seeing your actual card details. OpenAI announced it on 2026-11-13 and built it with American Express, Mastercard and Visa.[^oa-01]

## How a purchase works

- **Add a card once.** You save an eligible card in Wallet. Your bank may ask you to verify it.[^oa-02]
- **Approve each purchase.** Before each purchase you review the items, total and selected card, then approve with a security check such as Face ID or a fingerprint.[^oa-01] Approval needs biometric verification on a supported device.[^oa-02]
- **The network supplies a token.** After you approve, the card network provides a [network token](../glossary.md#network-token) with its own card number, security code and expiry date. The charge lands on your card.[^oa-01]
- **The merchant checks out as usual.** Wallet works with existing checkout pages, with no Wallet-specific integration. The merchant receives a network token, not the full card number, and should not reuse it for another purchase.[^oa-04]
- **The bank and merchant still decide.** Your card issuer decides whether to authorize the payment, and the merchant decides whether to accept the order.[^oa-03]

Wallet does not hold a balance, extend credit or move funds.[^oa-03] OpenAI says you keep your card's rewards and dispute protections.[^oa-01]

## What you control

- Every purchase needs your review and approval. The terms also allow granting ChatGPT the authority to approve purchases in advance.[^oa-03]
- OpenAI says it expects users to be able to set spending limits, categories or time periods and pre-approve purchases over time.[^oa-01] That is a stated plan, not a current feature.

## Who it works with

- **Card networks.** Built in partnership with American Express, Mastercard and Visa.[^oa-01] See [Mastercard Agent Pay](mastercard-agent-pay.md) and [Visa Intelligent Commerce](visa-intelligent-commerce.md). OpenAI does not say whether Wallet runs on those programs.
- **Fraud and payment partners.** OpenAI names fraud prevention partners Forter, Riskified, Sardine and Signifyd, and payment service providers Adyen, Checkout.com and Stripe, as working to help their systems recognize legitimate agent purchases.[^oa-01]
- **Merchant websites.** OpenAI asks merchants to recognize signed agent requests with [Web Bot Auth](../glossary.md#web-bot-auth), and warns that some sites may block agent purchases by accident.[^oa-01] Some merchants block agents on purpose: see [Merchants and outside agents](merchants-and-outside-agents.md).

## Availability

Wallet started rolling out on 2026-11-13 in dots, OpenAI's agents, for ChatGPT Pro subscribers in the US aged 18 or older.[^oa-01] It works with eligible US-issued American Express, Chase, Mastercard and Visa cards. It is not available in Chat, Work or standalone Codex threads.[^oa-02]

## How do I add a Chase card?

OpenAI's help page gives these steps for an eligible Chase card:[^oa-02]

1. Install the Chase app on your phone and sign in with biometrics.
2. Follow the setup link to approve the connection in the Chase mobile app. If you are on a computer, scan the QR code with your phone.
3. After approving in the Chase app, return to Wallet to finish setup.

You must be the primary cardholder, not an authorized user.[^oa-02] See also [Banks and outside agents](../personal-money/banks-and-outside-agents.md#what-about-shopping-with-a-card) for a news report on Chase and agents that shop with a card number.

## Related ChatGPT pages

- [Finances in ChatGPT](../personal-money/chatgpt-finances.md) reads your accounts through Plaid. It is separate from the wallet and cannot move money.[^oa-05]
- [OpenAI dots](../personal-money/openai-dots.md) are always-on agents that can buy with a saved merchant card after you approve.[^oa-07]

## Unknown

Whether there is an official MCP server or a public endpoint, fees, and when Wallet will reach more users or countries. No cited source confirms it, so the wiki says unknown.

All programs: [Payments](README.md).

## Sources

[^oa-01]: [Introducing ChatGPT Wallet](../sources/oa-01.md). OpenAI, official, retrieved 2026-11-15.
[^oa-02]: [Making purchases with ChatGPT Wallet](../sources/oa-02.md). OpenAI Help Center, official, retrieved 2026-11-19.
[^oa-04]: [Accept payments - OpenAI Commerce](../sources/oa-04.md). OpenAI Developers, official, retrieved 2026-11-15.
[^oa-03]: [ChatGPT Wallet terms](../sources/oa-03.md). OpenAI, official, retrieved 2026-11-15.
[^oa-05]: [Finances in ChatGPT (OpenAI Help Center)](../sources/oa-05.md). OpenAI, official, retrieved 2026-11-18.
[^oa-07]: [Dots privacy, security, and safety FAQs (OpenAI Help Center)](../sources/oa-07.md). OpenAI, official, retrieved 2026-11-18.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20payments%2Fchatgpt-wallet.md&body=Page%3A%20payments%2Fchatgpt-wallet.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
