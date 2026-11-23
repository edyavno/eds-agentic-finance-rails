---
type: rail
title: Mandates and data access
summary: Protocols that record what a user authorized an agent to do, and the US data-rights rule that may shape agent access to bank data.
page_status: current
last_verified: '2026-11-23'
---

# Mandates and data access

A [mandate](../glossary.md#mandates) records what a user authorized an agent to do, and AP2 is a payments protocol built on them.[^pm-13] On data access, the US personal financial data rights rule (CFPB Section 1033) went through a reconsideration notice in August 2025, and a November 2026 report says it could become a vehicle to regulate AI agents.[^pb-05][^pb-04]

## Which protocol uses mandates?

- **AP2 (Agent Payments Protocol):** a protocol for agent-initiated payments built on [mandates](../glossary.md#mandates), designed to work with A2A and [MCP](../glossary.md#mcp).[^pm-13] A reference implementation and samples are on GitHub.[^pm-12] Details: [AP2](../payments/ap2.md).

## What rules cover agent access to financial data?

- **CFPB Section 1033 (personal financial data rights):** the rule went through a reconsideration notice in August 2025.[^pb-05] A November 2026 report says the rule, then at OMB, could become a vehicle to regulate AI agents.[^pb-04]
- **Aggregators:** Plaid powers account connections for Meta's Muse agent.[^pb-01] Plaid says it built [Data Transparency Messaging](../glossary.md#data-transparency-messaging) into its Link screen to help customers stay in compliance with the 1033 rule, so people see which data types an app requests and why.[^pb-16] JPMorganChase and Plaid renewed their data access agreement on 2025-09-16. The release says it includes a pricing structure and does not give the price, which is unknown.[^jp-01] Plaid's own MCP servers are for dashboard diagnostics and a [sandbox](../glossary.md#sandbox) coding toolkit, not end-user account access.[^pb-02] A September 27, 2026 CNBC article covers Muse as a personal agent, including consumers giving the AI access to banking and credit card statements.[^pb-03] More in [Personal money agents](../personal-money/README.md), including [Meta Muse](../personal-money/meta-muse.md), [Plaid MCP servers](../personal-money/plaid.md) and [Banks and outside agents](../personal-money/banks-and-outside-agents.md).

## What have a regulator and two banks said about agent authority?

On 2026-11-19 the Monetary Authority of Singapore (MAS) spoke about who is responsible when an agent acts for a customer. Citi and Chase put their answer in their user agreements.

**MAS**, in a keynote at the Singapore FinTech Festival:

- MAS says a bank does not know whether an agent acts with the customer's full authorisation and control, or within its mandate and instructions. It asks who is responsible if an agent transacts incorrectly or beyond its instructions.[^ma-01]
- MAS says some users give agents their login credentials to financial accounts. It says it would not advise giving personal agents such access, as there is insufficient assurance of safety.[^ma-01]
- MAS says it published work earlier this year on Safeguards for Agentic Finance at Runtime ([SAFR](../glossary.md#safr)). Its lessons include bounded autonomy, clearly established identity and authority, clear and specific mandates (permissible actions, limits and conditions), and controls proportionate to authority.[^ma-01]
- In the new phase of SAFR, MAS says it will facilitate the development of a [Know Your Agent](../glossary.md#know-your-agent-kya) protocol for trusted information exchange between customer agents and financial institutions. See [Agent identity](agent-identity.md#what-is-know-your-agent).[^ma-01]
- MAS says it will also set up an agentic money sandbox with the Future of Finance Institute. It combines AI agents and programmable money in two use cases: corporate treasury management and payments services.[^ma-01]
- In the payments use case, MAS says participating banks or payments providers will verify the agent's identity and authority and apply risk controls before executing a transaction.[^ma-01]
- MAS says consumers and businesses need to keep meaningful control over the objectives, mandate and actions of their agents, and that autonomy has to be bounded.[^ma-01]
- The text, date and participants of the Know Your Agent protocol, and the start date of the sandbox, are unknown.

**Federal Reserve**, in a 16 November 2026 speech by Governor Michael S. Barr:

- Barr said major banks now report finding AI agents attempting to take actions in retail customer accounts, without the bank being able to verify authenticity, consent, and alignment with customer instructions.[^fr-01]
- He called for strict authentication, explicit consent verification for specific actions, and technical controls limiting agent capabilities.[^fr-01] The rest of the speech is about financial stability and is not used here.

**Citi and Chase**, in their own user agreements:

- Citi says that if a customer gives an outside AI agent their Online Credentials, Citi will consider the agent's access and actions authorized by the customer.[^ci-01]
- Chase says a customer who permits a third party, including External AI, to access their accounts is deemed to authorize that third party to transact in the account.[^jp-02]
- The details and what is unknown are on [Banks and outside agents](../personal-money/banks-and-outside-agents.md#what-do-the-citi-and-chase-user-agreements-say).

Rules and risk are background here, not a focus. A January 27, 2026 FINRA blog, "Emerging Trend in [GenAI](../glossary.md#genai): Observations on AI Agents," discusses member firms' use of AI agents.[^id-05] FINRA's 2026 Annual Regulatory Oversight Report has a GenAI section on emerging agent trends, describing AI agents as systems that can autonomously perform and complete tasks on behalf of a user.[^id-06]

## Sources

[^pm-13]: [AP2 - Agent Payments Protocol Documentation](../sources/pm-13.md). AP2 Protocol, official, retrieved 2026-11-12.
[^pb-05]: [Federal Register](../sources/pb-05.md). Federal Register, official, retrieved 2026-11-12.
[^pb-04]: [AI agents scramble banks' fight with fintechs](../sources/pb-04.md). POLITICO, third-party, retrieved 2026-11-12.
[^pm-12]: [GitHub - google-agentic-commerce/AP2: Building a Secure and Interoperable Future for AI-Driven Payments. · GitHub](../sources/pm-12.md). Google (GitHub), official, retrieved 2026-11-12.
[^pb-01]: [Plaid powers Meta's new AI agent, Muse - Plaid](../sources/pb-01.md). Plaid, official, retrieved 2026-11-12.
[^pb-16]: [Data Transparency Messaging migration guide (Plaid Docs)](../sources/pb-16.md). Plaid Docs, official, retrieved 2026-11-18.
[^jp-01]: [JPMorganChase and Plaid announce an extension to their data access agreement](../sources/jp-01.md). JPMorganChase, official, retrieved 2026-11-18.
[^pb-02]: [Resources - MCP Server - Plaid Docs](../sources/pb-02.md). Plaid Docs, official, retrieved 2026-11-12.
[^pb-03]: [Meta's Muse is attacking one of economy's most profitable weak spots](../sources/pb-03.md). CNBC, third-party, retrieved 2026-11-12.
[^ma-01]: [Keynote address by the Managing Director of the Monetary Authority of Singapore at the Singapore FinTech Festival 2026](../sources/ma-01.md). Monetary Authority of Singapore, official, retrieved 2026-11-20.
[^fr-01]: [Speech by Governor Barr: Some Potential Financial Stability Implications of Artificial Intelligence](../sources/fr-01.md). Board of Governors of the Federal Reserve System, official, retrieved 2026-11-23.
[^ci-01]: [Citi Online User Agreement (Section H: Use of Third-party AI Agents)](../sources/ci-01.md). Citi, official, retrieved 2026-11-20.
[^jp-02]: [Digital Services Agreement (J.P. Morgan Chase)](../sources/jp-02.md). JPMorgan Chase, official, retrieved 2026-11-20.
[^id-05]: [Emerging Trend in GenAI: Observations on AI Agents](../sources/id-05.md). FINRA, official, retrieved 2026-11-12.
[^id-06]: [GenAI: Continuing and Emerging Trends (FINRA 2026 oversight report)](../sources/id-06.md). FINRA, official, retrieved 2026-11-12.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20rails%2Fmandates-and-data-access.md&body=Page%3A%20rails%2Fmandates-and-data-access.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
