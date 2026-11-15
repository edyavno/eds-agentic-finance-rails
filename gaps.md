---
type: gaps
title: Gaps - what we do not know yet
summary: Open questions and missing sources, ranked.
page_status: current
last_verified: '2026-11-14'
---

# Gaps

This page lists what the wiki cannot answer yet. Items are added from unknown fields and reader feedback, and removed when a source closes them. Nothing here is a claim about the providers.

## Highest priority

1. **Terms and agreements: none collected.** Needed: Robinhood agentic disclosures and crypto agreement, IBKR Autonomous Trading terms, Coinbase agent terms, Webull and Public MCP terms.
2. **Limits.** IBKR AI Partition funding limits ("limits apply"),[^ib-02] Coinbase trade-size and spend rules (announced as coming soon),[^cb-07] and order rate limits for every provider.
3. **Paper trading for agents** at Robinhood, Coinbase, IBKR and Webull Cloud MCP.
4. **Order types** for Coinbase, Webull, IBKR and Alpaca agent orders.
5. **IBKR Autonomous Trading asset list.** An independent review found IBKR's descriptions inconsistent.[^ib-03]
6. **Primary statements from blockers.** The JPMorgan and Morgan Stanley evidence is from news reports.[^bl-01][^bl-02]
7. **Independent tests.** Only Robinhood and IBKR have independent write-ups in the batch.[^rh-02][^ib-03]

## Payments and personal money agents

- **Fees** for agent payments: none of the cited [payments](payments/README.md) sources give them.
- **Production MCP addresses** for Visa Intelligent Commerce and Mastercard Agent Pay, and whether Mastercard has an MCP at all.
- **Who approves what** under ACP and x402. It depends on the agent or wallet, and the cited specs do not say.
- **Primary sources** for [JPMorgan Smart Cash](personal-money/jpmorgan-smart-cash.md), which rests on one news report, and for most bank positions on [Banks and outside agents](personal-money/banks-and-outside-agents.md).
- **Whether Meta Muse can move money** or pay bills, and whether it offers developer access.

## Advisor agents

The [advisor agents](advisors/README.md) section is new and still thin: only Claude for Financial Advisors, Nitrogen, and Wells Fargo AI Teammate have pages so far. Official coverage of other advisor platforms, and of approval and access rules beyond the sources already cited, has not been collected yet.

## Unknown fields by provider

See the `unknown` values in [data/providers.csv](data/providers.csv) or the [directory](directory.md).

## Leads and other directories (not evidence)

These cards are prior art or competing directories. They are leads only: use them to find official sources, not to back a provider field or a factual claim about a broker or rail. Outbound referral or affiliate links from those sites are not reused here.

- Broker and finance MCP lists: awesome-broker-mcp,[^pa-01] awesome-finance-mcp,[^pa-02] awesome-finance-agent,[^pa-05] and the Finance & Fintech section of awesome-mcp-servers.[^pa-06]
- Agent-payments lists: awesome-payment-agent-skills[^pa-03] and awesome_mpp.[^pa-04]
- Other directories and explainers: FintechAI Directory,[^pa-07] Agentic Rails Atlas (Mastercard Agent Pay explainer),[^pa-08] AgentBroker Index (Fidelity page),[^pa-09] and The Agentic Trader (Interactive Brokers guide).[^pa-10]

## Sources

[^ib-02]: [Interactive Brokers Introduces Autonomous Trading](sources/ib-02.md). Interactive Brokers, official, retrieved 2026-11-12.
[^cb-07]: [Coinbase for Agents: Your AI Agent Can Now Trade and Pay with Coinbase](sources/cb-07.md). Coinbase, official, retrieved 2026-11-12.
[^ib-03]: [IBKR Autonomous Trading: What the AI Partition Lets an AI Trade Without Asking, Read Off IBKR's Pages — DeskTested](sources/ib-03.md). DeskTested, third-party, retrieved 2026-11-12.
[^bl-01]: [JPMorgan blocks outside AI agents like Muse, Instinct from account access](sources/bl-01.md). CNBC, third-party, retrieved 2026-11-12.
[^bl-02]: [Scoop: Unvetted AI agents are accessing U.S. bank accounts](sources/bl-02.md). Axios, third-party, retrieved 2026-11-12.
[^rh-02]: [Robinhood MCP Server: What 73 Tools and an OAuth Handshake Look Like Up Close — DeskTested](sources/rh-02.md). DeskTested, third-party, retrieved 2026-11-12.
[^pa-01]: [GitHub - mphinance/awesome-broker-mcp: Which brokers can an AI actually trade through? A verified directory of broker MCP servers — official vs commun](sources/pa-01.md). mphinance (GitHub), third-party, retrieved 2026-11-12.
[^pa-02]: [GitHub - BlockRunAI/awesome-finance-mcp: A curated list of MCP servers for AI finance agents · GitHub](sources/pa-02.md). BlockRunAI (GitHub), third-party, retrieved 2026-11-12.
[^pa-05]: [GitHub - macoloye/awesome-finance-agent: A curated list of finance agent SDKs, MCP tools, wallet infrastructure, safeguards, simulation systems, and s](sources/pa-05.md). macoloye (GitHub), third-party, retrieved 2026-11-12.
[^pa-06]: [awesome-mcp-servers: Finance & Fintech section](sources/pa-06.md). punkpeye (GitHub), third-party, retrieved 2026-11-12.
[^pa-03]: [GitHub - frankxai/awesome-payment-agent-skills: Web-first payment-agent skills: mandates, auth, settlement. Human spend cap required. · GitHub](sources/pa-03.md). frankxai (GitHub), third-party, retrieved 2026-11-12.
[^pa-04]: [GitHub - mpp-best/awesome_mpp: A curated list of open-source AI agent payment & x402 projects, SDKs and tools. Full directory at mpp.best · GitHub](sources/pa-04.md). mpp-best (GitHub), third-party, retrieved 2026-11-12.
[^pa-07]: [FintechAI Directory — AI Tools for Finance, Curated by Finance Professionals](sources/pa-07.md). FintechAI Directory, third-party, retrieved 2026-11-12.
[^pa-08]: [Mastercard Agent Pay explained: agentic tokens, Verifiable Intent and Know Your Agent - Agentic Rails Atlas](sources/pa-08.md). atlas.merces.ai, third-party, retrieved 2026-11-12.
[^pa-09]: [Fidelity Investments MCP: AI agent access (ChatGPT, Claude)](sources/pa-09.md). agentbrokerindex.com, third-party, retrieved 2026-11-12.
[^pa-10]: [How do I connect an AI agent to Interactive Brokers?](sources/pa-10.md). theagentictrader.com, third-party, retrieved 2026-11-12.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20gaps.md&body=Page%3A%20gaps.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
