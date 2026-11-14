---
title: Index
summary: Every page in the wiki, generated from page headers.
page_status: current
---

# Index

**Connect AI agents to money, safely**

How brokers, banks and payment networks let AI agents trade, pay and manage money, and who approves what. Starting with five brokers.

Every page in the wiki. Generated from page headers by the publisher; do not edit by hand.

## For agents

- Agents: GET `/feedback` first for the current schema and an example, then POST JSON to the same URL. `note` is required. Optional fields: `task`, `found`, `pages`, `missing`, `wanted`, `corrections`, `agent`. The body may be at most 4 KB. Limit is 10 submissions per rolling 24 hours per client. Do not include personal data, account numbers, credentials, or anything private about your user. A person reviews every note; nothing is published automatically.
- `/feedback`: agents can POST a short JSON note about what was missing or wrong (send GET for instructions).
- Full rules: [AGENTS.md](AGENTS.md). Entry point: [llms.txt](llms.txt).

## Start here

- [README.md](README.md): What this wiki is and how to use it
- [AGENTS.md](AGENTS.md): Rules for agents: ingest, query, lint, citations, page life cycle
- [Overview - the race to be agent-friendly](overview.md): Which financial providers let AI agents in, which keep them out, and what changed in 2026.
- [directory.md](directory.md): Every provider's key fields in one table (generated)
- [Advisor agents](advisors/README.md): AI tools for financial advisors (new, still thin)
- [Gaps - what we do not know yet](gaps.md): Open questions and missing sources, ranked.
- [log.md](log.md): Append-only history of ingests, reviews and lint passes

## Providers

- [Alpaca](providers/alpaca.md) (current): Developer-first. Hosted Trading MCP with OAuth (live and paper) plus a local open-source MCP and a CLI using API keys. No broker-side per-order approval is documented; paper trading is built in.
- [Coinbase](providers/coinbase.md) (current): Coinbase for Agents. Remote MCP with OAuth (allowlisted clients) or a local CLI with an API key. Agents can be limited to a dedicated portfolio chosen on the approval screen.
- [Interactive Brokers](providers/interactive-brokers.md) (current): Remote MCP connector. By default the AI drafts trade instructions you review and submit; eligible accounts can enable Autonomous Trading inside a separately funded AI Partition.
- [Robinhood](providers/robinhood.md) (current): Remote Trading MCP with OAuth. Agents read all Robinhood accounts but trade only in a dedicated agentic (MCP) account; per-order approval is an optional toggle.
- [Webull](providers/webull.md) (current): Two official paths. The hosted Cloud MCP prepares trade instructions that you confirm in the Webull app; the local OpenAPI MCP places orders directly, with configurable risk limits and a sandbox default.

## Advisor agents

- [Advisor agents](advisors/README.md) (current): AI tools that help financial advisors work with client data and firm systems. This section is new and still thin. It currently covers Claude for Financial Advisors, Nitrogen, and Wells Fargo AI Teammate.
- [Claude for Financial Advisors](advisors/claude-for-financial-advisors.md) (current): Anthropic's advisor product, with official connectors into firm systems. Official pages say Claude does not place trades or move money, and they recommend Enterprise for RIAs.
- [Nitrogen](advisors/nitrogen.md) (current): Official Nitrogen agents page documents an MCP server and approval-required actions. A Fall 2026 announcement said the suite was brought into Claude and ChatGPT and Nucleus was expanded.
- [Wells Fargo AI Teammate](advisors/wells-fargo-ai-teammate.md) (current): Official July 15, 2026 launch of a chat-based AI capability embedded in Advisor Gateway for WIM advisors, including FiNet. Later interview figures are company-reported and are labeled as such.

## Approval models

- [Approval models](approval-models/README.md) (current): The five ways brokers decide who approves an agent's order, from a walled-off account to no broker-side approval at all.
- [Approval model: AI Partition](approval-models/ai-partition.md) (current): An eligible client funds a partition inside their account where a connected AI may submit supported orders without approving each one.
- [Approval model: draft, then you submit](approval-models/draft-then-submit.md) (current): The agent writes a non-binding trade instruction; nothing happens until you review and submit it yourself in the broker's app.
- [Approval model: none at the broker](approval-models/none.md) (current): The broker executes what the agent sends. Any approval step has to live in your agent, MCP client or local server.
- [Approval model: per-order confirm](approval-models/per-order-confirm.md) (current): The agent prepares each order, and a person confirms it in the broker's own app before it reaches the market.
- [Approval model: separate account](approval-models/separate-account.md) (current): The agent can only trade in an account or portfolio you create and fund for it, so its reach is capped by what you deposit.

