---
type: analysis
title: 'AP2 vs ACP vs x402: which AI agent payment protocol does what?'
summary: AP2, ACP and x402 compared side by side. What each agent payment protocol does, who maintains it, what it costs and its limits, with a sourced table and FAQ.
page_status: current
last_verified: '2026-11-17'
---

# AP2 vs ACP vs x402: which AI agent payment protocol does what?

AP2, ACP and x402 are often compared, but each covers a different step of an AI agent's purchase. AP2 records what a person authorized the agent to do,[^pm-13] ACP runs a checkout between an AI app and a business,[^pm-07] and [x402](../glossary.md#x402) pays for a web resource inside the request itself.[^pm-15] All three are open specifications under the Apache 2.0 license, not hosted services you sign up for.[^pm-12][^pm-07][^pm-14] Which one fits depends on what is being bought and what has to be proved.

| Protocol | Best for | Cost to use | Key strength | Key limitation | Sources |
|---|---|---|---|---|---|
| [AP2](../payments/ap2.md) (Agent Payments Protocol) | Proving what a person authorized an agent to buy, including when the person is not present | Open spec, Apache 2.0. Fees depend on the payment method used: unknown | Signed mandates chain into an audit trail for each purchase | First version supports "pull" methods such as credit and debit cards; which networks and wallets use AP2 in production is unknown | [^pm-13][^pm-12] |
| [ACP](../payments/agentic-commerce-protocol.md) (Agentic Commerce Protocol) | Letting a user buy from a business inside an AI app, without the app being the [merchant of record](../glossary.md#merchant-of-record) | Open spec, Apache 2.0. Processing fees: unknown | A checkout API and a delegated-payment spec, published as OpenAPI files; OpenAI and Stripe implemented it first | Still in beta; what the person approves is unknown | [^pm-07] |
| [x402](../payments/x402.md) | Paying for a web resource, such as data or an API call, as part of the request | Open standard, Apache 2.0. [Facilitator](../glossary.md#facilitator) fees: unknown | Payment happens inside the request: the server asks, the client pays and retries | The spec's examples settle in USDC on blockchain networks; what the person approves depends on the agent or wallet and is unknown | [^pm-15][^pm-14] |

## What should you look for in an agent payment protocol?

Start with the job: proving consent, running a checkout, or paying per request. Then check who maintains the protocol, how mature it is, which payment methods it carries and what the person approves.

- **The job it does.** Consent records, checkout or per-request payment.
- **Who maintains it.** A company, a pair of companies or a foundation.
- **Maturity.** Beta, a numbered version, or reference code only.
- **Payment methods.** Cards, bank transfers, [stablecoins](../glossary.md#stablecoin) or several.
- **What the person approves.** Whether the protocol itself records approval, or leaves it to the agent or app.
- **How agents reach it.** For example through [MCP](../glossary.md#mcp) or [A2A](../glossary.md#a2a).

## How did we compare them?

We read each protocol's own documentation, specification and code repository, and checked them again on November 17, 2026. Every cell in the table comes from those official pages. Where they say nothing, the page says unknown, and outside explainers are not used as evidence.

## What does AP2 do?

AP2 carries signed proof of what a person authorized an agent to buy. It uses [mandates](../glossary.md#mandates): a Checkout Mandate shared with the merchant and a Payment Mandate shared with the credential provider, the card networks and the merchant's payment processor.[^pm-13]

- Each mandate has an open stage, which holds the person's limits and goals before a cart is final, such as a budget or allowed payment methods, and a closed stage, which approves one finalized checkout and amount.[^pm-13]
- The mandates chain together into an audit trail, whether or not the person is present at checkout.[^pm-13]
- The first version supports "pull" payment methods such as credit and debit cards. The roadmap includes e-wallets, "push" payments such as real-time bank transfers, and digital currencies.[^pm-13]
- AP2 is available as an extension for A2A and for Universal Commerce Protocol.[^pm-13]
- Google publishes reference code and samples in Python, Go and Android.[^pm-12] AP2's documentation says standardization will continue in FIDO Alliance working groups.[^pm-13]

More detail: [AP2](../payments/ap2.md).

## What does ACP do?

ACP lets a buyer's AI agent complete a purchase from a business. OpenAI and Stripe maintain the specification, and it is in beta.[^pm-07]

- It has a checkout API for businesses and a separate delegated-payment spec, both published as [OpenAPI](../glossary.md#openapi) files.[^pm-07]
- An AI app can let users buy directly from businesses without being the merchant of record.[^pm-07]
- Versions are dated. The first release is dated 2025-09-29, and the 2026-04-17 version adds cart, feed, orders, authentication and MCP.[^pm-07]
- OpenAI and Stripe were the first to implement it.[^pm-07] Stripe also offers shared payment tokens with usage and expiry limits for agent purchases.[^pm-08] See [Stripe](../payments/stripe.md).

More detail: [Agentic Commerce Protocol (ACP)](../payments/agentic-commerce-protocol.md).

## What does x402 do?

x402 lets a client, such as an agent, pay for a web resource as part of the request. If no valid payment is attached, the server replies with a payment-required signal and its terms, and the client sends the request again with a payment.[^pm-15]

- A facilitator can verify the payment and settle it on a blockchain for the website.[^pm-15]
- The spec names several payment schemes, including `exact`, `upto` and `batch-settlement`, and transports including HTTP, MCP and A2A.[^pm-15]
- The project says it aims to support all networks, crypto and fiat, and forms of value including stablecoins, tokens and fiat.[^pm-14]
- The x402 Foundation publishes the code and the specification.[^pm-14]

More detail: [x402](../payments/x402.md).

## Can AP2, ACP and x402 work together?

AP2 and x402 can. AP2's documentation includes a sample in which an agent pays with x402 while the person is not present, so AP2 records the consent and x402 makes the payment.[^pm-13] Whether ACP is combined with AP2 or x402 in production is unknown.

## How do you choose between AP2, ACP and x402?

Choose by the job, not by the company behind it. Each protocol answers a different question, and one purchase can involve more than one.

- **You sell goods or services and want AI apps to sell them for you:** ACP is the checkout spec built for that.[^pm-07]
- **You charge per request for data, an API or a tool:** x402 is built for paying inside the request.[^pm-15]
- **You need proof of what a person authorized, for example for purchases made while they are away:** AP2 records that as signed mandates.[^pm-13]

This is a factual comparison of published specifications, not investment, legal or tax advice.

## Frequently asked questions

### Does AP2 move money itself?

No cited source says it does. AP2 carries signed mandates, and the Payment Mandate authorizes a payment against a specific payment instrument that the credential provider, the card networks and the payment processor handle.[^pm-13]

### Is x402 only for crypto?

Not by design. x402 says it aims to support crypto and fiat networks alike,[^pm-14] but the specification's own examples pay in USDC on blockchain networks.[^pm-15]

### Who maintains AP2, ACP and x402?

OpenAI and Stripe maintain ACP.[^pm-07] The x402 Foundation publishes x402.[^pm-14] Google publishes AP2's reference code, and AP2's documentation says standardization will continue in FIDO Alliance working groups.[^pm-12][^pm-13]

### Do AP2, ACP and x402 work with MCP?

All three describe MCP support, but our sources show no official hosted MCP server for any of them. AP2's documentation calls it an open extension for A2A and MCP,[^pm-13] ACP's 2026-04-17 version adds MCP,[^pm-07] and the x402 spec lists MCP as a transport.[^pm-15]

### What does the person approve before an agent pays?

Under AP2, the person's limits and approvals are recorded in mandates.[^pm-13] The ACP and x402 sources do not say, so it depends on the agent, wallet or app and is unknown here. For example, AgentBank asks its owner to review the service, amount and payee before an x402 payment.[^ag-01]

### Which companies use AP2, ACP or x402?

OpenAI and Stripe were the first to implement ACP,[^pm-07] and Visa lists ACP among the agent protocols its Intelligent Commerce Connect accepts.[^pm-04] Coinbase for Agents lets an agent pay for data and research with x402 from a USDC balance,[^cb-01] and AgentBank lets an agent pay x402 services.[^ag-01] Which payment networks and wallets use AP2 in production is unknown.

## Sources

[^pm-13]: [AP2 - Agent Payments Protocol Documentation](../sources/pm-13.md). AP2 Protocol, official, retrieved 2026-11-12.
[^pm-07]: [GitHub - agentic-commerce-protocol/agentic-commerce-protocol: The Agentic Commerce Protocol (ACP) is an interaction model and open standard for connec](../sources/pm-07.md). ACP (GitHub), official, retrieved 2026-11-12.
[^pm-15]: [x402 specification v2](../sources/pm-15.md). x402 Foundation (GitHub), official, retrieved 2026-11-12.
[^pm-12]: [GitHub - google-agentic-commerce/AP2: Building a Secure and Interoperable Future for AI-Driven Payments. · GitHub](../sources/pm-12.md). Google (GitHub), official, retrieved 2026-11-12.
[^pm-14]: [GitHub - x402-foundation/x402: A payments protocol for the internet. Built on HTTP. · GitHub](../sources/pm-14.md). x402 Foundation (GitHub), official, retrieved 2026-11-12.
[^pm-08]: [Shared payment tokens - Stripe Documentation](../sources/pm-08.md). Stripe Docs, official, retrieved 2026-11-12.
[^ag-01]: [Connect your AI agent to real-world money - AgentBank](../sources/ag-01.md). AgentBank, official, retrieved 2026-11-19.
[^pm-04]: [Visa Opens the Door to AI-Driven Shopping for Businesses Worldwide - Visa](../sources/pm-04.md). Visa, official, retrieved 2026-11-12.
[^cb-01]: [Coinbase MCP - Coinbase Developer Documentation](../sources/cb-01.md). Coinbase Developer Platform, official, retrieved 2026-11-12.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20analyses%2Fap2-vs-acp-vs-x402.md&body=Page%3A%20analyses%2Fap2-vs-acp-vs-x402.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
