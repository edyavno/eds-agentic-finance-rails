---
type: gaps
title: Gaps - what we do not know yet
summary: 'Open questions the wiki cannot answer yet, ranked: missing agent terms, order limits, paper trading and more, from unknown fields and reader feedback.'
page_status: current
last_verified: '2026-11-19'
---

# Gaps

The biggest open questions are the brokers' agent terms and agreements, none of which are collected yet, and the limits on agent orders. Items come from unknown fields, sources that need a second check and reader feedback, and are removed when a source closes them. Nothing here is a claim about the providers.

## Highest priority

1. **Terms and agreements: none collected.** Needed: Robinhood agentic disclosures and crypto agreement, IBKR Autonomous Trading terms, Coinbase agent terms, Webull, Public, Scalable Capital and Kraken MCP terms.
2. **Limits.** IBKR AI Partition funding limits ("limits apply"),[^ib-02] Coinbase trade-size and spend rules (announced as coming soon at launch,[^cb-07] since documented as available with the amounts set by each user,[^cb-10] while whether auto-stop cancels open orders is unknown), Public's hosted server (whether it has the 0.11.0 order gate with limits and confirmation),[^pu-11] Scalable Capital order size and spend limits, and order rate limits for every provider.
3. **Paper trading for agents** at Robinhood, Coinbase, IBKR, Webull Cloud MCP and Scalable Capital.
4. **Order types** for Coinbase, Webull, IBKR, Public and Scalable Capital agent orders. Alpaca's are now documented for its Trading MCP server.[^al-09]
5. **IBKR Autonomous Trading asset list.** An independent review found IBKR's descriptions inconsistent.[^ib-03]
6. **Primary statements from blockers.** The JPMorgan and Morgan Stanley evidence is from news reports.[^bl-01][^bl-02]
7. **Independent tests.** Only Robinhood and IBKR have independent write-ups in our sources.[^rh-02][^ib-03]

## Payments and personal money agents

- **Fees** for agent payments: none of the cited [payments](payments/README.md) sources give them.
- **Production MCP addresses** for Visa Intelligent Commerce and Mastercard Agent Pay, and whether Mastercard has an MCP at all.
- **Who approves what** under ACP and x402. It depends on the agent or wallet, and the cited specs do not say.
- **Primary sources** for [JPMorgan Smart Cash](personal-money/jpmorgan-smart-cash.md), which rests on one news report, and for most bank positions on [Banks and outside agents](personal-money/banks-and-outside-agents.md).
- **Whether Meta Muse can pay bills or send money from a bank account.** Meta's payments page names only Link by Stripe and a saved credit card for purchases. Whether it offers developer access is also unknown.
- **Whether OpenAI dots can read Finances data.** The dots pages read for this wiki do not mention Finances or Plaid.
- **Agent access to X Money beyond Grok Bot.** The plugin README describes Grok Bot, X's own help pages do not mention agents, and no source gives the separate agent limits.
- **Perplexity's own description of Personal CFO.** The wiki relies on Plaid's posts, because Perplexity's page could not be fetched.
- **The price in the JPMorgan and Plaid data agreement.** The press release says it includes a pricing structure but gives no figure.
- **Whether Chase's card block applies to agents that use ChatGPT Wallet.** The Wall Street Journal report on the block does not mention Wallet, and OpenAI's help page does not mention the block.[^bl-12][^oa-02]
- **Whether ChatGPT Wallet runs on** Visa Intelligent Commerce or Mastercard Agent Pay. OpenAI names the networks as partners but not the programs.[^oa-01]
- **Nous's own FCA status.** Nous names its FCA-regulated open banking provider, but no cited source says whether Nous itself is authorised or an appointed representative.[^ns-02]
- **Merchant rules beyond eBay, United, Target and Booking.com**, and whether eBay, United or Booking.com grant permission to any agent today.[^eb-01][^ua-02][^tg-01][^bk-01]
- **The airline, date and volume** in the live Mastercard Agent Pay flight purchase. The announcement names none of them.[^pm-17]

