---
type: overview
title: Overview - the race to be agent-friendly
summary: Which financial providers let AI agents in, which keep them out, and what changed in 2026.
page_status: current
last_verified: '2026-11-13'
---

# Overview: the race to be agent-friendly

In 2026, several brokers started publishing official ways for AI agents to read accounts and place orders, mostly as MCP servers. Others are blocking outside agents. This wiki tracks both, with a source for every claim.

## Who has official agent access

All five launch brokers document an official MCP server:

- **Robinhood** opened Agentic Trading on 2026-05-27, in beta with equities only at launch.[^rh-10]
- **Coinbase** launched Coinbase for Agents on 2026-06-11.[^cb-07]
- **Webull** announced its MCP server on 2026-06-11[^wb-06] and widened its hosted Cloud MCP to trade preparation on 2026-09-29.[^wb-07]
- **Interactive Brokers** added a custom connector for any MCP client on 2026-07-17[^ib-08] and announced Autonomous Trading on 2026-10-21.[^ib-02]
- **Alpaca** documents hosted and local Trading MCP servers.[^al-03][^al-02]

Next in line for pages: **Public**, which documents a hosted MCP with a preflight before you confirm and no paper mode,[^pu-02][^pu-06] and **tastytrade**, whose MCP is self-hosted only.[^tt-03]

## Who is blocking agents

- **JPMorgan Chase:** its CEO said it will not allow outside agents into customer accounts, and a spokeswoman said the bank blocks external agents for retail customers (news report).[^bl-01]
- **Banks more broadly:** reports say JPMorgan, Morgan Stanley, Bank of America, Citi and Wells Fargo are detecting or blocking unvetted agents in customer accounts.[^bl-02][^bl-08]
- **Charles Schwab:** reported to block agents that log in on clients' behalf and any agent moving money,[^bl-04][^bl-06] while piloting its own Schwab MCP Server with Claude for select clients.[^bl-05] A third-party RIABiz article published November 13, 2026, quotes the announcement as letting thinkorswim-enabled clients "prepare, place, and manage trades, all with the client in-the-loop, through their own AI platform," and quotes sources saying the announcement "does not at all impact or target RIAs or advisors" and "doesn’t cover advisor-managed accounts." The article's Key Points box is labeled "AI generated." The headline framing that Anthropic's days are numbered is the publisher's opinion, not a fact used here.[^bl-11]

These are mostly news reports, not primary statements, which is a known gap.

## Advisor agents

The wiki also covers AI tools for financial advisors, in a new [advisor agents](advisors/README.md) section that is still thin. Current pages:

- [Claude for Financial Advisors](advisors/claude-for-financial-advisors.md), including official connector names and that Claude does not place trades or move money.[^an-01][^an-02]
- [Nitrogen](advisors/nitrogen.md), including an official MCP server and approval-required actions.[^ni-01][^ni-02]
- [Wells Fargo AI Teammate](advisors/wells-fargo-ai-teammate.md), from Wells Fargo's July 15, 2026 launch release.[^wf-01]

## How to read this wiki

- The [directory](directory.md) is the one-table view of launch brokers, with a shorter advisor-agents list below it.
- [Advisor agents](advisors/README.md) covers AI tools for financial advisors.
- [Approval models](approval-models/README.md) explain who approves an agent's order.
- [Build it](build/README.md) is for engineers and coding agents.
- [What changed](changelog/2026-11-13.md) ([2026-11-12](changelog/2026-11-12.md)) and [gaps](gaps.md) show what is new and what is still unknown.

## Sources

