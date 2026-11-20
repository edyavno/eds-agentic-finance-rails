---
type: payment
id: visa-intelligent-commerce
title: Visa Intelligent Commerce
summary: 'Visa''s agent payments program: approved agent builders get tokenized Visa credentials, network-level controls and consumer-approved purchase instructions.'
page_status: current
last_verified: '2026-11-20'
kind: card-network-program
operator: Visa
agent_can: Buy things for a consumer with tokenized Visa credentials, under purchase instructions the consumer approved
user_controls: Consumer-approved purchase instructions, Visa Payment Passkeys with device binding, and network-level controls
mcp_server: 'yes'
endpoint: unknown
availability: 'Production needs Visa onboarding and approval at each stage: sandbox, certification, production. Intelligent Commerce Connect was in pilot with select partners as of 2026-04-08'
field_sources:
  operator:
  - pm-01
  agent_can:
  - pm-01
  user_controls:
  - pm-01
  mcp_server:
  - pm-02
  - pm-01
  availability:
  - pm-01
  - pm-04
---

# Visa Intelligent Commerce

Visa Intelligent Commerce (VIC) lets agent providers, wallet providers and agent enablers buy things for consumers with Visa credentials. Visa says it provides network-level controls, consumer-approved purchase instructions, agent validation and tokenized payment credentials.[^pm-01] See [payment token](../glossary.md#payment-token).

## Who can use it

- Production access needs onboarding to VIC and approval as a participant. Visa also lists onboarding to its Trusted Agent Protocol, Visa Token Service and Visa Payment Passkeys, and registration in the Visa Agent Registry Service.[^pm-01]
- Only tokenizable credit, debit and prepaid cards enrolled in Visa's Cloud Token Framework qualify.[^pm-01]
- Every integration moves from sandbox to certification to production, with Visa approval at each step.[^pm-01]

## How an agent connects

- Visa's general Developer MCP lets builders search Visa docs and API references. Separate product MCP servers connect agents to Visa products, and VIC is listed as one.[^pm-02]
- The VIC docs describe an [MCP](../glossary.md#mcp) integration with the [sandbox](../glossary.md#sandbox) host `sandbox.mcp.visa.com`, or direct API calls.[^pm-01]
- A production MCP address is not in the cited sources, so the endpoint is unknown.

## Intelligent Commerce Connect

On 2026-04-08, Visa announced Intelligent Commerce Connect as part of VIC. Visa says one integration covers payment initiation, tokenization, spend controls and authentication, and lets agents pay with Visa and non-Visa cards. It names agent protocols it accepts, including Trusted Agent Protocol, Machine Payments Protocol (MPP), ACP and Universal Commerce Protocol (UCP). At launch it was in pilot with select partners.[^pm-04]

## What is Agentic Ready?

[Agentic Ready](../glossary.md#agentic-ready) is a Visa program, part of Visa Intelligent Commerce, where participants test agent-initiated transactions that use agentic network tokens.[^pm-26] Issuers joined first: Visa says 175+ issuers across 45 markets take part and test with their own credit and debit cards.[^pm-26]

On 2026-11-17 Visa opened it to the acceptance side: merchants, B2B suppliers, payment providers, acquirers and commerce platforms. It launched with more than 140 participants, and Visa expects more financial institutions, merchants and enablers to join through 2027.[^pm-26] Visa says participants test how agent-initiated transactions can be recognized, authenticated and processed on the payment infrastructure they already use.[^pm-26]

Visa issued a corrected release on 2026-11-19 that replaces its release of 2026-11-17.[^pm-26] The correction adds J.P. Morgan Payments to the subhead and after the 11th paragraph.[^pm-26] The release it replaced is the 2026-11-17 version, which the Agentic Ready paragraph above first relied on.[^pm-16]

### Agentic Ready in Europe

On 2026-11-18 Visa announced the expansion of Agentic Ready to the acceptance ecosystem in Europe, in a release datelined London.[^pm-25]

- It launched with more than 85 acceptance participants across Europe, including Adyen, Barclaycard Payments, Checkout.com, Global Payments, Nuvei, PayPal, Stripe and Worldline.[^pm-25]
- Merchants, payment service providers and acquirers can join the 40+ European issuers already taking part.[^pm-25]
- Visa says the framework supports agentic transactions on both consumer and commercial cards, and lays a foundation for agentic B2B services and payments.[^pm-25]
- Visa says the Visa Acceptance Platform complements the expanded programme with capabilities across the payment lifecycle, including omnichannel acceptance, credential management, fraud protection and dispute management.[^pm-25]
- Visa expects more financial institutions, merchants and enablers to join throughout 2027.[^pm-25]
- The release does not say whether the European participants are counted in the 140 or more in the global release, so that is unknown.

## Who says they work with it

- OpenAI says it built [ChatGPT Wallet](chatgpt-wallet.md) in partnership with American Express, Mastercard and Visa. It does not say whether Wallet uses Visa Intelligent Commerce.[^oa-01]
- Rain says its [Agent Vaults](rain-agent-vaults.md) support Visa Intelligent Commerce.[^rn-01]
- Visa names Adyen, Antom, Billtrust, Checkout.com, Fiserv, Global Payments, PayPal and Stripe among the initial Agentic Ready participants.[^pm-26] Stripe says it is testing ways to recognize agent-initiated payments, and PayPal says it is expanding acceptance of Visa agentic tokens across its merchant network.[^pm-26] See [Stripe](stripe.md) and [PayPal](paypal.md).
- Visa's corrected release names J.P. Morgan Payments among the initial participants.[^pm-26] It says J.P. Morgan Payments and Visa are collaborating to define how agentic payments should work across the acceptance ecosystem. They are testing and refining processing requirements and standards for agent-initiated transactions, including how agentic network tokens and associated Trusted Agent Protocol signals move across merchant, acquiring and network infrastructure.[^pm-26]
- AXS, a Singapore bill payment network, says Visa will show Visa Intelligent Commerce connecting AI agents to AXS's MCP server to complete everyday bill payments, using an agentic token.[^ax-01] See [Agent payments](../rails/agent-payments.md#can-an-agent-pay-bills).
- Replit says its Agent buys business supplies with Link and Visa. Replit says Link facilitates the transaction scoped to the approved purchase, while Visa provides trusted payment infrastructure and capabilities designed to support secure agent-initiated transactions.[^rp-01] See [Link wallet for agents](link-wallet-for-agents.md).

## Related

- Visa's Trusted Agent Protocol, on [agent identity](../rails/agent-identity.md).[^pm-03]
- [Agentic Commerce Protocol (ACP)](agentic-commerce-protocol.md).
- All programs: [Payments](README.md).

## Unknown

Fees, the consumer AI apps that support VIC today, a production MCP address, and how many Agentic Ready participants are live in production. Whether the European participants are part of the global count is also unknown. No cited source confirms it, so the wiki says unknown.

## Sources

[^pm-01]: [Visa Developer Center](../sources/pm-01.md). Visa Developer, official, retrieved 2026-11-12.
[^pm-02]: [MCP docs - Visa Developer](../sources/pm-02.md). Visa Developer, official, retrieved 2026-11-12.
[^pm-04]: [Visa Opens the Door to AI-Driven Shopping for Businesses Worldwide - Visa](../sources/pm-04.md). Visa, official, retrieved 2026-11-12.
[^pm-26]: [CORRECTING and REPLACING Visa Expands Agentic Ready to Help Scale Trusted AI Commerce Globally](../sources/pm-26.md). Visa, official, retrieved 2026-11-20.
[^pm-16]: [Visa Expands Agentic Ready to Help Scale Trusted AI Commerce Globally](../sources/pm-16.md). Visa, official, retrieved 2026-11-18.
[^pm-25]: [Visa Expands Agentic Ready to Help Scale Trusted AI Commerce across Europe](../sources/pm-25.md). Visa (Visa UK newsroom), official, retrieved 2026-11-20.
[^oa-01]: [Introducing ChatGPT Wallet](../sources/oa-01.md). OpenAI, official, retrieved 2026-11-15.
[^rn-01]: [Rain Agent Vaults bring embedded payments to AI agents](../sources/rn-01.md). Rain, official, retrieved 2026-11-15.
[^ax-01]: [AXS Pioneers Agentic Bill Payments in South-East Asia, Opening Its Bill Payment Network to AI-Powered Partners](../sources/ax-01.md). AXS, official, retrieved 2026-11-20.
[^rp-01]: [Replit Agent can now buy for your business and help you reach customers](../sources/rp-01.md). Replit, official, retrieved 2026-11-20.
[^pm-03]: [GitHub - visa/trusted-agent-protocol: Establishing a universal standard of trust between AI agents and merchants for the next phase of agentic commerc](../sources/pm-03.md). Visa (GitHub), official, retrieved 2026-11-12.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20payments%2Fvisa-intelligent-commerce.md&body=Page%3A%20payments%2Fvisa-intelligent-commerce.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