## Unknown fields by provider

See the `unknown` values in [data/providers.csv](data/providers.csv) or the [Trading](directory.md) page.

## Leads and other directories (not evidence)

These cards are prior art or competing directories. They are leads only: use them to find official sources, not to back a provider field or a factual claim about a broker or rail.

- Broker and finance MCP lists: awesome-broker-mcp,[^pa-01] awesome-finance-mcp,[^pa-02] awesome-finance-agent,[^pa-05] and the Finance & Fintech section of awesome-mcp-servers.[^pa-06]
- Agent-payments lists: awesome-payment-agent-skills[^pa-03] and awesome_mpp.[^pa-04]
- Other directories and explainers: FintechAI Directory,[^pa-07] Agentic Rails Atlas (Mastercard Agent Pay explainer),[^pa-08] AgentBroker Index (Fidelity page),[^pa-09] and The Agentic Trader (Interactive Brokers guide).[^pa-10]

## Sources

[^ib-02]: [Interactive Brokers Introduces Autonomous Trading](sources/ib-02.md). Interactive Brokers, official, retrieved 2026-11-12.
[^cb-07]: [Coinbase for Agents: Your AI Agent Can Now Trade and Pay with Coinbase](sources/cb-07.md). Coinbase, official, retrieved 2026-11-12.
[^cb-10]: [Coinbase for Agents introduces new Agent Controls](sources/cb-10.md). Coinbase, official, retrieved 2026-11-18.
[^pu-11]: [Enforce preflight and user confirmation on every order — 0.11.0 (pull request 19)](sources/pu-11.md). Public.com (GitHub), official, retrieved 2026-11-18.
[^al-09]: [Trading API MCP](sources/al-09.md). Alpaca Docs, official, retrieved 2026-11-19.
[^ib-03]: [IBKR Autonomous Trading: What the AI Partition Lets an AI Trade Without Asking, Read Off IBKR's Pages — DeskTested](sources/ib-03.md). DeskTested, third-party, retrieved 2026-11-12.
[^bl-01]: [JPMorgan blocks outside AI agents like Muse, Instinct from account access](sources/bl-01.md). CNBC, third-party, retrieved 2026-11-12.
[^bl-02]: [Scoop: Unvetted AI agents are accessing U.S. bank accounts](sources/bl-02.md). Axios, third-party, retrieved 2026-11-12.
[^rh-02]: [Robinhood MCP Server: What 73 Tools and an OAuth Handshake Look Like Up Close — DeskTested](sources/rh-02.md). DeskTested, third-party, retrieved 2026-11-12.
[^bl-12]: [AI bots are using credit cards. Banks are racing to keep up. (The Wall Street Journal, via Mint)](sources/bl-12.md). The Wall Street Journal (syndicated on Mint), third-party, retrieved 2026-11-19.
[^oa-02]: [Making purchases with ChatGPT Wallet](sources/oa-02.md). OpenAI Help Center, official, retrieved 2026-11-19.
[^oa-01]: [Introducing ChatGPT Wallet](sources/oa-01.md). OpenAI, official, retrieved 2026-11-15.
[^ns-02]: [Terms of use - Nous](sources/ns-02.md). Nous, official, retrieved 2026-11-15.
[^eb-01]: [User Agreement - eBay](sources/eb-01.md). eBay, official, retrieved 2026-11-15.
[^ua-02]: [Unauthorized third-party AI agents or assistants - United Airlines](sources/ua-02.md). United Airlines, official, retrieved 2026-11-15.
[^tg-01]: [Terms & Conditions : Target](sources/tg-01.md). Target, official, retrieved 2026-11-18.
[^bk-01]: [Booking.com: Terms and Conditions (Customer terms of service)](sources/bk-01.md). Booking.com, official, retrieved 2026-11-18.
[^pm-17]: [Travelport, Booked AI, Basis Theory, and Mastercard complete live end-to-end agentic flight purchase](sources/pm-17.md). Mastercard, official, retrieved 2026-11-18.
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