[^rh-10]: [Robinhood is Now Open to Agents](sources/rh-10.md). Robinhood, official, retrieved 2026-11-12.
[^cb-07]: [Coinbase for Agents: Your AI Agent Can Now Trade and Pay with Coinbase](sources/cb-07.md). Coinbase, official, retrieved 2026-11-12.
[^wb-06]: [Webull Launches Model Context Protocol, Enabling Investors to Trade Through AI in Plain Language](sources/wb-06.md). PR Newswire, official, retrieved 2026-11-12.
[^wb-07]: [Webull Expands Cloud MCP to Enable AI-Powered Trading Without Coding or Installation](sources/wb-07.md). Webull / PR Newswire, official, retrieved 2026-11-12.
[^ib-08]: [Version 1.1.5 - Custom Connector, Connect From Any MCP Client](sources/ib-08.md). IBKR Guides, official, retrieved 2026-11-12.
[^ib-02]: [Interactive Brokers Introduces Autonomous Trading](sources/ib-02.md). Interactive Brokers, official, retrieved 2026-11-12.
[^al-03]: [GitHub - alpacahq/agentic: Multi-platform plugin marketplace for Alpaca APIs · GitHub](sources/al-03.md). Alpaca (GitHub), official, retrieved 2026-11-12.
[^al-02]: [GitHub - alpacahq/alpaca-mcp-server: Alpaca’s official MCP Server lets you trade stocks, ETFs, crypto, and options, run data analysis, and build strat](sources/al-02.md). Alpaca (GitHub), official, retrieved 2026-11-12.
[^pu-02]: [Connect the Public Hosted MCP Server to Claude, ChatGPT, Codex, Muse, Perplexity, and Grok - AI Trading Setup](sources/pu-02.md). Public.com API docs, official, retrieved 2026-11-12.
[^pu-06]: [How to Trade Stocks, Options & Crypto Using Claude](sources/pu-06.md). Public.com, official, retrieved 2026-11-12.
[^tt-03]: [MCP Server · tastytrade Developer Docs](sources/tt-03.md). tastytrade Developer Docs, official, retrieved 2026-11-12.
[^bl-01]: [JPMorgan blocks outside AI agents like Muse, Instinct from account access](sources/bl-01.md). CNBC, third-party, retrieved 2026-11-12.
[^bl-02]: [Scoop: Unvetted AI agents are accessing U.S. bank accounts](sources/bl-02.md). Axios, third-party, retrieved 2026-11-12.
[^bl-08]: [Five Major Banks Are Blocking AI Agents From Logging Into Customer Accounts](sources/bl-08.md). Yahoo Finance, third-party, retrieved 2026-11-12.
[^bl-04]: [Schwab CEO says firm is blocking rogue AI agents from client accounts  - InvestmentNews](sources/bl-04.md). InvestmentNews, third-party, retrieved 2026-11-12.
[^bl-06]: [Schwab and JPMorgan are blocking AI agents from moving customer money](sources/bl-06.md). The Next Web, third-party, retrieved 2026-11-12.
[^bl-05]: [Schwab Announces Platform Enhancements Including MCP Server to Connect Clients’ AI Platforms With Their Schwab Accounts - Charles Schwab](sources/bl-05.md). Charles Schwab, official, retrieved 2026-11-12.
[^bl-11]: [Schwab surprises analysts with extra rapid launch of own MCP servers, also leaping from read-only to agentic (get stuff done) AI; it leaves RIAs out for now, and makes Anthropic's days numbered as Schwab's exclusive LLM - RIABiz](sources/bl-11.md). RIABiz, third-party, retrieved 2026-11-13.
[^an-01]: [Claude for Financial Advisors - Claude by Anthropic](sources/an-01.md). Anthropic, official, retrieved 2026-11-13.
[^an-02]: [Claude for Financial Advisors - Claude by Anthropic](sources/an-02.md). Anthropic, official, retrieved 2026-11-13.
[^ni-01]: [AI Agents Welcome - Nitrogen](sources/ni-01.md). Nitrogen, official, retrieved 2026-11-13.
[^ni-02]: [Nitrogen Brings Its AI-Powered Advisor Platform to Claude and ChatGPT, Expands Nucleus Capabilities](sources/ni-02.md). Nitrogen, official, retrieved 2026-11-13.
[^wf-01]: [Wells Fargo Newsroom - Wells Fargo introduces AI Teammate, bringing AI-powered support to the advisor experience](sources/wf-01.md). Wells Fargo, official, retrieved 2026-11-13.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20overview.md&body=Page%3A%20overview.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
