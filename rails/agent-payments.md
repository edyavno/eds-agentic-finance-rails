---
type: rail
title: Agent payments
summary: Starter overview of how agents pay - card-network agent programs, scoped payment tokens, open commerce protocols and HTTP 402 payments.
page_status: current
last_verified: '2026-11-23'
---

# Agent payments

AI agents pay through card-network programs, limited payment tokens, open commerce protocols and payments built into a web request.[^pm-01][^pm-05][^pm-08][^pm-07][^pm-14] The table lists each rail; every program also has its own page in [Payments](../payments/README.md).

| Rail | What it is | Sources |
|---|---|---|
| [Visa Intelligent Commerce](../payments/visa-intelligent-commerce.md) | Lets agent providers transact with Visa credentials, with network-level controls, consumer-approved instructions and tokenized credentials; an MCP is available | [^pm-01][^pm-02][^pm-04] |
| [Visa CLI](../payments/visa-cli.md) | After a US Visa card check, an agent gets a signing key, is listed in the [Visa Agent Directory](../glossary.md#visa-agent-directory), and can pay HTTP 402 requests in [OUSD](../glossary.md#ousd) within owner-set limits | [^pm-27][^pm-28] |
| [Mastercard Agent Pay](../payments/mastercard-agent-pay.md) | Registered, verified agents and agentic tokens | [^pm-05][^pm-06] |
| [Mastercard Agent Pay for Machines](../payments/mastercard-agent-pay.md#what-is-agent-pay-for-machines) | Agents pay digital services within a business-set spending limit, signing a payment voucher; builds on x402; Early Access for developers | [^pm-23] |
| [Mastercard Developers MCP](../payments/mastercard-agent-pay.md#does-mastercard-have-an-mcp-server) | Official MCP server for Mastercard's developer documentation; not a way to pay | [^pm-19][^pm-20] |
| [Agentic Commerce Protocol (ACP)](../payments/agentic-commerce-protocol.md) | Open standard for buyers, their agents and businesses; the spec is maintained by OpenAI and Stripe | [^pm-07] |
| [Stripe Shared Payment Tokens](../payments/stripe.md) | A scoped, expiring payment credential with usage limits for agent purchases | [^pm-08] |
| [Stripe Treasury for agents](../payments/stripe.md#treasury-for-agents) | Business accounts only, in public preview: agents can read financial data and, within limits the business sets, transfer funds, convert currencies and pay vendors | [^pm-30] |
| [PayPal Agent Ready](../payments/paypal.md#agent-ready) | Lets Braintree and PayPal merchants accept agent checkout on ChatGPT, Google AI Mode and Gemini over ACP or UCP | [^pm-32] |
| [Stripe MCP](../payments/stripe.md#stripe-mcp-server) | Official Stripe MCP server for API actions and knowledge search, at `https://mcp.stripe.com`, with OAuth or agent API keys | [^pm-09] |
| [PayPal MCP server and Agent Toolkit](../payments/paypal.md) | MCP server that runs locally or remotely | [^pm-10][^pm-11] |
| [x402](../payments/x402.md) | Open, HTTP-native payment standard built on HTTP 402 | [^pm-14][^pm-15] |
| [pay.sh](https://pay.sh/) | A client and gateway for x402 and MPP payments in stablecoins on Solana, launched 2026-05-05 by the Solana Foundation with Google Cloud | [^pm-33][^so-01] |
| [Amazon Bedrock AgentCore payments](../payments/agentcore-payments.md) | AWS service for agents to pay over x402 and MPP within per-session budgets. Since 2026-11-19 it can also pay AWS Marketplace sellers in US dollars on the AWS bill | [^aw-01][^aw-03] |
| [Lightspark Agent Accounts](../payments/lightspark-agent-accounts.md) | Accounts where an agent holds and spends money within limits and approvals the owner sets; pays Visa merchants with a card valid for one purchase | [^ls-01] |

## Which brokers also let agents pay?

- Coinbase for Agents lets an agent pay for data and research with x402 from a USDC balance.[^cb-01]
- Robinhood's Agentic Credit Card gives an agent a dedicated virtual card through Robinhood Banking's MCP server, with a spending limit you set and a choice of manual approvals.[^rh-10][^rh-09] Details: [Robinhood Agentic Credit Card](../payments/robinhood-agentic-credit-card.md).

For the three open protocols side by side, see [AP2 vs ACP vs x402](../analyses/ap2-vs-acp-vs-x402.md).

Each program has its own page, with a sourced record, in the [Payments](../payments/README.md) section. AP2, which records what a user authorized, is on [AP2](../payments/ap2.md).

## Can an agent pay bills?

In Singapore, AXS has opened its bill payment network to AI agents. AXS says it does this through its [MCP](../glossary.md#mcp) server.[^ax-01]

- AXS says the network covers more than 800 billing organisations in Singapore, with access to billing services being progressively rolled out.[^ax-01]
- AXS says Visa and Mastercard are working with it to bring agentic bill payments into their own ecosystems. It also names a pilot with the Grab AI Assistant, powered by Grab payments.[^ax-01]
- AXS says Visa and Mastercard will show their AI agents connecting to its MCP server at the Singapore FinTech Festival 2026. Visa's demonstration will use Visa Intelligent Commerce and an agentic token.[^ax-01] See [Visa Intelligent Commerce](../payments/visa-intelligent-commerce.md) and [Mastercard Agent Pay](../payments/mastercard-agent-pay.md).
- AXS says the solution is designed around four standards and frameworks: MCP, the Universal Commerce Protocol (UCP), [AP2](../payments/ap2.md), and the Monetary Authority of Singapore's [SAFR](../glossary.md#safr) (Safeguards for Agentic Finance at Runtime). AXS says SAFR guides safeguards such as payment limits, user approvals and transaction accountability.[^ax-01]
- AXS says the necessary user authorisations are built in.[^ax-01]
- Singapore's regulator says it will build on SAFR with a Know Your Agent protocol. See [Mandates and data access](mandates-and-data-access.md#what-have-a-regulator-and-two-banks-said-about-agent-authority).[^ma-01]
- AXS also says HSBC and Green Link Digital Bank are collaborating with it through the Monetary Authority of Singapore's PathFin.ai initiative. It says it is exploring with Green Link Digital Bank how agents can help business customers manage and pay bills.[^ax-01]
- The consumer launch date, the MCP address and the full list of agents that can use it are unknown.

## Is there an agent payment protocol for mobile wallets?

The Agentic Mobile Protocol ([AMP](../glossary.md#agentic-mobile-protocol-amp)) is an open payment protocol built by Ant International for digital wallets, super apps, smart devices and other mobile interfaces, so AI agents can execute payments. Ant International says it launched in April 2026.[^nt-01]

- NETS says that in September Ant International announced that 10 leading Alipay+ wallets and seven global acquiring partners were working with AMP on their own agentic commerce plans.[^nt-01]
- On 2026-11-19, NETS (Network for Electronic Transfers, which calls itself Singapore's leading payment services group) and Ant International signed a memorandum of understanding at the Singapore Fintech Festival 2026. It is to explore a collaboration around NETS' digital payments services and AMP.[^nt-01]
- NETS says it will become the first national payment rail to join AMP.[^nt-01]
- The two say they will explore letting NETS App wallet users give trusted authorisation for AI agents to start and complete payments through AMP, and NETS deploying AMP in its merchant acquiring infrastructure.[^nt-01]
- They also say they will explore interoperability between [Know Your Agent](../glossary.md#know-your-agent-kya) frameworks.[^nt-01]
- The agreement is to explore, not a launch. The release gives no dates and links no documentation, so those are unknown.

## Sources

[^pm-01]: [Visa Developer Center](../sources/pm-01.md). Visa Developer, official, retrieved 2026-11-12.
[^pm-05]: [Mastercard Agent Pay: secure, scalable and trusted agentic AI](../sources/pm-05.md). Mastercard, official, retrieved 2026-11-12.
[^pm-08]: [Shared payment tokens - Stripe Documentation](../sources/pm-08.md). Stripe Docs, official, retrieved 2026-11-12.
[^pm-07]: [GitHub - agentic-commerce-protocol/agentic-commerce-protocol: The Agentic Commerce Protocol (ACP) is an interaction model and open standard for connec](../sources/pm-07.md). ACP (GitHub), official, retrieved 2026-11-12.
[^pm-14]: [GitHub - x402-foundation/x402: A payments protocol for the internet. Built on HTTP. · GitHub](../sources/pm-14.md). x402 Foundation (GitHub), official, retrieved 2026-11-12.
[^pm-02]: [MCP docs - Visa Developer](../sources/pm-02.md). Visa Developer, official, retrieved 2026-11-12.
[^pm-04]: [Visa Opens the Door to AI-Driven Shopping for Businesses Worldwide - Visa](../sources/pm-04.md). Visa, official, retrieved 2026-11-12.
[^pm-27]: [Visa CLI docs: Introduction](../sources/pm-27.md). Visa CLI docs (Visa Crypto Labs), official, retrieved 2026-11-23.
[^pm-28]: [Visa CLI docs: What's live today](../sources/pm-28.md). Visa CLI docs (Visa Crypto Labs), official, retrieved 2026-11-23.
[^pm-06]: [Agentic token framework: Driving trusted AI transactions](../sources/pm-06.md). Mastercard, official, retrieved 2026-11-12.
[^pm-23]: [What happens when AI agents start paying each other? Watch Mastercard Agent Pay for Machines in action](../sources/pm-23.md). Mastercard, official, retrieved 2026-11-19.
[^pm-19]: [Mastercard Developers Agent Toolkit](../sources/pm-19.md). Mastercard Developers, official, retrieved 2026-11-19.
[^pm-20]: [Use the MCP SDK (Mastercard Developers Agent Toolkit FAQ)](../sources/pm-20.md). Mastercard Developers, official, retrieved 2026-11-19.
[^pm-30]: [Give your agents controlled access to analyze your data and move funds](../sources/pm-30.md). Stripe, official, retrieved 2026-11-23.
[^pm-32]: [Agent Ready overview - PayPal Developer](../sources/pm-32.md). PayPal Developer, official, retrieved 2026-11-23.
[^pm-09]: [Model Context Protocol (MCP) - Stripe Documentation](../sources/pm-09.md). Stripe Docs, official, retrieved 2026-11-19.
[^pm-10]: [MCP server quickstart guide - PayPal Developer](../sources/pm-10.md). PayPal Developer, official, retrieved 2026-11-12.
[^pm-11]: [Agent toolkit quickstart guide - PayPal Developer](../sources/pm-11.md). PayPal Developer, official, retrieved 2026-11-12.
[^pm-15]: [x402 specification v2](../sources/pm-15.md). x402 Foundation (GitHub), official, retrieved 2026-11-12.
[^pm-33]: [pay.sh](../sources/pm-33.md). pay.sh, official, retrieved 2026-11-23.
[^so-01]: [Solana Foundation Launches Pay.sh in Collaboration with Google Cloud](../sources/so-01.md). Solana Foundation, official, retrieved 2026-11-23.
[^aw-01]: [AWS Marketplace now supports agentic payments with AgentCore](../sources/aw-01.md). Amazon Web Services, official, retrieved 2026-11-20.
[^aw-03]: [Amazon Bedrock AgentCore payments: Enable secure microtransaction payments for AI agents](../sources/aw-03.md). Amazon Web Services (AgentCore Developer Guide), official, retrieved 2026-11-20.
[^ls-01]: [Lightspark Launches Agent Accounts for AI Agents to Make and Receive Payments](../sources/ls-01.md). Lightspark (via GlobeNewswire), official, retrieved 2026-11-20.
[^cb-01]: [Coinbase MCP - Coinbase Developer Documentation](../sources/cb-01.md). Coinbase Developer Platform, official, retrieved 2026-11-12.
[^rh-10]: [Robinhood is Now Open to Agents](../sources/rh-10.md). Robinhood, official, retrieved 2026-11-19.
[^rh-09]: [Agentic Credit Card - Robinhood](../sources/rh-09.md). Robinhood, official, retrieved 2026-11-19.
[^ax-01]: [AXS Pioneers Agentic Bill Payments in South-East Asia, Opening Its Bill Payment Network to AI-Powered Partners](../sources/ax-01.md). AXS, official, retrieved 2026-11-20.
[^ma-01]: [Keynote address by the Managing Director of the Monetary Authority of Singapore at the Singapore FinTech Festival 2026](../sources/ma-01.md). Monetary Authority of Singapore, official, retrieved 2026-11-20.
[^nt-01]: [NETS and Ant International Deepen Partnership to Empower Singapore’s Businesses for a Future in Agentic Commerce with Agentic Mobile Protocol](../sources/nt-01.md). NETS (Network for Electronic Transfers), official, retrieved 2026-11-20.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20rails%2Fagent-payments.md&body=Page%3A%20rails%2Fagent-payments.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
