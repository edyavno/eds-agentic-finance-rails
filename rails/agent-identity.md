---
type: rail
title: Agent identity
summary: How agents can prove who they are to websites and merchants - signed HTTP requests, network-run trust protocols and proof-of-human delegation.
page_status: current
last_verified: '2026-11-27'
---

# Agent identity

Agents can prove who they are to websites and merchants by signing their web requests, as Web Bot Auth and the card-network programs built on it do, by carrying proof that a real person delegated them, or through on-chain identity registries.[^id-01][^pm-03][^pm-06][^id-04][^id-07] The table lists each approach.

| Approach | What it is | Sources |
|---|---|---|
| Web Bot Auth | IETF draft using HTTP Message Signatures for automated traffic | [^id-01] |
| Cloudflare signed agents | Verification of Web Bot Auth signatures for bots and agents | [^id-02][^id-03] |
| [Trusted Agent Protocol](../glossary.md#trusted-agent-protocol-tap) (Visa) | Agent identity to merchants via HTTP Message Signatures | [^pm-03] |
| Akamai and Visa TAP | Akamai's blog says agents registered with Visa TAP are identified in Akamai's bot directory, and that Akamai verifies TAP signatures at the edge against credentials tied to Visa's agent directory. These are Akamai's own claims | [^ak-01] |
| [Visa Agent Directory](../glossary.md#visa-agent-directory) / [Visa CLI](../payments/visa-cli.md) | Visa CLI, a Visa Crypto Labs product, registers a newly connected agent's signing key in the Visa Agent Directory after the owner passes a US Visa card check. Since 2026-11-18, new agents are listed in the production directory | [^pm-27][^pm-28] |
| Mastercard Agent Pay | Uses Web Bot Auth at the CDN to verify agents | [^pm-06] |
| Plaid Agent Detection | A financial company's check on whether a session is a person or an AI agent, and which AI provider, from device, behavior, automation and network signals. It detects agents rather than verifying a signed identity | [^pb-06] |
| OpenAI ChatGPT agents | OpenAI asks merchants to recognize its agents' signed requests with Web Bot Auth | [^oa-01] |
| World AgentKit | Proof-of-human delegation to agents, in beta | [^id-04] |
| ERC-8004 (Trustless Agents) | Draft Ethereum ERC for on-chain identity, reputation, and validation registries, so agents can be discovered and trusted across organizational boundaries without pre-existing trust. Status on the official page: Draft. | [^id-07] |
| Know Your Agent protocol (Monetary Authority of Singapore) | Planned. MAS says it will facilitate a protocol for banks and customer agents to exchange who the agent is, what authority and mandate it has, and what assurance exists about it. Text and date unknown | [^ma-01] |
| Agentic Negotiation Protocol (BNY) | BNY's framework for authorized agents from different firms to negotiate. BNY says it verifies participants and lets agents connect securely. Used in a Treasury bill pilot | [^bn-01] |
| Know Your Human (Sardine) | Sardine's method to tie the customer's own device to an agent's session with a short-lived link and a one-time code. Sardine's own claims | [^sd-01][^sd-02] |

## Why does agent identity matter for finance?

Banks in our sources say they block agents that log in with customer credentials or browser automation.[^bl-04][^bl-08] Signed, identifiable agent traffic is one way a provider could tell a sanctioned agent from an unvetted one.

[Agent Detection](../glossary.md#agent-detection) is the other side of the same problem. Plaid launched it on 2026-11-16 so that banks and fintechs can see whether a session is a person or an AI agent, and which AI provider the agent is linked to, even when the agent does not announce itself.[^pb-06]

ERC-8004 says payments are orthogonal to the protocol and not covered here, but it gives examples of how x402 payments can enrich feedback signals.[^id-07]

## What is Know Your Agent?

[Know Your Agent](../glossary.md#know-your-agent-kya) is a term for a bank or merchant learning who an agent is and what it may do. Two sources describe plans for it.

- The Monetary Authority of Singapore (MAS) says a bank does not know whether an agent acts on the customer's full authorisation and control, or within its mandate.[^ma-01]
- In the new phase of its [SAFR](../glossary.md#safr) work, MAS says it will facilitate the development of a Know Your Agent protocol for trusted information exchange between customer agents and financial institutions.[^ma-01]
- MAS lists what the exchange covers: who the agent is and whom it represents, what authority it has been given, what mandate it operates under, and what assurance exists about its provenance and reliability.[^ma-01]
- MAS says this gives banks the information to decide the terms and scope permitted to an agent, and to set up a dedicated secure channel for agent access.[^ma-01]
- MAS says it will work with industry on these common approaches and protocols.[^ma-01]
- In a separate release, NETS and Ant International say they will explore interoperability between Know-Your-Agent frameworks, to make onboarding more efficient and strengthen trust, accountability and risk visibility across both ecosystems.[^nt-01] See [Agent payments](agent-payments.md#is-there-an-agent-payment-protocol-for-mobile-wallets).
- The protocol's text, date and participants are unknown.

## How do merchants tell a person's agent from a bot?

Sardine says a shopping agent usually shops through a cloud browser in a data center, so a merchant sees a data center IP address and a headless browser. Sardine says these are signals often seen in card testing or credential stuffing attacks.[^sd-01] Sardine's [Know Your Human](../glossary.md#know-your-human-kyh) is its answer: it captures signals from the customer's own device and ties them to the agent's session.[^sd-01] Sardine says the agent passes a few extra HTTP headers to the merchant, which uses Sardine to retrieve the customer's device and IP signals.[^sd-02] These are Sardine's claims about its own product. See [Merchants and outside agents](../payments/merchants-and-outside-agents.md#what-does-sardine-say-about-agent-checkouts).

Akamai's blog says it verifies Visa TAP signatures at the edge, so a merchant can let a verified agent browse a catalog while checkout, login or account changes follow stricter rules. These are Akamai's own claims.[^ak-01]

Cloudflare Radar's Black Friday / Cyber Monday 2026 Spotlight, updated hourly, is a network-level look at personal-agent requests. When the page was read at about 1:17 PM ET (America/New_York) on 27 November 2026, it showed personal-agent share of requests up from 0.02% in the 1–7 October baseline to 0.05% in the last 7 days, 98.39% of personal-agent requests allowed and 1.61% blocked, and the United States as 75.4% of that global traffic. Requests to cart, payment and purchase pages were shown as all personal agents +535% versus the baseline, with Muse +919%, dots +148% and Gemini Tasks +784%.[^ra-01] Forter's own page, retrieved at about 1:16 PM ET the same day, reported that agentic orders on its merchant network so far that Cyber Week were 107 times a year earlier, and that 20% of agentic orders in the week of 16 November 2026 checked out through a commerce protocol. Those are Forter's vendor-reported figures.[^ft-01] See [Merchants and outside agents](../payments/merchants-and-outside-agents.md#what-do-holiday-traffic-reports-say-about-personal-agents).

## How do agents from different firms identify each other?

BNY says its [Agentic Negotiation Protocol](../glossary.md#agentic-negotiation-protocol-anp) verifies participants and allows them to connect securely, so the agents can exchange offers and counteroffers.[^bn-01] See [Institutional markets](institutional-markets.md).

## Sources

[^id-01]: [draft-ietf-webbotauth-httpsig-protocol-01 - HTTP Message Signatures for automated traffic](../sources/id-01.md). IETF, official, retrieved 2026-11-12.
[^pm-03]: [GitHub - visa/trusted-agent-protocol: Establishing a universal standard of trust between AI agents and merchants for the next phase of agentic commerc](../sources/pm-03.md). Visa (GitHub), official, retrieved 2026-11-12.
[^pm-06]: [Agentic token framework: Driving trusted AI transactions](../sources/pm-06.md). Mastercard, official, retrieved 2026-11-12.
[^id-04]: [Now available: AgentKit, Proof of Human for the agentic web](../sources/id-04.md). World, official, retrieved 2026-11-12.
[^id-07]: [ERC-8004: Trustless Agents](../sources/id-07.md). Ethereum Improvement Proposals, official, retrieved 2026-11-14.
[^id-02]: [Web Bot Auth · Cloudflare bot solutions docs](../sources/id-02.md). Cloudflare Docs, official, retrieved 2026-11-12.
[^id-03]: [The age of agents: cryptographically recognizing agent traffic - Cloudflare Blog](../sources/id-03.md). Cloudflare Blog, official, retrieved 2026-11-12.
[^ak-01]: [Make Holiday Shopping Agent-Ready with Visa TAP](../sources/ak-01.md). Akamai, official, retrieved 2026-11-25.
[^pm-27]: [Visa CLI docs: Introduction](../sources/pm-27.md). Visa CLI docs (Visa Crypto Labs), official, retrieved 2026-11-23.
[^pm-28]: [Visa CLI docs: What's live today](../sources/pm-28.md). Visa CLI docs (Visa Crypto Labs), official, retrieved 2026-11-23.
[^pb-06]: [Introducing Agent Detection: building trust in the age of agentic finance](../sources/pb-06.md). Plaid, official, retrieved 2026-11-18.
[^oa-01]: [Introducing ChatGPT Wallet](../sources/oa-01.md). OpenAI, official, retrieved 2026-11-15.
[^ma-01]: [Keynote address by the Managing Director of the Monetary Authority of Singapore at the Singapore FinTech Festival 2026](../sources/ma-01.md). Monetary Authority of Singapore, official, retrieved 2026-11-20.
[^bn-01]: [BNY and Microsoft Complete First Agentic Negotiation of a U.S. Treasury Trade](../sources/bn-01.md). BNY, official, retrieved 2026-11-20.
[^sd-01]: [Know Your Human (KYH): Fraud prevention for agentic commerce](../sources/sd-01.md). Sardine, official, retrieved 2026-11-20.
[^sd-02]: [Know Your Human (KYH) for Agentic Commerce - Sardine](../sources/sd-02.md). Sardine, official, retrieved 2026-11-20.
[^bl-04]: [Schwab CEO says firm is blocking rogue AI agents from client accounts  - InvestmentNews](../sources/bl-04.md). InvestmentNews, third-party, retrieved 2026-11-12.
[^bl-08]: [Five Major Banks Are Blocking AI Agents From Logging Into Customer Accounts](../sources/bl-08.md). Yahoo Finance, third-party, retrieved 2026-11-12.
[^nt-01]: [NETS and Ant International Deepen Partnership to Empower Singapore’s Businesses for a Future in Agentic Commerce with Agentic Mobile Protocol](../sources/nt-01.md). NETS (Network for Electronic Transfers), official, retrieved 2026-11-20.
[^ra-01]: [Personal agents are shopping this holiday season](../sources/ra-01.md). Cloudflare, official, retrieved 2026-11-27.
[^ft-01]: [Agentic BFCM: how AI agents shop Black Friday & Cyber Monday 2026](../sources/ft-01.md). Forter, official, retrieved 2026-11-27.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20rails%2Fagent-identity.md&body=Page%3A%20rails%2Fagent-identity.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