## Rails

- [Rails](rails/README.md) (current): The building blocks under agent access to money - how agents connect, authenticate, pay, prove who they are, and carry a user's mandate.
- [Agent identity](rails/agent-identity.md) (current): How agents can prove who they are to websites and merchants - signed HTTP requests, network-run trust protocols and proof-of-human delegation.
- [Agent payments](rails/agent-payments.md) (current): Starter overview of how agents pay - card-network agent programs, scoped payment tokens, open commerce protocols and HTTP 402 payments.
- [Local MCP servers and CLIs](rails/local-mcp-and-cli.md) (current): Self-run MCP servers and CLIs authenticate with API keys you hold, so their guardrails are only as strong as your local setup.
- [Mandates and data access](rails/mandates-and-data-access.md) (current): Protocols that record what a user authorized an agent to do, and the US data-rights rule that may shape agent access to bank data.
- [Remote MCP with OAuth](rails/remote-mcp-oauth.md) (current): How hosted broker MCP servers advertise their OAuth setup, how clients register, and why allowlisting still matters.

## Build it

- [Build it](build/README.md) (current): Practical notes for engineers and coding agents connecting to broker MCP servers safely.
- [Connect an MCP client](build/connect-an-mcp-client.md) (current): Documented connection commands and URLs for each launch broker, taken from the providers' own setup pages.
- [Human-in-the-loop patterns](build/human-in-the-loop.md) (current): Where to put human approval in an agent trading flow, and why broker-side approval beats client-side approval.
- [Starter prompts for coding agents](build/starter-prompts.md) (current): Copy-paste prompts that make a coding agent use this wiki, cite pages and say "unknown" instead of guessing.

## Comparisons

- [Launch brokers compared: approval and safety posture](comparisons/launch-brokers.md) (current): Side-by-side view of how the five launch brokers let agents trade, who approves orders, and where the guardrails are enforced.

## Analyses

- [Analyses](analyses/README.md) (current): Saved answers to good questions, filed back into the wiki. Empty at launch.

## What changed

- [What changed: 2026-11-14](changelog/2026-11-14.md) (current): Added official ERC-8004, cited remaining source cards, and refreshed the front page for search and plain-English answers.
- [What changed: 2026-11-13](changelog/2026-11-13.md) (current): Added a thin advisor-agents section, a third-party Schwab RIABiz source, official Coinbase agent-feedback docs, and related official and third-party source cards.
- [What changed: 2026-11-12](changelog/2026-11-12.md) (current): First draft of the wiki - five launch broker pages, 103 source cards, approval-model taxonomy and agent packaging.

## Schema

- [schema/provider.schema.json](schema/provider.schema.json): provider page headers
- [schema/source.schema.json](schema/source.schema.json): source card headers
- [schema/page.schema.json](schema/page.schema.json): all other page headers

## Sources (114)

