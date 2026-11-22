---
type: gaps
title: Gaps - what we do not know yet
summary: 'Open questions the wiki cannot answer yet, ranked: missing agent terms, order limits, paper trading and more, from unknown fields and reader feedback.'
page_status: current
last_verified: '2026-11-20'
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
   - Citi's and Chase's own user agreements are now cited on [Banks and outside agents](personal-money/banks-and-outside-agents.md#what-do-the-citi-and-chase-user-agreements-say).[^ci-01][^jp-02] The day each changed is unknown. Bank of America, Citizens and PNC are known only from a TechCrunch report, and PNC's wording is unknown.[^tc-01]
7. **Independent tests.** Only Robinhood and IBKR have independent write-ups in our sources.[^rh-02][^ib-03]

## Payments and personal money agents

- **Fees** for agent payments: none of the cited [payments](payments/README.md) sources give them.
- **Production MCP addresses** for Visa Intelligent Commerce and Mastercard Agent Pay. Mastercard does have an official MCP server, but it serves developer documentation only, so whether Agent Pay has an MCP for payments is still unknown.[^pm-19][^pm-20] See [Mastercard Agent Pay](payments/mastercard-agent-pay.md#does-mastercard-have-an-mcp-server).
- **Agent Pay for Machines.** Price, countries and how to join Early Access are not stated on Mastercard's announcement page.[^pm-23]
- **Mastercard Open Finance US.** Whether an AI agent can use it on a consumer's behalf. Mastercard's developer page does not say.[^pm-24]
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
- **Know Your Agent protocol.** The Monetary Authority of Singapore says it will facilitate one. Its speech gives no protocol text, date or participants, and no start date for its agentic money sandbox.[^ma-01]
- **Amazon Bedrock AgentCore payments.** The list of AWS Regions and the prices are not in the pages read. The pages do not describe a per-purchase approval step beyond the session budget.[^aw-01][^aw-02][^aw-03] See [AgentCore payments](payments/agentcore-payments.md).
- **Lightspark Agent Accounts.** Price, the countries where consumers can use it, and the MCP address.[^ls-01][^ls-02] See [Lightspark Agent Accounts](payments/lightspark-agent-accounts.md).
- **The Ant International coffee purchase on Agent Pay.** The date, amount, merchant and country are not given. Mastercard's 2026-11-19 text says Agent Pay for Machines was "Introduced in June this year", while the Mastercard page the wiki cites for it is dated 2026-10-20, and the two are not reconciled.[^an-01][^pm-23]
- **AXS agentic bill payments.** The consumer launch date, the MCP address, and which agents can use it beyond those AXS names.[^ax-01]
- **NETS and Ant International's AMP.** The agreement is a memorandum of understanding to explore. No dates or documentation are given.[^nt-01]
- **Coinbase Advisor.** Availability beyond select Coinbase One subscribers, and whether Coinbase's Agent Controls apply to it.[^cb-11][^cb-12]
- **Visa Agentic Ready in Europe.** Whether the 85 or more European acceptance participants are part of the 140 or more in Visa's global figure.[^pm-25][^pm-26]
- **Sardine Know Your Human.** No independent test, and no merchant or agent is named as using it.[^sd-01][^sd-02]
- **Replit Agent purchases with Link and Visa.** Price, countries beyond the US, and whether Link's purchase protections apply.[^rp-01]
- **BNY and Microsoft's Treasury bill negotiation.** The bill's tenor, size and price, the date of the trade itself, and any public specification for BNY's Agentic Negotiation Protocol.[^bn-01] See [Institutional markets](rails/institutional-markets.md).

## Unknown fields by provider

See the `unknown` values in [data/providers.csv](data/providers.csv) or the [Trading](trading.md) page.

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
[^ci-01]: [Citi Online User Agreement (Section H: Use of Third-party AI Agents)](sources/ci-01.md). Citi, official, retrieved 2026-11-20.
[^jp-02]: [Digital Services Agreement (J.P. Morgan Chase)](sources/jp-02.md). JPMorgan Chase, official, retrieved 2026-11-20.
[^tc-01]: [More banks say customers using AI agents are on their own — even if they get hacked (TechCrunch)](sources/tc-01.md). TechCrunch, third-party, retrieved 2026-11-20.
[^rh-02]: [Robinhood MCP Server: What 73 Tools and an OAuth Handshake Look Like Up Close — DeskTested](sources/rh-02.md). DeskTested, third-party, retrieved 2026-11-12.
[^pm-19]: [Mastercard Developers Agent Toolkit](sources/pm-19.md). Mastercard Developers, official, retrieved 2026-11-19.
[^pm-20]: [Use the MCP SDK (Mastercard Developers Agent Toolkit FAQ)](sources/pm-20.md). Mastercard Developers, official, retrieved 2026-11-19.
[^pm-23]: [What happens when AI agents start paying each other? Watch Mastercard Agent Pay for Machines in action](sources/pm-23.md). Mastercard, official, retrieved 2026-11-19.
[^pm-24]: [Mastercard Open Finance US (Mastercard Developers documentation)](sources/pm-24.md). Mastercard Developers, official, retrieved 2026-11-19.
[^bl-12]: [AI bots are using credit cards. Banks are racing to keep up. (The Wall Street Journal, via Mint)](sources/bl-12.md). The Wall Street Journal (syndicated on Mint), third-party, retrieved 2026-11-19.
[^oa-02]: [Making purchases with ChatGPT Wallet](sources/oa-02.md). OpenAI Help Center, official, retrieved 2026-11-19.
[^oa-01]: [Introducing ChatGPT Wallet](sources/oa-01.md). OpenAI, official, retrieved 2026-11-15.
[^ns-02]: [Terms of use - Nous](sources/ns-02.md). Nous, official, retrieved 2026-11-15.
[^eb-01]: [User Agreement - eBay](sources/eb-01.md). eBay, official, retrieved 2026-11-15.
[^ua-02]: [Unauthorized third-party AI agents or assistants - United Airlines](sources/ua-02.md). United Airlines, official, retrieved 2026-11-15.
[^tg-01]: [Terms & Conditions : Target](sources/tg-01.md). Target, official, retrieved 2026-11-18.
[^bk-01]: [Booking.com: Terms and Conditions (Customer terms of service)](sources/bk-01.md). Booking.com, official, retrieved 2026-11-18.
[^pm-17]: [Travelport, Booked AI, Basis Theory, and Mastercard complete live end-to-end agentic flight purchase](sources/pm-17.md). Mastercard, official, retrieved 2026-11-18.
[^ma-01]: [Keynote address by the Managing Director of the Monetary Authority of Singapore at the Singapore FinTech Festival 2026](sources/ma-01.md). Monetary Authority of Singapore, official, retrieved 2026-11-20.
[^aw-01]: [AWS Marketplace now supports agentic payments with AgentCore](sources/aw-01.md). Amazon Web Services, official, retrieved 2026-11-20.
[^aw-02]: [Enable AI agents to pay for AWS Marketplace x402 products with Amazon Bedrock AgentCore payments](sources/aw-02.md). Amazon Web Services (AWS Machine Learning Blog), official, retrieved 2026-11-20.
[^aw-03]: [Amazon Bedrock AgentCore payments: Enable secure microtransaction payments for AI agents](sources/aw-03.md). Amazon Web Services (AgentCore Developer Guide), official, retrieved 2026-11-20.
[^ls-01]: [Lightspark Launches Agent Accounts for AI Agents to Make and Receive Payments](sources/ls-01.md). Lightspark (via GlobeNewswire), official, retrieved 2026-11-20.
[^ls-02]: [Agent Accounts (Lightspark documentation)](sources/ls-02.md). Lightspark (documentation), official, retrieved 2026-11-20.
[^an-01]: [Mastercard and Ant International Advance Trusted Agentic Commerce in Asia Pacific (Ant International page)](sources/an-01.md). Mastercard (posted by Ant International), official, retrieved 2026-11-20.
[^ax-01]: [AXS Pioneers Agentic Bill Payments in South-East Asia, Opening Its Bill Payment Network to AI-Powered Partners](sources/ax-01.md). AXS, official, retrieved 2026-11-20.
[^nt-01]: [NETS and Ant International Deepen Partnership to Empower Singapore’s Businesses for a Future in Agentic Commerce with Agentic Mobile Protocol](sources/nt-01.md). NETS (Network for Electronic Transfers), official, retrieved 2026-11-20.
[^cb-11]: [Coinbase Advisor](sources/cb-11.md). Coinbase, official, retrieved 2026-11-20.
[^cb-12]: [System Update: Take control of your money with Coinbase](sources/cb-12.md). Coinbase, official, retrieved 2026-11-20.
[^pm-25]: [Visa Expands Agentic Ready to Help Scale Trusted AI Commerce across Europe](sources/pm-25.md). Visa (Visa UK newsroom), official, retrieved 2026-11-20.
[^pm-26]: [CORRECTING and REPLACING Visa Expands Agentic Ready to Help Scale Trusted AI Commerce Globally](sources/pm-26.md). Visa, official, retrieved 2026-11-20.
[^sd-01]: [Know Your Human (KYH): Fraud prevention for agentic commerce](sources/sd-01.md). Sardine, official, retrieved 2026-11-20.
[^sd-02]: [Know Your Human (KYH) for Agentic Commerce - Sardine](sources/sd-02.md). Sardine, official, retrieved 2026-11-20.
[^rp-01]: [Replit Agent can now buy for your business and help you reach customers](sources/rp-01.md). Replit, official, retrieved 2026-11-20.
[^bn-01]: [BNY and Microsoft Complete First Agentic Negotiation of a U.S. Treasury Trade](sources/bn-01.md). BNY, official, retrieved 2026-11-20.
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
