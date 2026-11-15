---
type: payment
title: Payments
summary: How AI agents pay. Card-network agent programs, payment tokens, commerce and payment protocols, and an agent credit card, each with its own page and a sourced record.
page_status: current
last_verified: '2026-11-14'
---

# Payments

This section covers how an AI agent pays for things on a person's behalf, often called [agentic commerce](../glossary.md#agentic-commerce). Each program has its own page. The YAML header at the top of each page holds a short record: who runs it, what an agent can do, what the person controls, whether there is an official [MCP](../glossary.md#mcp) server, and how available it is. Every value is sourced or says "unknown." The same records are in [data/programs.json](../data/programs.json).

## The programs

| Program | Type | In one line |
|---|---|---|
| [Visa Intelligent Commerce](visa-intelligent-commerce.md) | Card network | Approved agent builders pay with tokenized Visa credentials, under purchase instructions the consumer approved.[^pm-01] |
| [Mastercard Agent Pay](mastercard-agent-pay.md) | Card network | Only registered agents can pay, using Mastercard agentic tokens.[^pm-05][^pm-06] |
| [Agentic Commerce Protocol (ACP)](agentic-commerce-protocol.md) | Commerce protocol | An open standard for buyers, their agents and businesses to complete purchases. OpenAI and Stripe maintain it, and it is in beta.[^pm-07] |
| [Stripe](stripe.md) | Payment tokens and MCP | Shared payment tokens give a seller limited use of a customer's payment method. Stripe also runs an official MCP server.[^pm-08][^pm-09] |
| [PayPal](paypal.md) | MCP server and toolkit | An MCP server and an agent toolkit for PayPal business APIs such as orders and invoices.[^pm-10][^pm-11] |
| [x402](x402.md) | Payment protocol | An open standard for paying inside a web request, built on the HTTP 402 "Payment Required" status.[^pm-14][^pm-15] |
| [AP2 (Agent Payments Protocol)](ap2.md) | Mandate protocol | An open protocol that carries signed proof of what the user authorized.[^pm-13] |
| [Robinhood Agentic Credit Card](robinhood-agentic-credit-card.md) | Agent card | A [virtual card](../glossary.md#virtual-card) for your agent, with approval for each purchase or a required monthly limit.[^rh-09] |

## How the controls work

The sources describe three kinds of control. Most programs use more than one.

- **The network vets the agent.** Visa requires approved participants and agent registration before production use.[^pm-01] Mastercard registers and verifies agents before they can transact.[^pm-06]
- **The credential is limited.** Stripe's shared payment tokens carry usage and expiry limits.[^pm-08] Visa and Mastercard use tokenized credentials instead of the raw card number.[^pm-01][^pm-06] See [payment token](../glossary.md#payment-token).
- **The person approves.** Robinhood lets you approve each purchase in its app. If you turn that off, a monthly limit is required.[^rh-09] AP2 records the user's authorization as signed [mandates](../glossary.md#mandates).[^pm-13]

## What is still unknown

- Fees for agent payments. None of the cited sources give them.
- Which consumer AI apps can use each card-network program today.
- Production MCP addresses for Visa and Mastercard.

See [gaps](../gaps.md) for the full list.

## Related pages

- [Agent payments](../rails/agent-payments.md): the one-table rail overview.
- [Agent identity](../rails/agent-identity.md): how merchants tell which agent is calling, including Visa's Trusted Agent Protocol and Web Bot Auth.
- [Mandates and data access](../rails/mandates-and-data-access.md): proof of authorization and the US data-rights rule.
- [Personal money agents](../personal-money/README.md): agents that work with your bank and card data.

Not investment advice. No affiliate links.

## Sources

[^pm-01]: [Visa Developer Center](../sources/pm-01.md). Visa Developer, official, retrieved 2026-11-12.
[^pm-05]: [Mastercard Agent Pay: secure, scalable and trusted agentic AI](../sources/pm-05.md). Mastercard, official, retrieved 2026-11-12.
[^pm-06]: [Agentic token framework: Driving trusted AI transactions](../sources/pm-06.md). Mastercard, official, retrieved 2026-11-12.
[^pm-07]: [GitHub - agentic-commerce-protocol/agentic-commerce-protocol: The Agentic Commerce Protocol (ACP) is an interaction model and open standard for connec](../sources/pm-07.md). ACP (GitHub), official, retrieved 2026-11-12.
[^pm-08]: [Shared payment tokens - Stripe Documentation](../sources/pm-08.md). Stripe Docs, official, retrieved 2026-11-12.
[^pm-09]: [Model Context Protocol (MCP) - Stripe Documentation](../sources/pm-09.md). Stripe Docs, official, retrieved 2026-11-12.
[^pm-10]: [MCP server quickstart guide - PayPal Developer](../sources/pm-10.md). PayPal Developer, official, retrieved 2026-11-12.
[^pm-11]: [Agent toolkit quickstart guide - PayPal Developer](../sources/pm-11.md). PayPal Developer, official, retrieved 2026-11-12.
[^pm-14]: [GitHub - x402-foundation/x402: A payments protocol for the internet. Built on HTTP. · GitHub](../sources/pm-14.md). x402 Foundation (GitHub), official, retrieved 2026-11-12.
[^pm-15]: [x402 specification v2](../sources/pm-15.md). x402 Foundation (GitHub), official, retrieved 2026-11-12.
[^pm-13]: [AP2 - Agent Payments Protocol Documentation](../sources/pm-13.md). AP2 Protocol, official, retrieved 2026-11-12.
[^rh-09]: [Agentic Credit Card - Robinhood](../sources/rh-09.md). Robinhood, official, retrieved 2026-11-12.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20payments%2FREADME.md&body=Page%3A%20payments%2FREADME.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
