---
type: payment
id: mastercard-agent-pay
title: Mastercard Agent Pay
summary: Mastercard's program for agent payments. Agents are registered and verified before they can pay, and they pay with agentic tokens. Merchants can verify agents with Web Bot Auth.
page_status: current
last_verified: '2026-11-19'
kind: card-network-program
operator: Mastercard
agent_can: Pay with agentic tokens once registered and verified, including through a merchant's normal card checkout form
user_controls: Mastercard says each transaction is checked against authenticated user intent and explicit consent before the action
mcp_server: unknown
endpoint: unknown
availability: unknown
field_sources:
  operator:
  - pm-05
  - pm-06
  agent_can:
  - pm-05
  - pm-06
  user_controls:
  - pm-05
---

# Mastercard Agent Pay

Mastercard says only registered agents can transact with Agent Pay, and that payments are traceable through Mastercard network tokens. It covers both consumer and business use cases.[^pm-05]

## How it works

- **Register the agent.** Mastercard's Agent Pay Acceptance Framework registers and verifies AI agents before they may transact on the network. Each agent is uniquely identified.[^pm-06]
- **Pay with an agentic token.** Agents pay with agentic tokens, which Mastercard describes as dynamic, cryptographically secure credentials.[^pm-06] See [payment token](../glossary.md#payment-token).
- **Merchants verify the agent.** Merchants can check an agent with the Web Bot Auth standard at their content delivery network. A verified agent can then submit a Dynamic Token Verification Code in a normal card checkout form.[^pm-06] More on [agent identity](../rails/agent-identity.md).
- **User intent.** Mastercard says every transaction is verified by authenticated user intent and explicit consent before an action is taken.[^pm-05] In a 2026-11-12 announcement, Mastercard describes [Verifiable Intent](../glossary.md#verifiable-intent) as the link between the customer's approval and the payment.[^pm-17]

The framework story is dated 2025-10-14.[^pm-06]

## What did the live flight purchase show?

On 2026-11-12, Mastercard, Travelport, Booked AI and Basis Theory announced a live purchase by an AI travel agent. The agent searched, booked, paid for and ticketed a flight without the customer leaving the conversation.[^pm-17]

- **Payment.** Agent Pay made the payment with a tokenized credential. The card itself sat in Basis Theory's vault, and the agent never saw the card number.[^pm-17]
- **Approval.** The customer approved the specific booking and amount before payment. Verifiable Intent linked that approval to the payment so it could be checked against the customer's instructions. Mastercard says a payment that did not match would not have proceeded, and a further purchase would need a new approval.[^pm-17]
- **Merchant.** The airline stayed the merchant and processed the payment itself, with no intermediary checkout.[^pm-17]

The airline is described only as "a major airline". The date of the transaction and the volume are not given, so they are unknown.[^pm-17]

## Does Mastercard have an MCP server?

Yes, but it is for developers and it serves documentation only. It is not Agent Pay. Mastercard Developers runs an official [MCP](../glossary.md#mcp) server that exposes product docs, API specs and guides as tools, so an AI assistant can answer questions about Mastercard's APIs.[^pm-19]

- **Address.** The remote server is at `https://developer.mcp.mastercard.com`. Mastercard recommends the remote option, which needs no local process. Its steps for ChatGPT say to choose "No Authentication" as the connection mechanism, so there is no sign-in.[^pm-19]
- **Cost and scope.** Mastercard says the MCP is exclusively for Mastercard Developers and the toolkit is completely free to use.[^pm-20]
- **Run it locally.** A local option runs with `npx -y @mastercard/developers-mcp`.[^pm-21] Mastercard says the local option suits agent developers or setups that need local tools or more customization.[^pm-19]
- **What the tools do.** The repository lists nine tools. They list Mastercard Developers services, fetch documentation and integration guides (including the OAuth and Open Finance guides), and list and describe API operations.[^pm-21] None of them is described as reading an account or moving money.
- **When it launched.** Mastercard's press release of 2025-09-10 announced the Agent Toolkit, which lets AI assistants and agentic tools access and interpret Mastercard's API documentation through an MCP server.[^pm-22]

This is the same kind of tool as [Plaid's developer MCP servers](../personal-money/plaid.md): it helps developers build, and it does not give an agent access to a person's money. Whether Agent Pay itself has an MCP server is unknown, so the `mcp_server` field above stays unknown.

## What is Agent Pay for Machines?

Agent Pay for Machines is a separate Mastercard offering, announced on 2026-10-20, that lets AI agents pay digital services such as AI models, data, computing power and APIs.[^pm-23] It builds on [x402](x402.md), an open protocol that lets digital services request payment online, and connects it with the Mastercard network.[^pm-23]

- **How a payment works.** A business gives an agent a job and a spending limit. When the agent reaches a paid service, the service answers "402 Payment Required". The agent creates a digitally signed payment voucher, a secure promise to pay within its approved limit. The provider verifies it and delivers the service.[^pm-23]
- **Who sets the limit.** Mastercard says businesses set the task, permissions and spending limit, and the agent transacts within those parameters rather than having unlimited spending authority.[^pm-23]
- **Early Access.** Mastercard says it is opening Early Access to developers: the first version of its buyer- and seller-side APIs, plus a toolkit, sandbox and documentation.[^pm-23]
- **Pilot partners.** Mastercard names Cloudflare, Ant International, AIsa, Base, BVNK, Coinbase and Hype as partners in its end-to-end pilots.[^pm-23] Coinbase's own agent payments are on its [provider page](../providers/coinbase.md).

Price, countries and how to join Early Access are unknown. The page does not say.

## What about Mastercard Open Finance US?

Mastercard's developer documentation describes Open Finance US as API-based services for secure financial data sharing in consumer and small business applications, which can power payments, money management and lending. In the United States it is provided by Finicity, a Mastercard company.[^pm-24] The same page lists the Agent Toolkit under "For AI coding agents".[^pm-24] It is a tool for developers. Whether an AI agent can use it on a consumer's behalf is unknown, because the page does not say.

## Who says they work with it

- OpenAI says it built [ChatGPT Wallet](chatgpt-wallet.md) in partnership with American Express, Mastercard and Visa. It does not say whether Wallet uses Agent Pay.[^oa-01]
- Rain says its [Agent Vaults](rain-agent-vaults.md) support Mastercard Agent Pay.[^rn-01]
- Travelport, Booked AI and Basis Theory took part in the live flight purchase above.[^pm-17]

## Unknown

Whether Agent Pay itself has an MCP server, any public endpoint, availability by country, and fees. Price, countries and how to join Agent Pay for Machines Early Access are also unknown. No cited source confirms them, so the wiki says unknown.

All programs: [Payments](README.md).

## Sources

[^pm-05]: [Mastercard Agent Pay: secure, scalable and trusted agentic AI](../sources/pm-05.md). Mastercard, official, retrieved 2026-11-12.
[^pm-06]: [Agentic token framework: Driving trusted AI transactions](../sources/pm-06.md). Mastercard, official, retrieved 2026-11-12.
[^pm-17]: [Travelport, Booked AI, Basis Theory, and Mastercard complete live end-to-end agentic flight purchase](../sources/pm-17.md). Mastercard, official, retrieved 2026-11-18.
[^pm-19]: [Mastercard Developers Agent Toolkit](../sources/pm-19.md). Mastercard Developers, official, retrieved 2026-11-19.
[^pm-20]: [Use the MCP SDK (Mastercard Developers Agent Toolkit FAQ)](../sources/pm-20.md). Mastercard Developers, official, retrieved 2026-11-19.
[^pm-21]: [GitHub - Mastercard/developers-agent-toolkit](../sources/pm-21.md). Mastercard (GitHub), official, retrieved 2026-11-19.
[^pm-22]: [Mastercard unveils new tools and collaborations to power smarter, safer agentic commerce](../sources/pm-22.md). Mastercard, official, retrieved 2026-11-19.
[^pm-23]: [What happens when AI agents start paying each other? Watch Mastercard Agent Pay for Machines in action](../sources/pm-23.md). Mastercard, official, retrieved 2026-11-19.
[^pm-24]: [Mastercard Open Finance US (Mastercard Developers documentation)](../sources/pm-24.md). Mastercard Developers, official, retrieved 2026-11-19.
[^oa-01]: [Introducing ChatGPT Wallet](../sources/oa-01.md). OpenAI, official, retrieved 2026-11-15.
[^rn-01]: [Rain Agent Vaults bring embedded payments to AI agents](../sources/rn-01.md). Rain, official, retrieved 2026-11-15.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20payments%2Fmastercard-agent-pay.md&body=Page%3A%20payments%2Fmastercard-agent-pay.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