| Card | Subject | Publisher | Authority | Retrieved |
|---|---|---|---|---|
| [al-01](sources/al-01.md): Alpaca - Trade with AI Using Alpaca's MCP Server | Alpaca | Alpaca | official | 2026-11-12 |
| [al-02](sources/al-02.md): GitHub - alpacahq/alpaca-mcp-server: Alpaca’s official MCP Server lets you trade stocks, ETFs, crypto, and options, run data analysis, and build strat | Alpaca | Alpaca (GitHub) | official | 2026-11-12 |
| [al-03](sources/al-03.md): GitHub - alpacahq/agentic: Multi-platform plugin marketplace for Alpaca APIs · GitHub | Alpaca | Alpaca (GitHub) | official | 2026-11-12 |
| [al-04](sources/al-04.md): GitHub - alpacahq/alpaca-skills: Agent skills for Alpaca's Trading API and Broker API: drop-in SKILL.md files for AI coding assistants · GitHub | Alpaca | Alpaca (GitHub) | official | 2026-11-12 |
| [al-05](sources/al-05.md): GitHub - alpacahq/cli: CLI for Trading API · GitHub | Alpaca | Alpaca (GitHub) | official | 2026-11-12 |
| [al-07](sources/al-07.md): Alpaca Launches MCP Servers in Public Beta for Broker Partners. | Alpaca | Alpaca | official | 2026-11-12 |
| [al-08](sources/al-08.md): Broker API MCP (Alpaca Docs) | Alpaca | Alpaca Docs | official | 2026-11-12 |
| [al-09](sources/al-09.md): Trading API MCP | Alpaca | Alpaca Docs | official | 2026-11-12 |
| [an-01](sources/an-01.md): Claude for Financial Advisors \| Claude by Anthropic | Anthropic | Anthropic | official | 2026-11-13 |
| [an-02](sources/an-02.md): Claude for Financial Advisors \| Claude by Anthropic | Anthropic | Anthropic | official | 2026-11-13 |
| [bd-01](sources/bd-01.md): 8 questions for the Wells Fargo wealth unit’s AI chief \| Banking Dive | Wells Fargo | Banking Dive | third-party | 2026-11-13 |
| [bl-01](sources/bl-01.md): JPMorgan blocks outside AI agents like Muse, Instinct from account access | JPMorgan Chase | CNBC | third-party | 2026-11-12 |
| [bl-02](sources/bl-02.md): Scoop: Unvetted AI agents are accessing U.S. bank accounts | Banks (JPM, MS, BofA, Citi, Wells) | Axios | third-party | 2026-11-12 |
| [bl-04](sources/bl-04.md): Schwab CEO says firm is blocking rogue AI agents from client accounts  - InvestmentNews | Charles Schwab | InvestmentNews | third-party | 2026-11-12 |
| [bl-05](sources/bl-05.md): Schwab Announces Platform Enhancements Including MCP Server to Connect Clients’ AI Platforms With Their Schwab Accounts \| Charles Schwab | Charles Schwab | Charles Schwab | official | 2026-11-12 |
| [bl-06](sources/bl-06.md): Schwab and JPMorgan are blocking AI agents from moving customer money | Charles Schwab | The Next Web | third-party | 2026-11-12 |
| [bl-07](sources/bl-07.md): JPMorgan CEO Dimon warns customers of 'liability transfer' with AI | JPMorgan Chase | Banking Dive | third-party | 2026-11-12 |
| [bl-08](sources/bl-08.md): Five Major Banks Are Blocking AI Agents From Logging Into Customer Accounts | Banks (JPM, MS, BofA, Citi, Wells) | Yahoo Finance | third-party | 2026-11-12 |
| [bl-09](sources/bl-09.md): Schwab and JPMorgan are blocking outside AI agents from accounts | Charles Schwab / JPMorgan | Quartz | third-party | 2026-11-12 |
| [bl-10](sources/bl-10.md): Schwab blocks outside AI agents and steers clients to Charley: the cash-sweep stakes for client-side agents | Charles Schwab | The Exchange (theexchange.tech) | third-party | 2026-11-12 |
| [bl-11](sources/bl-11.md): Schwab surprises analysts with extra rapid launch of own MCP servers, also leaping from read-only to agentic (get stuff done) AI; it leaves RIAs out for now, and makes Anthropic's days numbered as Schwab's exclusive LLM \| RIABiz | Charles Schwab | RIABiz | third-party | 2026-11-13 |
| [cb-01](sources/cb-01.md): Coinbase MCP - Coinbase Developer Documentation | Coinbase | Coinbase Developer Platform | official | 2026-11-12 |
| [cb-03](sources/cb-03.md): Coinbase for Agents setup skill (skill.md) | Coinbase | Coinbase Developer Platform | official | 2026-11-12 |
| [cb-04](sources/cb-04.md): Coinbase for Agents MCP: OAuth protected-resource metadata | Coinbase | Coinbase (endpoint metadata) | official | 2026-11-12 |
| [cb-05](sources/cb-05.md): CDP MCP - Coinbase Developer Documentation | Coinbase | Coinbase Developer Platform | official | 2026-11-12 |
| [cb-06](sources/cb-06.md): Coinbase Developer Platform docs llms.txt | Coinbase | Coinbase Developer Platform | official | 2026-11-12 |
| [cb-07](sources/cb-07.md): Coinbase for Agents: Your AI Agent Can Now Trade and Pay with Coinbase | Coinbase | Coinbase | official | 2026-11-12 |
| [cb-08](sources/cb-08.md): Coinbase’s new tool can help agents trade and pay for premium research \| TechCrunch | Coinbase | TechCrunch | third-party | 2026-11-12 |
| [cb-09](sources/cb-09.md): Coinbase MCP - Coinbase Developer Documentation | Coinbase | Coinbase Developer Platform | official | 2026-11-13 |
| [ib-01](sources/ib-01.md): Interactive Brokers AI Hub | Interactive Brokers | Interactive Brokers | official | 2026-11-12 |
| [ib-02](sources/ib-02.md): Interactive Brokers Introduces Autonomous Trading | Interactive Brokers | Interactive Brokers | official | 2026-11-12 |
| [ib-03](sources/ib-03.md): IBKR Autonomous Trading: What the AI Partition Lets an AI Trade Without Asking, Read Off IBKR's Pages — DeskTested | Interactive Brokers | DeskTested | third-party | 2026-11-12 |
| [ib-04](sources/ib-04.md): Interactive Brokers (IBKR) connector \| Claude by Anthropic | Interactive Brokers | Anthropic (Claude connector directory) | third-party | 2026-11-12 |
| [ib-06](sources/ib-06.md): AI-Powered Portfolio Analysis & Trading Tools (IBKR AI Integrations) | Interactive Brokers | Interactive Brokers | official | 2026-11-12 |
| [ib-07](sources/ib-07.md): AI Instructions | Interactive Brokers | IBKR Guides | official | 2026-11-12 |
| [ib-08](sources/ib-08.md): Version 1.1.5 - Custom Connector, Connect From Any MCP Client | Interactive Brokers | IBKR Guides | official | 2026-11-12 |
| [id-01](sources/id-01.md): draft-ietf-webbotauth-httpsig-protocol-01 - HTTP Message Signatures for automated traffic | Web Bot Auth | IETF | official | 2026-11-12 |
| [id-02](sources/id-02.md): Web Bot Auth · Cloudflare bot solutions docs | Web Bot Auth | Cloudflare Docs | official | 2026-11-12 |
| [id-03](sources/id-03.md): The age of agents: cryptographically recognizing agent traffic \| Cloudflare Blog | Web Bot Auth | Cloudflare Blog | official | 2026-11-12 |
| [id-04](sources/id-04.md): Now available: AgentKit, Proof of Human for the agentic web | World AgentKit | World | official | 2026-11-12 |
| [id-05](sources/id-05.md): Emerging Trend in GenAI: Observations on AI Agents | FINRA | FINRA | official | 2026-11-12 |
| [id-06](sources/id-06.md): GenAI: Continuing and Emerging Trends (FINRA 2026 oversight report) | FINRA | FINRA | official | 2026-11-12 |
| [id-07](sources/id-07.md): ERC-8004: Trustless Agents | ERC-8004 | Ethereum Improvement Proposals | official | 2026-11-14 |
| [ni-01](sources/ni-01.md): AI Agents Welcome \| Nitrogen | Nitrogen | Nitrogen | official | 2026-11-13 |
| [ni-02](sources/ni-02.md): Nitrogen Brings Its AI-Powered Advisor Platform to Claude and ChatGPT, Expands Nucleus Capabilities | Nitrogen | Nitrogen | official | 2026-11-13 |
| [np-02](sources/np-02.md): PrimeXBT Launches AI-Assisted Trading with MCP Integration, Connecting ChatGPT and Claude to Trading Accounts | PrimeXBT | GlobeNewswire | official | 2026-11-12 |
| [nv-01](sources/nv-01.md): Nevis Raises $70M Series B Led by EQT Ventures – Nevis | Nevis | Nevis | official | 2026-11-13 |
| [pa-01](sources/pa-01.md): GitHub - mphinance/awesome-broker-mcp: Which brokers can an AI actually trade through? A verified directory of broker MCP servers — official vs commun | awesome-broker-mcp | mphinance (GitHub) | third-party | 2026-11-12 |
| [pa-02](sources/pa-02.md): GitHub - BlockRunAI/awesome-finance-mcp: A curated list of MCP servers for AI finance agents · GitHub | awesome-finance-mcp | BlockRunAI (GitHub) | third-party | 2026-11-12 |
| [pa-03](sources/pa-03.md): GitHub - frankxai/awesome-payment-agent-skills: Web-first payment-agent skills: mandates, auth, settlement. Human spend cap required. · GitHub | awesome-payment-agent-skills | frankxai (GitHub) | third-party | 2026-11-12 |
| [pa-04](sources/pa-04.md): GitHub - mpp-best/awesome_mpp: A curated list of open-source AI agent payment & x402 projects, SDKs and tools. Full directory at mpp.best · GitHub | awesome_mpp | mpp-best (GitHub) | third-party | 2026-11-12 |
| [pa-05](sources/pa-05.md): GitHub - macoloye/awesome-finance-agent: A curated list of finance agent SDKs, MCP tools, wallet infrastructure, safeguards, simulation systems, and s | awesome-finance-agent | macoloye (GitHub) | third-party | 2026-11-12 |
| [pa-06](sources/pa-06.md): awesome-mcp-servers: Finance & Fintech section | awesome-mcp-servers (Finance & Fintech) | punkpeye (GitHub) | third-party | 2026-11-12 |
| [pa-07](sources/pa-07.md): FintechAI Directory — AI Tools for Finance, Curated by Finance Professionals | fintechai.directory | FintechAI Directory | third-party | 2026-11-12 |
| [pa-08](sources/pa-08.md): Mastercard Agent Pay explained: agentic tokens, Verifiable Intent and Know Your Agent \| Agentic Rails Atlas | Agentic Rails Atlas | atlas.merces.ai | third-party | 2026-11-12 |
| [pa-09](sources/pa-09.md): Fidelity Investments MCP: AI agent access (ChatGPT, Claude) | AgentBroker Index | agentbrokerindex.com | third-party | 2026-11-12 |
| [pa-10](sources/pa-10.md): How do I connect an AI agent to Interactive Brokers? | The Agentic Trader | theagentictrader.com | third-party | 2026-11-12 |
| [pb-01](sources/pb-01.md): Plaid powers Meta's new AI agent, Muse \| Plaid | Meta Muse / Plaid | Plaid | official | 2026-11-12 |
| [pb-02](sources/pb-02.md): Resources - MCP Server \| Plaid Docs | Plaid | Plaid Docs | official | 2026-11-12 |
| [pb-03](sources/pb-03.md): Meta's Muse is attacking one of economy's most profitable weak spots | Meta Muse | CNBC | third-party | 2026-11-12 |
| [pb-04](sources/pb-04.md): AI agents scramble banks' fight with fintechs | Regulation (CFPB 1033) | POLITICO | third-party | 2026-11-12 |
| [pb-05](sources/pb-05.md): Federal Register | CFPB 1033 | Federal Register | official | 2026-11-12 |
| [pm-01](sources/pm-01.md): Visa Developer Center | Visa Intelligent Commerce | Visa Developer | official | 2026-11-12 |
| [pm-02](sources/pm-02.md): MCP docs \| Visa Developer | Visa Intelligent Commerce | Visa Developer | official | 2026-11-12 |
| [pm-03](sources/pm-03.md): GitHub - visa/trusted-agent-protocol: Establishing a universal standard of trust between AI agents and merchants for the next phase of agentic commerc | Visa Trusted Agent Protocol | Visa (GitHub) | official | 2026-11-12 |
| [pm-04](sources/pm-04.md): Visa Opens the Door to AI-Driven Shopping for Businesses Worldwide \| Visa | Visa Intelligent Commerce | Visa | official | 2026-11-12 |
| [pm-05](sources/pm-05.md): Mastercard Agent Pay: secure, scalable and trusted agentic AI | Mastercard Agent Pay | Mastercard | official | 2026-11-12 |
| [pm-06](sources/pm-06.md): Agentic token framework: Driving trusted AI transactions | Mastercard Agent Pay | Mastercard | official | 2026-11-12 |
| [pm-07](sources/pm-07.md): GitHub - agentic-commerce-protocol/agentic-commerce-protocol: The Agentic Commerce Protocol (ACP) is an interaction model and open standard for connec | Agentic Commerce Protocol (OpenAI/Stripe) | ACP (GitHub) | official | 2026-11-12 |
| [pm-08](sources/pm-08.md): Shared payment tokens \| Stripe Documentation | Stripe | Stripe Docs | official | 2026-11-12 |
| [pm-09](sources/pm-09.md): Model Context Protocol (MCP) \| Stripe Documentation | Stripe | Stripe Docs | official | 2026-11-12 |
| [pm-10](sources/pm-10.md): MCP server quickstart guide \| PayPal Developer | PayPal | PayPal Developer | official | 2026-11-12 |
| [pm-11](sources/pm-11.md): Agent toolkit quickstart guide \| PayPal Developer | PayPal | PayPal Developer | official | 2026-11-12 |
| [pm-12](sources/pm-12.md): GitHub - google-agentic-commerce/AP2: Building a Secure and Interoperable Future for AI-Driven Payments. · GitHub | Google AP2 | Google (GitHub) | official | 2026-11-12 |
| [pm-13](sources/pm-13.md): AP2 - Agent Payments Protocol Documentation | Google AP2 | AP2 Protocol | official | 2026-11-12 |
| [pm-14](sources/pm-14.md): GitHub - x402-foundation/x402: A payments protocol for the internet. Built on HTTP. · GitHub | x402 | x402 Foundation (GitHub) | official | 2026-11-12 |
| [pm-15](sources/pm-15.md): x402 specification v2 | x402 | x402 Foundation (GitHub) | official | 2026-11-12 |
| [pu-01](sources/pu-01.md): Public MCP Server for trading on AI platforms | Public | Public.com | official | 2026-11-12 |
| [pu-02](sources/pu-02.md): Connect the Public Hosted MCP Server to Claude, ChatGPT, Codex, Muse, Perplexity, and Grok \| AI Trading Setup | Public | Public.com API docs | official | 2026-11-12 |
| [pu-03](sources/pu-03.md): Public Trading API Changelog \| Latest Updates & Release Notes | Public | Public.com API docs | official | 2026-11-12 |
| [pu-04](sources/pu-04.md): GitHub - PublicDotCom/publicdotcom-mcp-server · GitHub | Public | Public.com (GitHub) | official | 2026-11-12 |
| [pu-05](sources/pu-05.md): Public MCP: OAuth protected-resource metadata | Public | Public.com (endpoint metadata) | official | 2026-11-12 |
| [pu-06](sources/pu-06.md): How to Trade Stocks, Options & Crypto Using Claude | Public | Public.com | official | 2026-11-12 |
| [pu-07](sources/pu-07.md): public.com llms.txt | Public | Public.com | official | 2026-11-12 |
| [pu-08](sources/pu-08.md): Release 0.1.0 · PublicDotCom/publicdotcom-mcp-server · GitHub | Public | Public.com (GitHub) | official | 2026-11-12 |
| [pu-09](sources/pu-09.md): Claude & Claude Code Connector for Stock & Options Trading on Public MCP | Public | Public.com API docs | official | 2026-11-12 |
| [rh-01](sources/rh-01.md): Onboarding an external agent \| Robinhood | Robinhood | Robinhood | official | 2026-11-12 |
| [rh-02](sources/rh-02.md): Robinhood MCP Server: What 73 Tools and an OAuth Handshake Look Like Up Close — DeskTested | Robinhood | DeskTested | third-party | 2026-11-12 |
| [rh-04](sources/rh-04.md): Trading with your agent \| Robinhood | Robinhood | Robinhood | official | 2026-11-12 |
| [rh-05](sources/rh-05.md): Robinhood Agents \| Build Your AI Trading Agent | Robinhood | Robinhood | official | 2026-11-12 |
| [rh-06](sources/rh-06.md): robinhood.com llms.txt | Robinhood | Robinhood | official | 2026-11-12 |
| [rh-07](sources/rh-07.md): Robinhood Agents overview \| Robinhood | Robinhood | Robinhood | official | 2026-11-12 |
| [rh-08](sources/rh-08.md): Setting up an agent \| Robinhood | Robinhood | Robinhood | official | 2026-11-12 |
| [rh-09](sources/rh-09.md): Agentic Credit Card \| Robinhood | Robinhood (Agentic Credit Card) | Robinhood | official | 2026-11-12 |
| [rh-10](sources/rh-10.md): Robinhood is Now Open to Agents | Robinhood | Robinhood | official | 2026-11-12 |
| [rh-11](sources/rh-11.md): Robinhood now lets your AI agents trade stocks \| TechCrunch | Robinhood | TechCrunch | third-party | 2026-11-12 |
| [rh-12](sources/rh-12.md): Agent apps \| Robinhood | Robinhood | Robinhood | official | 2026-11-12 |
| [rh-13](sources/rh-13.md): Robinhood Trading MCP: OAuth protected-resource metadata | Robinhood | Robinhood (endpoint metadata) | official | 2026-11-12 |
| [tt-01](sources/tt-01.md): GitHub - tastytrade/tastytrade-mcp: MCP server for the tastytrade open API: quotes, positions, balances, and dry-run-gated order flow for LLM agents.  | tastytrade | tastytrade (GitHub) | official | 2026-11-12 |
| [tt-02](sources/tt-02.md): Open API MCP Brings AI to Your tastytrade Account | tastytrade | tastytrade | official | 2026-11-12 |
| [tt-03](sources/tt-03.md): MCP Server · tastytrade Developer Docs | tastytrade | tastytrade Developer Docs | official | 2026-11-12 |
| [tt-04](sources/tt-04.md): OAuth2 authentication · tastytrade Developer Docs | tastytrade | tastytrade Developer Docs | official | 2026-11-12 |
| [wb-01](sources/wb-01.md): Webull Agentic Trading — Let your AI agent trade the markets | Webull | Webull | official | 2026-11-12 |
| [wb-02](sources/wb-02.md): Webull Cloud MCP Server \| Webull API | Webull | Webull Developer | official | 2026-11-12 |
| [wb-03](sources/wb-03.md): GitHub - webull-inc/webull-openapi-mcp: Webull OpenAPI MCP · GitHub | Webull | Webull (GitHub) | official | 2026-11-12 |
| [wb-04](sources/wb-04.md): GitHub - webull-inc/webull-openapi-skills · GitHub | Webull | Webull (GitHub) | official | 2026-11-12 |
| [wb-05](sources/wb-05.md): GitHub - webull-inc/webull-openapi-cli · GitHub | Webull | Webull (GitHub) | official | 2026-11-12 |
| [wb-06](sources/wb-06.md): Webull Launches Model Context Protocol, Enabling Investors to Trade Through AI in Plain Language | Webull | PR Newswire | official | 2026-11-12 |
| [wb-07](sources/wb-07.md): Webull Expands Cloud MCP to Enable AI-Powered Trading Without Coding or Installation | Webull | Webull / PR Newswire | official | 2026-11-12 |
| [wb-08](sources/wb-08.md): Webull Launches ChatGPT, Claude & Grok Connectors, CLI, and Enhanced MCP to Expand AI-Powered Investing Tools | Webull | Webull / PR Newswire | official | 2026-11-12 |
| [wb-09](sources/wb-09.md): Webull API: OAuth protected-resource metadata | Webull | Webull (endpoint metadata) | official | 2026-11-12 |
| [wb-10](sources/wb-10.md): 「Webull MCP Server」および「Webull Agent Skills」の提供開始　日本株と米国株の取引ができる公式MCP Serverの提供は日本初（※） | Webull | Webull Securities Japan | official | 2026-11-12 |
| [wf-01](sources/wf-01.md): Wells Fargo Newsroom - Wells Fargo introduces AI Teammate, bringing AI-powered support to the advisor experience | Wells Fargo | Wells Fargo | official | 2026-11-13 |
| [ws-01](sources/ws-01.md): Wealthtech Roundup: Anthropic, Schwab, Advyzon, Orion And More | Anthropic | Wealth Solutions Report | third-party | 2026-11-13 |

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20index.md&body=Page%3A%20index.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
