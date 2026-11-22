---
type: guide
title: "FAQ: AI agents and money"
summary: Short, cited answers to common questions about AI agents that trade, pay and use bank data, and who approves what. Each links to the page with the details.
page_status: current
last_verified: '2026-11-12'
---

# FAQ: AI agents and money

AI agents can already trade at five launch brokers and pay through card-network programs, payment tokens and wallets, but each sets its own approval rules. Every answer below is short, cited and links to the page with the details; anything the sources do not confirm stays "unknown". Not investment advice.

## Which brokers let AI agents trade?

All five launch brokers publish an official [MCP](glossary.md#mcp) server for AI agents: Alpaca, Coinbase, Interactive Brokers, Robinhood and Webull.[^al-02][^cb-01][^ib-01][^rh-01][^wb-02] They differ on who approves each order. Details: [Trading](trading.md).

## Who approves an AI agent's trades?

It depends on the broker. Robinhood limits the agent to a separate account you fund, and per-order approval is an optional toggle.[^rh-01][^rh-04] With Webull's hosted Cloud MCP, you confirm each trade in the Webull app.[^wb-07] At Interactive Brokers, by default the AI drafts instructions you review and submit.[^ib-01][^ib-07] Alpaca documents no broker-side approval, so approval has to live in your agent or client.[^al-05][^al-03] See [approval models](approval-models/README.md).

## Can I test a trading agent without real money?

Sometimes. Alpaca has a separate [paper trading](glossary.md#paper-trading) endpoint with a $100K simulated balance.[^al-01][^al-03] Webull's local OpenAPI MCP defaults to the UAT [sandbox](glossary.md#sandbox); a sandbox for its Cloud MCP is unknown.[^wb-03] For Robinhood, Coinbase and Interactive Brokers, a paper option for agents is unknown. See the [launch-broker comparison](comparisons/launch-brokers.md).

## Can an AI agent pay for things for me?

Yes, through several programs, each with limits. Visa lets approved agent builders pay with tokenized Visa credentials, under purchase instructions the consumer approved.[^pm-01] Mastercard lets only registered agents pay, using agentic tokens.[^pm-05][^pm-06] Stripe's shared [payment tokens](glossary.md#payment-token) carry usage and expiry limits.[^pm-08] Robinhood's Agentic Credit Card asks you to approve each purchase or set a monthly limit.[^rh-09] OpenAI's ChatGPT Wallet asks for a biometric check before each purchase, for ChatGPT Pro users in the US.[^oa-01] See [Payments](payments/README.md).

## Can my AI agent buy from any website?

No. Some merchants forbid agents in their terms. eBay bans buy-for-me agents without its prior express permission.[^eb-01] United bans the use of AI agents to make, change or service a ticket or to buy any product.[^ua-01] See [Merchants and outside agents](payments/merchants-and-outside-agents.md).

## Do banks let outside AI agents into my account?

Often not fully, according to news reports. They say several big US banks block outside agents that log in with a customer's password,[^bl-02][^bl-08] and that most allow read-only access at best, while some build their own AI tools.[^bl-01][^bl-02] See [Banks and outside agents](personal-money/banks-and-outside-agents.md).

## Sources

[^al-02]: [GitHub - alpacahq/alpaca-mcp-server: Alpaca’s official MCP Server lets you trade stocks, ETFs, crypto, and options, run data analysis, and build strat](sources/al-02.md). Alpaca (GitHub), official, retrieved 2026-11-19.
[^cb-01]: [Coinbase MCP - Coinbase Developer Documentation](sources/cb-01.md). Coinbase Developer Platform, official, retrieved 2026-11-12.
[^ib-01]: [Interactive Brokers AI Hub](sources/ib-01.md). Interactive Brokers, official, retrieved 2026-11-12.
[^rh-01]: [Onboarding an external agent - Robinhood](sources/rh-01.md). Robinhood, official, retrieved 2026-11-19.
[^wb-02]: [Webull Cloud MCP Server - Webull API](sources/wb-02.md). Webull Developer, official, retrieved 2026-11-19.
[^rh-04]: [Trading with your agent - Robinhood](sources/rh-04.md). Robinhood, official, retrieved 2026-11-19.
[^wb-07]: [Webull Expands Cloud MCP to Enable AI-Powered Trading Without Coding or Installation](sources/wb-07.md). Webull / PR Newswire, official, retrieved 2026-11-12.
[^ib-07]: [AI Instructions](sources/ib-07.md). IBKR Guides, official, retrieved 2026-11-12.
[^al-05]: [GitHub - alpacahq/cli: CLI for Trading API · GitHub](sources/al-05.md). Alpaca (GitHub), official, retrieved 2026-11-12.
[^al-03]: [GitHub - alpacahq/agentic: Multi-platform plugin marketplace for Alpaca APIs · GitHub](sources/al-03.md). Alpaca (GitHub), official, retrieved 2026-11-19.
[^al-01]: [Alpaca - Trade with AI Using Alpaca's MCP Server](sources/al-01.md). Alpaca, official, retrieved 2026-11-19.
[^wb-03]: [GitHub - webull-inc/webull-openapi-mcp: Webull OpenAPI MCP · GitHub](sources/wb-03.md). Webull (GitHub), official, retrieved 2026-11-19.
[^pm-01]: [Visa Developer Center](sources/pm-01.md). Visa Developer, official, retrieved 2026-11-12.
[^pm-05]: [Mastercard Agent Pay: secure, scalable and trusted agentic AI](sources/pm-05.md). Mastercard, official, retrieved 2026-11-12.
[^pm-06]: [Agentic token framework: Driving trusted AI transactions](sources/pm-06.md). Mastercard, official, retrieved 2026-11-12.
[^pm-08]: [Shared payment tokens - Stripe Documentation](sources/pm-08.md). Stripe Docs, official, retrieved 2026-11-12.
[^rh-09]: [Agentic Credit Card - Robinhood](sources/rh-09.md). Robinhood, official, retrieved 2026-11-19.
[^oa-01]: [Introducing ChatGPT Wallet](sources/oa-01.md). OpenAI, official, retrieved 2026-11-15.
[^eb-01]: [User Agreement - eBay](sources/eb-01.md). eBay, official, retrieved 2026-11-15.
[^ua-01]: [Contract of Carriage Document - United Airlines](sources/ua-01.md). United Airlines, official, retrieved 2026-11-15.
[^bl-02]: [Scoop: Unvetted AI agents are accessing U.S. bank accounts](sources/bl-02.md). Axios, third-party, retrieved 2026-11-12.
[^bl-08]: [Five Major Banks Are Blocking AI Agents From Logging Into Customer Accounts](sources/bl-08.md). Yahoo Finance, third-party, retrieved 2026-11-12.
[^bl-01]: [JPMorgan blocks outside AI agents like Muse, Instinct from account access](sources/bl-01.md). CNBC, third-party, retrieved 2026-11-12.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20faq.md&body=Page%3A%20faq.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
