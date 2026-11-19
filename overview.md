---
type: overview
title: Overview - the race to be agent-friendly
summary: Which financial providers let AI agents read accounts, trade or pay, which keep them out, and what changed in 2026. Every fact links to its source.
page_status: current
last_verified: '2026-11-18'
---

# Overview: the race to be agent-friendly

In 2026, several brokers started publishing official ways for AI agents to read accounts and place orders, mostly as [MCP](glossary.md#mcp) servers. Others are blocking outside agents. This wiki tracks both, with a source for every claim.

## Who has official agent access

All five launch brokers document an official MCP server:

- **Robinhood** opened Agentic Trading on 2026-05-27, in beta with equities only at launch.[^rh-10]
- **Coinbase** launched Coinbase for Agents on 2026-06-11.[^cb-07] On 2026-11-11 it added Agent Controls, limits Coinbase enforces itself: a maximum trade size, a 24-hour volume limit and an auto-stop after a set percentage loss.[^cb-10]
- **Webull** announced its MCP server on 2026-06-11[^wb-06] and widened its hosted Cloud MCP to trade preparation on 2026-09-29.[^wb-07]
- **Interactive Brokers** added a custom connector for any MCP client on 2026-07-17[^ib-08] and announced Autonomous Trading on 2026-10-21.[^ib-02]
- **Alpaca** documents hosted and local Trading MCP servers.[^al-03][^al-02]

Not yet profiled here: **Public**, which documents a hosted MCP at `https://mcp.public.com/mcp` with a [preflight](glossary.md#preflight) before you confirm and no [paper mode](glossary.md#paper-trading).[^pu-02][^pu-06] Public's product page lists stocks and ETFs, options, crypto, and bonds, describes dedicated brokerage accounts for MCP connections, and documents [OAuth](glossary.md#oauth) for some clients and an [API key](glossary.md#api-key) for others.[^pu-01] An official changelog entry covers Grok MCP connector setup with OAuth.[^pu-03] Public's official GitHub repository is `publicdotcom-mcp-server`; release 0.1.0 on 2026-03-11 is described as the "initial release of the Official Public API MCP Server," and the repo documents tools including `place_order` and `preflight_order`.[^pu-08][^pu-04] Public also publishes a Claude and Claude Code connector guide and a site-wide [llms.txt](glossary.md#llmstxt) index.[^pu-09][^pu-07] Release 0.11.0 of the self-hosted server, on 2026-11-17, puts the checks in the server: optional per-order quantity and value limits, a preflight of the exact order, and user confirmation through [MCP elicitation](glossary.md#elicitation), which is on by default. Whether Public's hosted server has the same changes is unknown.[^pu-10][^pu-11]

**tastytrade** documents a self-hosted MCP only, with "no tastytrade-hosted endpoint," using an OAuth2 [refresh token](glossary.md#refresh-token) in [environment variables](glossary.md#environment-variables).[^tt-03][^tt-04] A tastytrade newsroom post describes real-time quotes, full option chains with [Greeks](glossary.md#greeks), single-leg and multi-leg order placement, and preflight cost estimates.[^tt-02]

On the watchlist, not yet a provider page: PrimeXBT announced on 2026-11-04 an MCP integration for ChatGPT and Claude that lets clients prepare market, limit, and stop orders and preview estimated prices, fees, margin requirements, leverage, and liquidation levels, with explicit trader confirmation before execution and Read-only and Read & Trade permissions.[^np-02]

## Who is blocking agents

- **JPMorgan Chase:** its CEO said it will not allow outside agents into customer accounts, and a spokeswoman said the bank blocks external agents for retail customers (news report).[^bl-01] In a later Banking Dive report, Dimon said JPMorgan is "not going to allow just any outside agent to come in inside the company because it's too risky for the clients and for JPMorgan," and warned customers about "liability transfer."[^bl-07]
- **Banks more broadly:** reports say JPMorgan, Morgan Stanley, Bank of America, Citi and Wells Fargo are detecting or blocking unvetted agents in customer accounts.[^bl-02][^bl-08]
- **Charles Schwab:** reported to block agents that log in on clients' behalf and any agent moving money,[^bl-04][^bl-06] while piloting its own Schwab MCP Server with Claude for select clients.[^bl-05] Other third-party reports likewise say Schwab is blocking outside agents that use client credentials or browser automation, will not allow agents to move money, and is steering clients toward Charley, while describing MCP access for a client's chosen model to check balances and do research with no money movement.[^bl-10] Quartz, citing The Epoch Times, also reported that Schwab planned to let third-party models connect through MCP with defined permissions, including a bar on transferring funds.[^bl-09] A third-party RIABiz article published November 13, 2026, quotes the announcement as letting thinkorswim-enabled clients "prepare, place, and manage trades, all with the client in-the-loop, through their own AI platform," and quotes sources saying the announcement "does not at all impact or target RIAs or advisors" and "doesn’t cover advisor-managed accounts." The article's Key Points box is labeled "AI generated." The headline framing that Anthropic's days are numbered is the publisher's opinion, not a fact used here.[^bl-11]

These are mostly news reports, not primary statements, which is a known gap. More detail, bank by bank: [Banks and outside agents](personal-money/banks-and-outside-agents.md).

## Payments

Card networks, payment companies and open protocols are building ways for agents to pay. Each has a page in [Payments](payments/README.md).

- **Card networks:** [Visa Intelligent Commerce](payments/visa-intelligent-commerce.md) lets approved agent builders pay with tokenized Visa credentials,[^pm-01] and [Mastercard Agent Pay](payments/mastercard-agent-pay.md) lets only registered agents pay with agentic tokens.[^pm-05] On 2026-11-17 Visa opened its [Agentic Ready](glossary.md#agentic-ready) program to merchants, payment providers and acquirers, with more than 140 participants at launch.[^pm-16] On 2026-11-12 Mastercard and partners announced a live flight purchase by an AI agent that used Agent Pay and [Verifiable Intent](glossary.md#verifiable-intent).[^pm-17]
- **Payment companies:** [Stripe](payments/stripe.md) has scoped, expiring [payment tokens](glossary.md#payment-token) for agent purchases,[^pm-08] and [PayPal](payments/paypal.md) has an MCP server for its business APIs.[^pm-10]
- **Open protocols:** [ACP](payments/agentic-commerce-protocol.md) for checkout,[^pm-07] [x402](payments/x402.md) for paying inside a web request,[^pm-15] and [AP2](payments/ap2.md) for signed proof of what the user authorized.[^pm-13]
- **An agent card:** the [Robinhood Agentic Credit Card](payments/robinhood-agentic-credit-card.md) gives your agent a virtual card, with approval for each purchase or a required monthly limit.[^rh-09]

## Personal money agents

Personal AI agents now read people's bank and card data. Banks are pushing back. See [Personal money agents](personal-money/README.md).

- [Meta Muse](personal-money/meta-muse.md) connects to bank accounts through Plaid.[^pb-01]
- [Plaid's MCP servers](personal-money/plaid.md) are developer tools, not end-user account access.[^pb-02] Plaid also launched [Agent Detection](glossary.md#agent-detection) on 2026-11-16, which lets banks see whether a session is a person or an AI agent.[^pb-06]
- [Gemini with Google Wallet](personal-money/gemini-google-wallet.md) lets US Gemini users connect Wallet, and accounts linked through Plaid, for read-only spending answers.[^gg-01]
- [Starling Assistant](personal-money/starling-assistant.md) is a UK bank's in-app agent that will set up payments from voice or text, with a tap to approve each one.[^st-01]
- [JPMorgan Smart Cash](personal-money/jpmorgan-smart-cash.md) is the bank's own pilot tool to forecast cash flow and move funds for yield (news report).[^bl-01]

## How to read this wiki

- [Trading](directory.md) is the one-table view of launch brokers. Payments and personal money each have their own section page: [payments](payments/README.md) and [personal money agents](personal-money/README.md). Short answers are in the [FAQ](faq.md).
- The [glossary](glossary.md) defines recurring terms.
- [Providers](providers/README.md) lists the brokers covered, [comparisons](comparisons/README.md) put them side by side, and [sources](sources/README.md) lists every outside page the wiki cites.
- [Approval models](approval-models/README.md) explain who approves an agent's order.
- [Build it](build/README.md) is for engineers and coding agents.
- [What changed](changelog/README.md) (latest: [2026-11-18](changelog/2026-11-18.md); earlier: [2026-11-17](changelog/2026-11-17.md), [2026-11-15](changelog/2026-11-15.md), [2026-11-14](changelog/2026-11-14.md), [2026-11-13](changelog/2026-11-13.md), [2026-11-12](changelog/2026-11-12.md)) and [gaps](gaps.md) show what is new and what is still unknown.

## Sources

[^rh-10]: [Robinhood is Now Open to Agents](sources/rh-10.md). Robinhood, official, retrieved 2026-11-12.
[^cb-07]: [Coinbase for Agents: Your AI Agent Can Now Trade and Pay with Coinbase](sources/cb-07.md). Coinbase, official, retrieved 2026-11-12.
[^cb-10]: [Coinbase for Agents introduces new Agent Controls](sources/cb-10.md). Coinbase, official, retrieved 2026-11-18.
[^wb-06]: [Webull Launches Model Context Protocol, Enabling Investors to Trade Through AI in Plain Language](sources/wb-06.md). PR Newswire, official, retrieved 2026-11-12.
[^wb-07]: [Webull Expands Cloud MCP to Enable AI-Powered Trading Without Coding or Installation](sources/wb-07.md). Webull / PR Newswire, official, retrieved 2026-11-12.
[^ib-08]: [Version 1.1.5 - Custom Connector, Connect From Any MCP Client](sources/ib-08.md). IBKR Guides, official, retrieved 2026-11-12.
[^ib-02]: [Interactive Brokers Introduces Autonomous Trading](sources/ib-02.md). Interactive Brokers, official, retrieved 2026-11-12.
[^al-03]: [GitHub - alpacahq/agentic: Multi-platform plugin marketplace for Alpaca APIs · GitHub](sources/al-03.md). Alpaca (GitHub), official, retrieved 2026-11-12.
[^al-02]: [GitHub - alpacahq/alpaca-mcp-server: Alpaca’s official MCP Server lets you trade stocks, ETFs, crypto, and options, run data analysis, and build strat](sources/al-02.md). Alpaca (GitHub), official, retrieved 2026-11-12.
[^pu-02]: [Connect the Public Hosted MCP Server to Claude, ChatGPT, Codex, Muse, Perplexity, and Grok - AI Trading Setup](sources/pu-02.md). Public.com API docs, official, retrieved 2026-11-12.
[^pu-06]: [How to Trade Stocks, Options & Crypto Using Claude](sources/pu-06.md). Public.com, official, retrieved 2026-11-12.
[^pu-01]: [Public MCP Server for trading on AI platforms](sources/pu-01.md). Public.com, official, retrieved 2026-11-12.
[^pu-03]: [Public Trading API Changelog - Latest Updates & Release Notes](sources/pu-03.md). Public.com API docs, official, retrieved 2026-11-12.
[^pu-08]: [Release 0.1.0 · PublicDotCom/publicdotcom-mcp-server · GitHub](sources/pu-08.md). Public.com (GitHub), official, retrieved 2026-11-12.
[^pu-04]: [GitHub - PublicDotCom/publicdotcom-mcp-server · GitHub](sources/pu-04.md). Public.com (GitHub), official, retrieved 2026-11-12.
[^pu-09]: [Claude & Claude Code Connector for Stock & Options Trading on Public MCP](sources/pu-09.md). Public.com API docs, official, retrieved 2026-11-12.
[^pu-07]: [public.com llms.txt](sources/pu-07.md). Public.com, official, retrieved 2026-11-12.
[^pu-10]: [Release v0.11.0 · PublicDotCom/publicdotcom-mcp-server](sources/pu-10.md). Public.com (GitHub), official, retrieved 2026-11-18.
[^pu-11]: [Enforce preflight and user confirmation on every order — 0.11.0 (pull request 19)](sources/pu-11.md). Public.com (GitHub), official, retrieved 2026-11-18.
[^tt-03]: [MCP Server · tastytrade Developer Docs](sources/tt-03.md). tastytrade Developer Docs, official, retrieved 2026-11-12.
[^tt-04]: [OAuth2 authentication · tastytrade Developer Docs](sources/tt-04.md). tastytrade Developer Docs, official, retrieved 2026-11-12.
[^tt-02]: [Open API MCP Brings AI to Your tastytrade Account](sources/tt-02.md). tastytrade, official, retrieved 2026-11-12.
[^np-02]: [PrimeXBT Launches AI-Assisted Trading with MCP Integration, Connecting ChatGPT and Claude to Trading Accounts](sources/np-02.md). GlobeNewswire, official, retrieved 2026-11-12.
[^bl-01]: [JPMorgan blocks outside AI agents like Muse, Instinct from account access](sources/bl-01.md). CNBC, third-party, retrieved 2026-11-12.
[^bl-07]: [JPMorgan CEO Dimon warns customers of 'liability transfer' with AI](sources/bl-07.md). Banking Dive, third-party, retrieved 2026-11-12.
[^bl-02]: [Scoop: Unvetted AI agents are accessing U.S. bank accounts](sources/bl-02.md). Axios, third-party, retrieved 2026-11-12.
[^bl-08]: [Five Major Banks Are Blocking AI Agents From Logging Into Customer Accounts](sources/bl-08.md). Yahoo Finance, third-party, retrieved 2026-11-12.
[^bl-04]: [Schwab CEO says firm is blocking rogue AI agents from client accounts  - InvestmentNews](sources/bl-04.md). InvestmentNews, third-party, retrieved 2026-11-12.
[^bl-06]: [Schwab and JPMorgan are blocking AI agents from moving customer money](sources/bl-06.md). The Next Web, third-party, retrieved 2026-11-12.
[^bl-05]: [Schwab Announces Platform Enhancements Including MCP Server to Connect Clients’ AI Platforms With Their Schwab Accounts - Charles Schwab](sources/bl-05.md). Charles Schwab, official, retrieved 2026-11-12.
[^bl-10]: [Schwab blocks outside AI agents and steers clients to Charley: the cash-sweep stakes for client-side agents](sources/bl-10.md). The Exchange (theexchange.tech), third-party, retrieved 2026-11-12.
[^bl-09]: [Schwab and JPMorgan are blocking outside AI agents from accounts](sources/bl-09.md). Quartz, third-party, retrieved 2026-11-12.
[^bl-11]: [Schwab surprises analysts with extra rapid launch of own MCP servers, also leaping from read-only to agentic (get stuff done) AI; it leaves RIAs out for now, and makes Anthropic's days numbered as Schwab's exclusive LLM - RIABiz](sources/bl-11.md). RIABiz, third-party, retrieved 2026-11-13.
[^pm-01]: [Visa Developer Center](sources/pm-01.md). Visa Developer, official, retrieved 2026-11-12.
[^pm-05]: [Mastercard Agent Pay: secure, scalable and trusted agentic AI](sources/pm-05.md). Mastercard, official, retrieved 2026-11-12.
[^pm-16]: [Visa Expands Agentic Ready to Help Scale Trusted AI Commerce Globally](sources/pm-16.md). Visa, official, retrieved 2026-11-18.
[^pm-17]: [Travelport, Booked AI, Basis Theory, and Mastercard complete live end-to-end agentic flight purchase](sources/pm-17.md). Mastercard, official, retrieved 2026-11-18.
[^pm-08]: [Shared payment tokens - Stripe Documentation](sources/pm-08.md). Stripe Docs, official, retrieved 2026-11-12.
[^pm-10]: [MCP server quickstart guide - PayPal Developer](sources/pm-10.md). PayPal Developer, official, retrieved 2026-11-12.
[^pm-07]: [GitHub - agentic-commerce-protocol/agentic-commerce-protocol: The Agentic Commerce Protocol (ACP) is an interaction model and open standard for connec](sources/pm-07.md). ACP (GitHub), official, retrieved 2026-11-12.
[^pm-15]: [x402 specification v2](sources/pm-15.md). x402 Foundation (GitHub), official, retrieved 2026-11-12.
[^pm-13]: [AP2 - Agent Payments Protocol Documentation](sources/pm-13.md). AP2 Protocol, official, retrieved 2026-11-12.
[^rh-09]: [Agentic Credit Card - Robinhood](sources/rh-09.md). Robinhood, official, retrieved 2026-11-12.
[^pb-01]: [Plaid powers Meta's new AI agent, Muse - Plaid](sources/pb-01.md). Plaid, official, retrieved 2026-11-12.
[^pb-02]: [Resources - MCP Server - Plaid Docs](sources/pb-02.md). Plaid Docs, official, retrieved 2026-11-12.
[^pb-06]: [Introducing Agent Detection: building trust in the age of agentic finance](sources/pb-06.md). Plaid, official, retrieved 2026-11-18.
[^gg-01]: [Connect Google Wallet to Gemini for personal finance insights](sources/gg-01.md). Google, official, retrieved 2026-11-18.
[^st-01]: ['Talk to transact': Starling customers can use their voice to send money](sources/st-01.md). Starling Bank, official, retrieved 2026-11-18.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20overview.md&body=Page%3A%20overview.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
