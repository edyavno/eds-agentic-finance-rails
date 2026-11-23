---
title: Index
summary: Every page in the wiki, generated from page headers.
page_status: current
---

# Index

**How AI agents connect to money**

How brokers, banks and payment networks let AI agents trade, pay and manage money, and who approves what.

Every page in the wiki, generated from page headers.

## For agents

- How to read and cite: [AGENTS.md](AGENTS.md). Entry point: [llms.txt](llms.txt).

## Start here

- [README.md](README.md): What this wiki is and how to use it
- [AGENTS.md](AGENTS.md): How to read and cite the wiki: where to start, source cards, unknowns, freshness
- [Overview - the race to be agent-friendly](overview.md): Which financial providers let AI agents read accounts, trade or pay, which keep them out, and what changed in 2026. Every fact links to its source.
- [Glossary](glossary.md): Short, plain-English definitions of recurring terms in this wiki, including MCP, OAuth, paper trading, payment tokens, open banking, and related agent-finance vocabulary.
- [Trading](trading.md): Trading: which brokers let AI agents trade, who approves, and every broker's key fields (generated)
- [FAQ: AI agents and money](faq.md): Short cited answers to common questions
- [Payments](payments/README.md): How AI agents pay: card networks, payment tokens, commerce and payment protocols
- [Personal money agents](personal-money/README.md): Personal money agents, bank AI tools, and how banks treat outside agents
- [Gaps - what we do not know yet](gaps.md): Open questions the wiki cannot answer yet, ranked: missing agent terms, order limits, paper trading and more, from unknown fields and reader feedback.

## Providers

- [Alpaca](providers/alpaca.md) (current): Alpaca's hosted Trading MCP uses OAuth for live and paper accounts; a local MCP and a CLI use API keys. No broker-side per-order approval is documented.
- [Coinbase](providers/coinbase.md) (current): Coinbase for Agents: a remote MCP with OAuth for allowlisted clients, or a local CLI with an API key. Coinbase enforces trade limits, and a dedicated portfolio is optional.
- [Interactive Brokers](providers/interactive-brokers.md) (current): Remote MCP connector. By default the AI drafts trade instructions you review and submit; eligible accounts can enable Autonomous Trading in an AI Partition.
- [Kraken](providers/kraken.md) (current): Kraken ships a local MCP server with its CLI. It runs on your own machine, can trade live only when you turn on trading services, and asks you to approve each order, withdrawal or transfer.
- [Public](providers/public.md) (current): Public runs a hosted MCP server at mcp.public.com/mcp for Claude, ChatGPT, Codex, Meta Muse, Perplexity and Grok. Most apps sign in with OAuth; Muse uses a Public API key. Every trade is a real order, with no paper mode.
- [Robinhood](providers/robinhood.md) (current): Remote Trading MCP with OAuth. Agents read all Robinhood accounts but trade only in a dedicated agentic (MCP) account; per-order approval is an optional toggle.
- [Scalable Capital](providers/scalable-capital.md) (current): Scalable Capital runs an MCP server with four access levels you set in its web app. Buy and sell orders need Full access, and each order needs your fresh, explicit confirmation of a preview.
- [Webull](providers/webull.md) (current): Webull's hosted Cloud MCP prepares trades you confirm in the Webull app; its local OpenAPI MCP places orders directly, with risk limits and a sandbox default.

## Payments

- [Payments](payments/README.md) (current): How AI agents pay: card-network agent programs, payment tokens, wallets, protocols and agent cards, each with a sourced page, plus merchants that ban agents.
- [Aave MCP](payments/aave-mcp.md) (current): Aave's official MCP server for Aave V3 and V4. An agent can read markets and positions, including health factor, simulate an action, and prepare an unsigned transaction. The user's wallet signs every state change.
- [AgentBank](payments/agentbank.md) (current): An MCP server that lets an AI agent collect, hold, convert and send money, including to bank accounts in local currency, using crypto rails. The owner confirms every payment, and an approval threshold adds an extra check.
- [Amazon Bedrock AgentCore payments](payments/agentcore-payments.md) (current): AWS service that lets an agent pay for APIs, MCP servers and content over x402 and MPP within a per-session budget. Since 2026-11-19 it can also pay AWS Marketplace sellers in US dollars on the AWS bill, with no crypto wallet.
- [Agentic Commerce Protocol (ACP)](payments/agentic-commerce-protocol.md) (current): An open standard for buyers, their AI agents and businesses to complete purchases. OpenAI and Stripe maintain the spec, which is in beta.
- [AP2 (Agent Payments Protocol)](payments/ap2.md) (current): An open protocol that records what a user authorized an agent to buy as signed mandates: a Checkout Mandate for the merchant, a Payment Mandate for payment.
- [ChatGPT Wallet](payments/chatgpt-wallet.md) (current): OpenAI's wallet that lets an agent in ChatGPT pay for you. You approve each purchase with a biometric check, and the card network supplies a payment token so the agent and merchant never see your real card number.
- [Lightspark Agent Accounts](payments/lightspark-agent-accounts.md) (current): Lightspark accounts where an AI agent holds, spends, sends and receives money within limits and approvals the account holder sets. It pays Visa merchants with a card valid for one purchase. Sold to companies that build agents.
- [Link wallet for agents](payments/link-wallet-for-agents.md) (current): Stripe's Link wallet for agents lets a person approve each purchase an agent makes, with a one-time card or shared payment token. Muse, Grok Bot, Instinct and Claude Duet use Link or a wallet like it.
- [Mastercard Agent Pay](payments/mastercard-agent-pay.md) (current): Mastercard's program for agent payments. Agents are registered and verified before they can pay, and they pay with agentic tokens. Merchants can verify agents with Web Bot Auth.
- [Merchants and outside agents](payments/merchants-and-outside-agents.md) (current): Some merchants forbid AI agents from buying. eBay, United and Booking.com ban them without permission, and Target allows only a short list of approved agents.
- [PayPal](payments/paypal.md) (current): PayPal offers an MCP server, run locally or hosted, and an agent toolkit that let AI agents use PayPal business APIs such as orders, invoices, subscriptions and disputes.
- [Rain Agent Vaults](payments/rain-agent-vaults.md) (current): Rain's funded balance for AI agents. The owner funds a vault and sets rules, and the agent pays with a single-use virtual Visa or Mastercard card issued for each purchase. Sold to companies that build agents.
- [Robinhood Agentic Credit Card](payments/robinhood-agentic-credit-card.md) (current): A virtual card inside the Robinhood Gold Card that your AI agent uses through the Robinhood Banking MCP. You approve each purchase or set a required monthly limit.
- [Stripe](payments/stripe.md) (current): Stripe offers shared payment tokens, which give a seller scoped, time-limited use of a customer's payment method for agent purchases, plus an official MCP server at mcp.stripe.com.
- [Visa CLI](payments/visa-cli.md) (current): A Visa Crypto Labs product: after a US Visa card check, an agent gets a signing key, is listed in the Visa Agent Directory, and can take paid tasks and pay HTTP 402 requests in OUSD within limits the owner set.
- [Visa Intelligent Commerce](payments/visa-intelligent-commerce.md) (current): Visa's agent payments program: approved agent builders get tokenized Visa credentials, network-level controls and consumer-approved purchase instructions.
- [x402](payments/x402.md) (current): An open payment standard built on HTTP 402 Payment Required: the server asks for payment inside the request, and the client pays and retries. Coinbase uses it.

## Personal money agents

- [Personal money agents](personal-money/README.md) (current): AI agents that work with a person's bank and card data, the tools that connect them, banks' own AI tools, and how big banks treat outside agents.
- [Banks and outside agents](personal-money/banks-and-outside-agents.md) (current): What news reports say about big US banks blocking or limiting outside AI agents, including Chase's block on agents shopping with a card number, the read-only middle ground, and the US data-rights rule in the background.
- [Finances in ChatGPT](personal-money/chatgpt-finances.md) (current): Finances in ChatGPT reads your accounts through Plaid and credit reports through Experian, in the US. OpenAI says it cannot move money, pay bills, trade or change account settings.
- [Claude Duet](personal-money/claude-duet.md) (current): Claude Duet is Anthropic's proactive agent app, in research preview. It asks before it pays, sends or deletes, pays with a one-time Link card, and cannot trade or move money between accounts.
- [Claude Personal Finance](personal-money/claude-personal-finance.md) (current): Claude's Personal Finance feature reads your balances and transactions from banks you link through Plaid, read-only. It cannot move, manage or invest money. It is in beta on paid US plans.
- [Gemini with Google Wallet](personal-money/gemini-google-wallet.md) (current): Google's Gemini app can read your spending from Google Wallet and linked bank and card accounts to answer money questions. It is read-only and cannot move money.
- [Grok Bot](personal-money/grok-bot.md) (current): Grok Bot can read balances, spending and investments from accounts you link through Plaid, read-only. It can also pay with a Link one-time card or X Money, with a prompt to approve each purchase.
- [Instinct](personal-money/instinct.md) (current): Instinct is a personal assistant that works in iMessage and WhatsApp. Plaid says it powers read-only account connections for US users, and Stripe says Link helps power its payments.
- [JPMorgan Smart Cash](personal-money/jpmorgan-smart-cash.md) (current): A JPMorgan Chase AI tool in a targeted pilot. Per a news report, it aims to predict a user's cash flow and move funds to maximize yield. Only a news source is cited.
- [Meta Muse](personal-money/meta-muse.md) (current): Meta's personal AI agent. Its finance features use Plaid so people can connect bank, card, investment and mortgage accounts for personalized money guidance.
- [Nous](personal-money/nous.md) (current): A UK household AI agent that tracks bills and subscriptions, switches providers and cancels services for you. You choose how much it decides on its own. It reads bank data through an FCA-regulated open banking provider but cannot move money.
- [OpenAI dots](personal-money/openai-dots.md) (current): OpenAI's dots are always-on agents with their own cloud computer. They can buy with a card saved on a merchant site after approval. Whether a dot can read your Finances data is unknown.
- [Perplexity Personal CFO](personal-money/perplexity-personal-cfo.md) (current): Perplexity lets people connect accounts through Plaid and ask about their own money, read-only. Plaid reports it in the US with Perplexity Computer and in 17 European countries as Personal CFO.
- [Plaid MCP servers](personal-money/plaid.md) (current): Plaid's MCP servers are developer tools: a hosted Dashboard MCP for diagnostics and a local sandbox MCP. They do not give agents access to users' accounts.
- [Starling Assistant](personal-money/starling-assistant.md) (current): Starling Bank's in-app AI assistant will set up payments from voice or text, and the customer approves each one with a tap. It reaches all retail customers by the end of 2026.
- [X Money](personal-money/x-money.md) (current): X Money is a US money account inside the X app, run by X Payments LLC with Cross River Bank. Through the Grok Bot plugin, an agent can read the balance and history, and send or pay with approval per action.

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
- [Institutional markets](rails/institutional-markets.md) (current): How AI agents negotiate and trade between firms, starting with a pilot Treasury bill negotiation by BNY and Microsoft in which humans approved the final terms and the agents could not execute.
- [Local MCP servers and CLIs](rails/local-mcp-and-cli.md) (current): Self-run MCP servers and CLIs authenticate with API keys you hold, so their guardrails are only as strong as your local setup.
- [Mandates and data access](rails/mandates-and-data-access.md) (current): Protocols that record what a user authorized an agent to do, and the US data-rights rule that may shape agent access to bank data.
- [Remote MCP with OAuth](rails/remote-mcp-oauth.md) (current): How hosted broker MCP servers advertise their OAuth setup, how AI clients register with them, and why a broker's allowlist of clients still matters.

## Build it

- [Build it](build/README.md) (current): Practical notes for engineers and coding agents connecting to broker MCP servers safely.
- [Connect an MCP client](build/connect-an-mcp-client.md) (current): The connection commands and server URLs each launch broker documents for MCP clients, from the providers' own setup pages. Start with paper or sandbox.
- [Human-in-the-loop patterns](build/human-in-the-loop.md) (current): Where to put human approval in an agent trading flow, and why broker-side approval beats client-side approval.
- [Starter prompts](build/starter-prompts.md) (current): Copy-paste prompts for AI assistants: questions this wiki can answer, then prompts for coding agents. Cite pages and say unknown rather than guess.

## Comparisons

- [Comparisons](comparisons/README.md) (current): Side-by-side views of how providers handle approval, read access and safety for AI agents. Every value is sourced or says unknown.
- [Launch brokers compared: approval and safety posture](comparisons/launch-brokers.md) (current): Side-by-side view of how the five launch brokers let agents trade, who approves orders, and where the guardrails are enforced.

## Analyses

- [Analyses](analyses/README.md) (current): Saved answers to questions asked of the wiki, each with cited sources, starting with a comparison of the AP2, ACP and x402 agent payment protocols.
- [AP2 vs ACP vs x402: which AI agent payment protocol does what?](analyses/ap2-vs-acp-vs-x402.md) (current): AP2, ACP and x402 compared side by side. What each agent payment protocol does, who maintains it, what it costs and its limits, with a sourced table and FAQ.

## What changed

- [What changed](changelog/README.md) (current): Every update to the wiki, newest first, with the current size of the wiki in numbers. Generated from page headers.
- [What changed: 2026-11-23](changelog/2026-11-23.md) (current): Visa CLI, Klarna in Adyen Agentic checkout, Stripe agent fund tools, PayPal Agent Ready, pay.sh, and Aave's official MCP are on the payments pages. A Consumer Reports and Affirm draft covers payment choice; a Fed governor spoke about bank-account agents. Webull's local MCP adds Australia.
- [What changed: 2026-11-22](changelog/2026-11-22.md) (current): Stripe's chief economist shared Link agent-wallet spend figures, including nearly 80-fold growth from September to mid-November. The Link page has a spend diagram; Trading moved to /trading with a broker-approval diagram, and personal-money records are folded.
- [What changed: 2026-11-21](changelog/2026-11-21.md) (current): The starter prompts page now has research questions and coding-agent prompts, the front page has a Try a starter prompt link, and Coinbase has a table of which AI apps trade the most.
- [What changed: 2026-11-20](changelog/2026-11-20.md) (current): Citi and Chase user agreements, Singapore's planned Know Your Agent protocol, AWS AgentCore payments, Lightspark, BNY and Microsoft's Treasury bill negotiation, and six more updates.
- [What changed: 2026-11-19](changelog/2026-11-19.md) (current): Chase's reported block on agents that shop with a card number, how Stripe's Link gets around it, adding a Chase card to ChatGPT Wallet, connecting eight providers from your AI app, new pages for Public, Scalable Capital and Kraken, and Mastercard's developer MCP server and Agent Pay for Machines.
- [What changed: 2026-11-18](changelog/2026-11-18.md) (current): Coinbase Agent Controls and ChatGPT confirmation cards, Public's order gate, Visa Agentic Ready, a live Mastercard flight purchase, Plaid Agent Detection, Gemini, Starling and Wealth.com, plus Grok Bot, X Money, Claude, ChatGPT Finances, dots, Instinct and Perplexity.
- [What changed: 2026-11-17](changelog/2026-11-17.md) (current): A comparison of the AP2, ACP and x402 agent payment protocols, question-style headings, answer-first openings, shorter page descriptions and an Updated date label.
- [What changed: 2026-11-15](changelog/2026-11-15.md) (current): A shorter front page, a trading-only Trading page, a cited FAQ, record tables, a What changed home page, search and agent metadata, and new pages on ChatGPT Wallet, Rain Agent Vaults, AgentBank, Nous and merchants that forbid agents.
- [What changed: 2026-11-14](changelog/2026-11-14.md) (current): Added Payments and Personal money agents sections with one page per program, a What we cover overview on the front page, official ERC-8004, a glossary, and a front-page refresh.
- [What changed: 2026-11-13](changelog/2026-11-13.md) (current): Added a thin advisor-agents section, a third-party Schwab RIABiz source, official Coinbase agent-feedback docs, and related official and third-party source cards.
- [What changed: 2026-11-12](changelog/2026-11-12.md) (current): First draft of the wiki - five launch broker pages, 103 source cards, approval-model taxonomy and agent packaging.

## Schema

- [schema/provider.schema.json](schema/provider.schema.json): provider page headers
- [schema/source.schema.json](schema/source.schema.json): source card headers
- [schema/program.schema.json](schema/program.schema.json): payments and personal money program page headers
- [schema/page.schema.json](schema/page.schema.json): all other page headers

## Sources (245)

| Card | Subject | Publisher | Authority | Retrieved |
|---|---|---|---|---|
| [aa-01](sources/aa-01.md): Aave MCP | Aave MCP | Aave | official | 2026-11-23 |
| [aa-02](sources/aa-02.md): Get Started with Aave MCP | Aave MCP | Aave | official | 2026-11-23 |
| [aa-03](sources/aa-03.md): Aave MCP llms.txt | Aave MCP | Aave | official | 2026-11-23 |
| [aa-04](sources/aa-04.md): Aave MCP Safety | Aave MCP | Aave | official | 2026-11-23 |
| [aa-05](sources/aa-05.md): Aave MCP Tools | Aave MCP | Aave | official | 2026-11-23 |
| [aa-06](sources/aa-06.md): GitHub - aave/skills | Aave MCP | Aave (GitHub) | official | 2026-11-23 |
| [aa-07](sources/aa-07.md): @aave/mcp | Aave MCP | npm (package published by Aave) | official | 2026-11-23 |
| [ag-01](sources/ag-01.md): Connect your AI agent to real-world money \| AgentBank | AgentBank | AgentBank | official | 2026-11-19 |
| [ag-02](sources/ag-02.md): Security and wallet control \| AgentBank | AgentBank | AgentBank | official | 2026-11-15 |
| [ag-03](sources/ag-03.md): AgentBank FAQ: banking for AI agents \| AgentBank | AgentBank | AgentBank | official | 2026-11-15 |
| [ag-04](sources/ag-04.md): Connect your agent - AgentBank docs | AgentBank | AgentBank | official | 2026-11-19 |
| [ag-05](sources/ag-05.md): Connect ChatGPT - AgentBank docs | AgentBank | AgentBank | official | 2026-11-19 |
| [ag-06](sources/ag-06.md): Connect Claude - AgentBank docs | AgentBank | AgentBank | official | 2026-11-19 |
| [ag-07](sources/ag-07.md): Account revocation - AgentBank docs | AgentBank | AgentBank | official | 2026-11-19 |
| [ag-08](sources/ag-08.md): Configure thresholds - AgentBank docs | AgentBank | AgentBank | official | 2026-11-19 |
| [al-01](sources/al-01.md): Alpaca - Trade with AI Using Alpaca's MCP Server | Alpaca | Alpaca | official | 2026-11-19 |
| [al-02](sources/al-02.md): GitHub - alpacahq/alpaca-mcp-server: Alpaca’s official MCP Server lets you trade stocks, ETFs, crypto, and options, run data analysis, and build strat | Alpaca | Alpaca (GitHub) | official | 2026-11-19 |
| [al-03](sources/al-03.md): GitHub - alpacahq/agentic: Multi-platform plugin marketplace for Alpaca APIs · GitHub | Alpaca | Alpaca (GitHub) | official | 2026-11-19 |
| [al-04](sources/al-04.md): GitHub - alpacahq/alpaca-skills: Agent skills for Alpaca's Trading API and Broker API: drop-in SKILL.md files for AI coding assistants · GitHub | Alpaca | Alpaca (GitHub) | official | 2026-11-12 |
| [al-05](sources/al-05.md): GitHub - alpacahq/cli: CLI for Trading API · GitHub | Alpaca | Alpaca (GitHub) | official | 2026-11-12 |
| [al-07](sources/al-07.md): Alpaca Launches MCP Servers in Public Beta for Broker Partners. | Alpaca | Alpaca | official | 2026-11-12 |
| [al-08](sources/al-08.md): Broker API MCP (Alpaca Docs) | Alpaca | Alpaca Docs | official | 2026-11-12 |
| [al-09](sources/al-09.md): Trading API MCP | Alpaca | Alpaca Docs | official | 2026-11-19 |
| [an-01](sources/an-01.md): Mastercard and Ant International Advance Trusted Agentic Commerce in Asia Pacific (Ant International page) | Mastercard Agent Pay | Mastercard (posted by Ant International) | official | 2026-11-20 |
| [an-02](sources/an-02.md): Mastercard and Ant International Advance Trusted Agentic Commerce in Asia Pacific (PR Newswire) | Mastercard Agent Pay | Mastercard (via PR Newswire) | official | 2026-11-20 |
| [aw-01](sources/aw-01.md): AWS Marketplace now supports agentic payments with AgentCore | Amazon Bedrock AgentCore payments | Amazon Web Services | official | 2026-11-20 |
| [aw-02](sources/aw-02.md): Enable AI agents to pay for AWS Marketplace x402 products with Amazon Bedrock AgentCore payments | Amazon Bedrock AgentCore payments | Amazon Web Services (AWS Machine Learning Blog) | official | 2026-11-20 |
| [aw-03](sources/aw-03.md): Amazon Bedrock AgentCore payments: Enable secure microtransaction payments for AI agents | Amazon Bedrock AgentCore payments | Amazon Web Services (AgentCore Developer Guide) | official | 2026-11-20 |
| [ax-01](sources/ax-01.md): AXS Pioneers Agentic Bill Payments in South-East Asia, Opening Its Bill Payment Network to AI-Powered Partners | AXS agentic bill payments | AXS | official | 2026-11-20 |
| [bk-01](sources/bk-01.md): Booking.com: Terms and Conditions (Customer terms of service) | Booking.com | Booking.com | official | 2026-11-18 |
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
| [bl-12](sources/bl-12.md): AI bots are using credit cards. Banks are racing to keep up. (The Wall Street Journal, via Mint) | JPMorgan Chase | The Wall Street Journal (syndicated on Mint) | third-party | 2026-11-19 |
| [bl-13](sources/bl-13.md): JPMorgan Stops AI Agents From Using Customer Credit Cards (PYMNTS) | JPMorgan Chase | PYMNTS | third-party | 2026-11-19 |
| [bn-01](sources/bn-01.md): BNY and Microsoft Complete First Agentic Negotiation of a U.S. Treasury Trade | BNY and Microsoft Treasury bill negotiation | BNY | official | 2026-11-20 |
| [cb-01](sources/cb-01.md): Coinbase MCP - Coinbase Developer Documentation | Coinbase | Coinbase Developer Platform | official | 2026-11-12 |
| [cb-03](sources/cb-03.md): Coinbase for Agents setup skill (skill.md) | Coinbase | Coinbase Developer Platform | official | 2026-11-12 |
| [cb-04](sources/cb-04.md): Coinbase for Agents MCP: OAuth protected-resource metadata | Coinbase | Coinbase (endpoint metadata) | official | 2026-11-12 |
| [cb-05](sources/cb-05.md): CDP MCP - Coinbase Developer Documentation | Coinbase | Coinbase Developer Platform | official | 2026-11-12 |
| [cb-06](sources/cb-06.md): Coinbase Developer Platform docs llms.txt | Coinbase | Coinbase Developer Platform | official | 2026-11-12 |
| [cb-07](sources/cb-07.md): Coinbase for Agents: Your AI Agent Can Now Trade and Pay with Coinbase | Coinbase | Coinbase | official | 2026-11-12 |
| [cb-08](sources/cb-08.md): Coinbase’s new tool can help agents trade and pay for premium research \| TechCrunch | Coinbase | TechCrunch | third-party | 2026-11-12 |
| [cb-09](sources/cb-09.md): Coinbase MCP - Coinbase Developer Documentation | Coinbase | Coinbase Developer Platform | official | 2026-11-19 |
| [cb-10](sources/cb-10.md): Coinbase for Agents introduces new Agent Controls | Coinbase | Coinbase | official | 2026-11-18 |
| [cb-11](sources/cb-11.md): Coinbase Advisor | Coinbase | Coinbase | official | 2026-11-20 |
| [cb-12](sources/cb-12.md): System Update: Take control of your money with Coinbase | Coinbase | Coinbase | official | 2026-11-20 |
| [cb-13](sources/cb-13.md): Coinbase on X: "Which AI agent is the most popular on Coinbase?" (with video chart) | Coinbase | Coinbase (@coinbase on X) | official | 2026-11-21 |
| [ci-01](sources/ci-01.md): Citi Online User Agreement (Section H: Use of Third-party AI Agents) | Citi | Citi | official | 2026-11-20 |
| [cl-01](sources/cl-01.md): Use Personal Finance in Claude (Claude Help Center) | Claude Personal Finance | Anthropic | official | 2026-11-18 |
| [cl-02](sources/cl-02.md): Introducing Personal Finance in Claude | Claude Personal Finance | Anthropic | official | 2026-11-18 |
| [cl-03](sources/cl-03.md): Claude Duet safety, privacy and security | Claude Duet | Anthropic | official | 2026-11-18 |
| [cl-04](sources/cl-04.md): Introducing Claude Duet | Claude Duet | Anthropic | official | 2026-11-18 |
| [cr-01](sources/cr-01.md): A Consumer-First Standard for AI Payments (Affirm and Consumer Reports case study) | Payment Choice Framework | Affirm and Consumer Reports | official | 2026-11-23 |
| [cr-02](sources/cr-02.md): GitHub - consumer-reports-innovation-lab/payment-choice-framework | Payment Choice Framework | Consumer Reports Innovation Lab (GitHub), with Affirm | official | 2026-11-23 |
| [eb-01](sources/eb-01.md): User Agreement \| eBay | eBay | eBay | official | 2026-11-15 |
| [fr-01](sources/fr-01.md): Speech by Governor Barr: Some Potential Financial Stability Implications of Artificial Intelligence | Banks and outside agents | Board of Governors of the Federal Reserve System | official | 2026-11-23 |
| [gb-01](sources/gb-01.md): Grok Bot on X: "Grok Bot now connects to your finances" (with follow-up post) | Grok Bot | Grok Bot (@bot on X) | official | 2026-11-18 |
| [gb-02](sources/gb-02.md): Finance plugin README (cursor/plugins, third_party/finance) | Grok Bot | cursor/plugins (GitHub) | official | 2026-11-18 |
| [gb-03](sources/gb-03.md): Vault and secure sign-in (Grok Bot docs) | Grok Bot | xAI Docs | official | 2026-11-18 |
| [gb-04](sources/gb-04.md): Approvals, security, and privacy (Grok Bot docs) | Grok Bot | xAI Docs | official | 2026-11-18 |
| [gb-05](sources/gb-05.md): Grok Bot changelog | Grok Bot | xAI | official | 2026-11-18 |
| [gg-01](sources/gg-01.md): Connect Google Wallet to Gemini for personal finance insights | Gemini and Google Wallet | Google | official | 2026-11-18 |
| [gg-02](sources/gg-02.md): Get info & personalized insights from Google Wallet with Gemini Apps | Gemini and Google Wallet | Google Gemini Apps Help | official | 2026-11-18 |
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
| [jp-01](sources/jp-01.md): JPMorganChase and Plaid announce an extension to their data access agreement | JPMorgan and Plaid | JPMorganChase | official | 2026-11-18 |
| [jp-02](sources/jp-02.md): Digital Services Agreement (J.P. Morgan Chase) | JPMorgan Chase | JPMorgan Chase | official | 2026-11-20 |
| [kr-01](sources/kr-01.md): MCP server - Kraken docs | Kraken | Kraken | official | 2026-11-19 |
| [kr-02](sources/kr-02.md): kraken-cli - Kraken docs | Kraken | Kraken | official | 2026-11-19 |
| [kr-03](sources/kr-03.md): GitHub - krakenfx/kraken-cli: Kraken CLI · GitHub | Kraken | Kraken (GitHub) | official | 2026-11-19 |
| [ls-01](sources/ls-01.md): Lightspark Launches Agent Accounts for AI Agents to Make and Receive Payments | Lightspark Agent Accounts | Lightspark (via GlobeNewswire) | official | 2026-11-20 |
| [ls-02](sources/ls-02.md): Agent Accounts (Lightspark documentation) | Lightspark Agent Accounts | Lightspark (documentation) | official | 2026-11-20 |
| [ma-01](sources/ma-01.md): Keynote address by the Managing Director of the Monetary Authority of Singapore at the Singapore FinTech Festival 2026 | Monetary Authority of Singapore (Know Your Agent) | Monetary Authority of Singapore | official | 2026-11-20 |
| [mi-01](sources/mi-01.md): Trusted intelligence in banking, insurance, and capital markets: Six firms show how | BNY and Microsoft Treasury bill negotiation | Microsoft (Microsoft Cloud Blog) | official | 2026-11-20 |
| [mi-02](sources/mi-02.md): Microsoft Ignite 2026: Empowering human ambition, intelligence and trust | BNY and Microsoft Treasury bill negotiation | Microsoft (Microsoft Source) | official | 2026-11-20 |
| [mm-01](sources/mm-01.md): How Muse works with payments (Meta Help Center) | Meta Muse | Meta | official | 2026-11-18 |
| [mm-02](sources/mm-02.md): How Muse works with Connectors (Meta Help Center) | Meta Muse | Meta | official | 2026-11-18 |
| [mm-03](sources/mm-03.md): Introducing Muse (Meta newsroom) | Meta Muse | Meta | official | 2026-11-18 |
| [np-02](sources/np-02.md): PrimeXBT Launches AI-Assisted Trading with MCP Integration, Connecting ChatGPT and Claude to Trading Accounts | PrimeXBT | GlobeNewswire | official | 2026-11-12 |
| [ns-01](sources/ns-01.md): Frequently asked questions \| Nous | Nous | Nous | official | 2026-11-15 |
| [ns-02](sources/ns-02.md): Terms of use \| Nous | Nous | Nous | official | 2026-11-15 |
| [ns-03](sources/ns-03.md): We've raised $17M to get Nous into every household that's had enough of life admin | Nous | Nous | official | 2026-11-15 |
| [nt-01](sources/nt-01.md): NETS and Ant International Deepen Partnership to Empower Singapore’s Businesses for a Future in Agentic Commerce with Agentic Mobile Protocol | Agentic Mobile Protocol | NETS (Network for Electronic Transfers) | official | 2026-11-20 |
| [oa-01](sources/oa-01.md): Introducing ChatGPT Wallet | ChatGPT Wallet | OpenAI | official | 2026-11-15 |
| [oa-02](sources/oa-02.md): Making purchases with ChatGPT Wallet | ChatGPT Wallet | OpenAI Help Center | official | 2026-11-19 |
| [oa-03](sources/oa-03.md): ChatGPT Wallet terms | ChatGPT Wallet | OpenAI | official | 2026-11-15 |
| [oa-04](sources/oa-04.md): Accept payments - OpenAI Commerce | ChatGPT Wallet | OpenAI Developers | official | 2026-11-15 |
| [oa-05](sources/oa-05.md): Finances in ChatGPT (OpenAI Help Center) | ChatGPT Finances | OpenAI | official | 2026-11-18 |
| [oa-06](sources/oa-06.md): A new personal finance experience in ChatGPT (OpenAI) | ChatGPT Finances | OpenAI | official | 2026-11-18 |
| [oa-07](sources/oa-07.md): Dots privacy, security, and safety FAQs (OpenAI Help Center) | OpenAI dots | OpenAI | official | 2026-11-18 |
| [oa-08](sources/oa-08.md): Introducing dots (OpenAI) | OpenAI dots | OpenAI | official | 2026-11-18 |
| [oa-09](sources/oa-09.md): Getting started with your dot (OpenAI Help Center) | OpenAI dots | OpenAI | official | 2026-11-18 |
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
| [pb-06](sources/pb-06.md): Introducing Agent Detection: building trust in the age of agentic finance | Plaid | Plaid | official | 2026-11-18 |
| [pb-08](sources/pb-08.md): Plaid is powering personalized financial insights with Google Wallet in the Gemini app | Gemini and Google Wallet | Plaid | official | 2026-11-18 |
| [pb-09](sources/pb-09.md): Instinct gets the full financial picture with Plaid | Instinct | Plaid | official | 2026-11-18 |
| [pb-10](sources/pb-10.md): Plaid powers financial insights in Claude | Claude Personal Finance | Plaid | official | 2026-11-18 |
| [pb-11](sources/pb-11.md): ChatGPT personal finance experience, powered by Plaid | ChatGPT Finances | Plaid | official | 2026-11-18 |
| [pb-12](sources/pb-12.md): Plaid and Perplexity expand integration to power personalized financial insights | Perplexity Personal CFO | Plaid | official | 2026-11-18 |
| [pb-13](sources/pb-13.md): Perplexity brings Personal CFO to Europe with Plaid | Perplexity Personal CFO | Plaid | official | 2026-11-18 |
| [pb-14](sources/pb-14.md): Link overview (Plaid Docs) | Plaid | Plaid Docs | official | 2026-11-18 |
| [pb-15](sources/pb-15.md): Link OAuth guide (Plaid Docs) | Plaid | Plaid Docs | official | 2026-11-18 |
| [pb-16](sources/pb-16.md): Data Transparency Messaging migration guide (Plaid Docs) | Plaid | Plaid Docs | official | 2026-11-18 |
| [pb-17](sources/pb-17.md): Choosing how to initialize products (Plaid Docs) | Plaid | Plaid Docs | official | 2026-11-18 |
| [pb-18](sources/pb-18.md): Items API reference (Plaid Docs) | Plaid | Plaid Docs | official | 2026-11-18 |
| [pb-19](sources/pb-19.md): Transactions API reference (Plaid Docs) | Plaid | Plaid Docs | official | 2026-11-18 |
| [pb-20](sources/pb-20.md): Announcing Plaid Portal: An ongoing commitment to data privacy | Plaid | Plaid | official | 2026-11-18 |
| [pb-21](sources/pb-21.md): Can I remove app access or delete my data from Plaid? (Plaid Consumer Help Center) | Plaid | Plaid Consumer Help Center | official | 2026-11-18 |
| [pb-22](sources/pb-22.md): Product Updates: August 2026 (Plaid) | Plaid | Plaid | official | 2026-11-18 |
| [pm-01](sources/pm-01.md): Visa Developer Center | Visa Intelligent Commerce | Visa Developer | official | 2026-11-12 |
| [pm-02](sources/pm-02.md): MCP docs \| Visa Developer | Visa Intelligent Commerce | Visa Developer | official | 2026-11-12 |
| [pm-03](sources/pm-03.md): GitHub - visa/trusted-agent-protocol: Establishing a universal standard of trust between AI agents and merchants for the next phase of agentic commerc | Visa Trusted Agent Protocol | Visa (GitHub) | official | 2026-11-12 |
| [pm-04](sources/pm-04.md): Visa Opens the Door to AI-Driven Shopping for Businesses Worldwide \| Visa | Visa Intelligent Commerce | Visa | official | 2026-11-12 |
| [pm-05](sources/pm-05.md): Mastercard Agent Pay: secure, scalable and trusted agentic AI | Mastercard Agent Pay | Mastercard | official | 2026-11-12 |
| [pm-06](sources/pm-06.md): Agentic token framework: Driving trusted AI transactions | Mastercard Agent Pay | Mastercard | official | 2026-11-12 |
| [pm-07](sources/pm-07.md): GitHub - agentic-commerce-protocol/agentic-commerce-protocol: The Agentic Commerce Protocol (ACP) is an interaction model and open standard for connec | Agentic Commerce Protocol (OpenAI/Stripe) | ACP (GitHub) | official | 2026-11-12 |
| [pm-08](sources/pm-08.md): Shared payment tokens \| Stripe Documentation | Stripe | Stripe Docs | official | 2026-11-12 |
| [pm-09](sources/pm-09.md): Model Context Protocol (MCP) \| Stripe Documentation | Stripe | Stripe Docs | official | 2026-11-19 |
| [pm-10](sources/pm-10.md): MCP server quickstart guide \| PayPal Developer | PayPal | PayPal Developer | official | 2026-11-12 |
| [pm-11](sources/pm-11.md): Agent toolkit quickstart guide \| PayPal Developer | PayPal | PayPal Developer | official | 2026-11-12 |
| [pm-12](sources/pm-12.md): GitHub - google-agentic-commerce/AP2: Building a Secure and Interoperable Future for AI-Driven Payments. · GitHub | Google AP2 | Google (GitHub) | official | 2026-11-12 |
| [pm-13](sources/pm-13.md): AP2 - Agent Payments Protocol Documentation | Google AP2 | AP2 Protocol | official | 2026-11-12 |
| [pm-14](sources/pm-14.md): GitHub - x402-foundation/x402: A payments protocol for the internet. Built on HTTP. · GitHub | x402 | x402 Foundation (GitHub) | official | 2026-11-12 |
| [pm-15](sources/pm-15.md): x402 specification v2 | x402 | x402 Foundation (GitHub) | official | 2026-11-12 |
| [pm-16](sources/pm-16.md): Visa Expands Agentic Ready to Help Scale Trusted AI Commerce Globally | Visa Intelligent Commerce | Visa | official | 2026-11-18 |
| [pm-17](sources/pm-17.md): Travelport, Booked AI, Basis Theory, and Mastercard complete live end-to-end agentic flight purchase | Mastercard Agent Pay | Mastercard | official | 2026-11-18 |
| [pm-18](sources/pm-18.md): Model Context Protocol (MCP) \| Stripe Documentation (Markdown version) | Stripe | Stripe Docs | official | 2026-11-19 |
| [pm-19](sources/pm-19.md): Mastercard Developers Agent Toolkit | Mastercard Developers MCP server | Mastercard Developers | official | 2026-11-19 |
| [pm-20](sources/pm-20.md): Use the MCP SDK (Mastercard Developers Agent Toolkit FAQ) | Mastercard Developers MCP server | Mastercard Developers | official | 2026-11-19 |
| [pm-21](sources/pm-21.md): GitHub - Mastercard/developers-agent-toolkit | Mastercard Developers MCP server | Mastercard (GitHub) | official | 2026-11-19 |
| [pm-22](sources/pm-22.md): Mastercard unveils new tools and collaborations to power smarter, safer agentic commerce | Mastercard Developers MCP server | Mastercard | official | 2026-11-19 |
| [pm-23](sources/pm-23.md): What happens when AI agents start paying each other? Watch Mastercard Agent Pay for Machines in action | Mastercard Agent Pay for Machines | Mastercard | official | 2026-11-19 |
| [pm-24](sources/pm-24.md): Mastercard Open Finance US (Mastercard Developers documentation) | Mastercard Open Finance US | Mastercard Developers | official | 2026-11-19 |
| [pm-25](sources/pm-25.md): Visa Expands Agentic Ready to Help Scale Trusted AI Commerce across Europe | Visa Intelligent Commerce | Visa (Visa UK newsroom) | official | 2026-11-20 |
| [pm-26](sources/pm-26.md): CORRECTING and REPLACING Visa Expands Agentic Ready to Help Scale Trusted AI Commerce Globally | Visa Intelligent Commerce | Visa | official | 2026-11-20 |
| [pm-27](sources/pm-27.md): Visa CLI docs: Introduction | Visa CLI | Visa CLI docs (Visa Crypto Labs) | official | 2026-11-23 |
| [pm-28](sources/pm-28.md): Visa CLI docs: What's live today | Visa CLI | Visa CLI docs (Visa Crypto Labs) | official | 2026-11-23 |
| [pm-29](sources/pm-29.md): Adyen Merchants Can Now Offer Klarna in AI Agent Checkout | Klarna / Adyen Agentic | Klarna and Adyen (Business Wire release on Klarna's investor site) | official | 2026-11-23 |
| [pm-30](sources/pm-30.md): Give your agents controlled access to analyze your data and move funds | Stripe | Stripe | official | 2026-11-23 |
| [pm-31](sources/pm-31.md): Issuing for agents - Stripe Documentation | Stripe | Stripe Docs | official | 2026-11-23 |
| [pm-32](sources/pm-32.md): Agent Ready overview \| PayPal Developer | PayPal | PayPal Developer | official | 2026-11-23 |
| [pm-33](sources/pm-33.md): pay.sh | pay.sh | pay.sh | official | 2026-11-23 |
| [pu-01](sources/pu-01.md): Public MCP Server for trading on AI platforms | Public | Public.com | official | 2026-11-19 |
| [pu-02](sources/pu-02.md): Connect the Public Hosted MCP Server to Claude, ChatGPT, Codex, Muse, Perplexity, and Grok \| AI Trading Setup | Public | Public.com API docs | official | 2026-11-19 |
| [pu-03](sources/pu-03.md): Public Trading API Changelog \| Latest Updates & Release Notes | Public | Public.com API docs | official | 2026-11-12 |
| [pu-04](sources/pu-04.md): GitHub - PublicDotCom/publicdotcom-mcp-server · GitHub | Public | Public.com (GitHub) | official | 2026-11-12 |
| [pu-05](sources/pu-05.md): Public MCP: OAuth protected-resource metadata | Public | Public.com (endpoint metadata) | official | 2026-11-12 |
| [pu-06](sources/pu-06.md): How to Trade Stocks, Options & Crypto Using Claude | Public | Public.com | official | 2026-11-12 |
| [pu-07](sources/pu-07.md): public.com llms.txt | Public | Public.com | official | 2026-11-12 |
| [pu-08](sources/pu-08.md): Release 0.1.0 · PublicDotCom/publicdotcom-mcp-server · GitHub | Public | Public.com (GitHub) | official | 2026-11-12 |
| [pu-09](sources/pu-09.md): Claude & Claude Code Connector for Stock & Options Trading on Public MCP | Public | Public.com API docs | official | 2026-11-19 |
| [pu-10](sources/pu-10.md): Release v0.11.0 · PublicDotCom/publicdotcom-mcp-server | Public | Public.com (GitHub) | official | 2026-11-18 |
| [pu-11](sources/pu-11.md): Enforce preflight and user confirmation on every order — 0.11.0 (pull request 19) | Public | Public.com (GitHub) | official | 2026-11-18 |
| [pu-12](sources/pu-12.md): ChatGPT & Codex Connector for Stock & Options Trading on Public MCP | Public | Public.com API docs | official | 2026-11-19 |
| [pu-13](sources/pu-13.md): Grok Connector for Stock & Options Trading on Public MCP | Public | Public.com API docs | official | 2026-11-19 |
| [pu-14](sources/pu-14.md): Meta Muse Connector for Stock & Options Trading on Public MCP | Public | Public.com API docs | official | 2026-11-19 |
| [pu-15](sources/pu-15.md): Perplexity Connector for Stock & Options Trading on Public MCP | Public | Public.com API docs | official | 2026-11-19 |
| [pu-16](sources/pu-16.md): Guides (Public.com API docs index) | Public | Public.com API docs | official | 2026-11-19 |
| [rh-01](sources/rh-01.md): Onboarding an external agent \| Robinhood | Robinhood | Robinhood | official | 2026-11-19 |
| [rh-02](sources/rh-02.md): Robinhood MCP Server: What 73 Tools and an OAuth Handshake Look Like Up Close — DeskTested | Robinhood | DeskTested | third-party | 2026-11-12 |
| [rh-04](sources/rh-04.md): Trading with your agent \| Robinhood | Robinhood | Robinhood | official | 2026-11-19 |
| [rh-05](sources/rh-05.md): Robinhood Agents \| Build Your AI Trading Agent | Robinhood | Robinhood | official | 2026-11-12 |
| [rh-06](sources/rh-06.md): robinhood.com llms.txt | Robinhood | Robinhood | official | 2026-11-19 |
| [rh-07](sources/rh-07.md): Robinhood Agents overview \| Robinhood | Robinhood | Robinhood | official | 2026-11-12 |
| [rh-08](sources/rh-08.md): Setting up an agent \| Robinhood | Robinhood | Robinhood | official | 2026-11-12 |
| [rh-09](sources/rh-09.md): Agentic Credit Card \| Robinhood | Robinhood (Agentic Credit Card) | Robinhood | official | 2026-11-19 |
| [rh-10](sources/rh-10.md): Robinhood is Now Open to Agents | Robinhood | Robinhood | official | 2026-11-19 |
| [rh-11](sources/rh-11.md): Robinhood now lets your AI agents trade stocks \| TechCrunch | Robinhood | TechCrunch | third-party | 2026-11-12 |
| [rh-12](sources/rh-12.md): Agent apps \| Robinhood | Robinhood | Robinhood | official | 2026-11-12 |
| [rh-13](sources/rh-13.md): Robinhood Trading MCP: OAuth protected-resource metadata | Robinhood | Robinhood (endpoint metadata) | official | 2026-11-12 |
| [rn-01](sources/rn-01.md): Rain Agent Vaults bring embedded payments to AI agents | Rain Agent Vaults | Rain | official | 2026-11-15 |
| [rn-02](sources/rn-02.md): Rain Agent Vaults \| Embedded payments for AI agents | Rain Agent Vaults | Rain | official | 2026-11-15 |
| [rp-01](sources/rp-01.md): Replit Agent can now buy for your business and help you reach customers | Replit Agent with Link | Replit | official | 2026-11-20 |
| [sc-01](sources/sc-01.md): How do I connect to Scalable MCP? \| Scalable Capital Help Center | Scalable Capital | Scalable Capital Help Center | official | 2026-11-19 |
| [sc-02](sources/sc-02.md): What can my AI assistant do with the Scalable MCP? \| Scalable Capital Help Center | Scalable Capital | Scalable Capital Help Center | official | 2026-11-19 |
| [sc-03](sources/sc-03.md): How are orders approved and protected when using Scalable MCP? \| Scalable Capital Help Center | Scalable Capital | Scalable Capital Help Center | official | 2026-11-19 |
| [sd-01](sources/sd-01.md): Know Your Human (KYH): Fraud prevention for agentic commerce | Sardine Know Your Human | Sardine | official | 2026-11-20 |
| [sd-02](sources/sd-02.md): Know Your Human (KYH) for Agentic Commerce \| Sardine | Sardine Know Your Human | Sardine | official | 2026-11-20 |
| [so-01](sources/so-01.md): Solana Foundation Launches Pay.sh in Collaboration with Google Cloud | pay.sh | Solana Foundation | official | 2026-11-23 |
| [sp-01](sources/sp-01.md): Stripe helps Meta Muse shop with Link | Link wallet for agents | Stripe | official | 2026-11-18 |
| [sp-02](sources/sp-02.md): Giving agents the ability to pay (Stripe) | Link wallet for agents | Stripe | official | 2026-11-18 |
| [sp-03](sources/sp-03.md): Helping personal agents shop more intelligently and reliably with Link (Stripe) | Link wallet for agents | Stripe | official | 2026-11-18 |
| [sp-04](sources/sp-04.md): Ernie Tedeschi on X: "The agentic story on the eve of the 2026 holiday season" | Link wallet for agents | Ernie Tedeschi (@ernietedeschi on X), Stripe's chief economist, personal account | third-party | 2026-11-22 |
| [st-01](sources/st-01.md): 'Talk to transact': Starling customers can use their voice to send money | Starling Bank | Starling Bank | official | 2026-11-18 |
| [tc-01](sources/tc-01.md): More banks say customers using AI agents are on their own — even if they get hacked (TechCrunch) | Banks (Citi, JPMorgan, Bank of America, PNC, Citizens) | TechCrunch | third-party | 2026-11-20 |
| [tg-01](sources/tg-01.md): Terms & Conditions : Target | Target | Target | official | 2026-11-18 |
| [tt-01](sources/tt-01.md): GitHub - tastytrade/tastytrade-mcp: MCP server for the tastytrade open API: quotes, positions, balances, and dry-run-gated order flow for LLM agents.  | tastytrade | tastytrade (GitHub) | official | 2026-11-12 |
| [tt-02](sources/tt-02.md): Open API MCP Brings AI to Your tastytrade Account | tastytrade | tastytrade | official | 2026-11-12 |
| [tt-03](sources/tt-03.md): MCP Server · tastytrade Developer Docs | tastytrade | tastytrade Developer Docs | official | 2026-11-12 |
| [tt-04](sources/tt-04.md): OAuth2 authentication · tastytrade Developer Docs | tastytrade | tastytrade Developer Docs | official | 2026-11-12 |
| [ua-01](sources/ua-01.md): Contract of Carriage Document \| United Airlines | United Airlines | United Airlines | official | 2026-11-15 |
| [ua-02](sources/ua-02.md): Unauthorized third-party AI agents or assistants \| United Airlines | United Airlines | United Airlines | official | 2026-11-15 |
| [wb-01](sources/wb-01.md): Webull Agentic Trading — Let your AI agent trade the markets | Webull | Webull | official | 2026-11-19 |
| [wb-02](sources/wb-02.md): Webull Cloud MCP Server \| Webull API | Webull | Webull Developer | official | 2026-11-19 |
| [wb-03](sources/wb-03.md): GitHub - webull-inc/webull-openapi-mcp: Webull OpenAPI MCP · GitHub | Webull | Webull (GitHub) | official | 2026-11-19 |
| [wb-04](sources/wb-04.md): GitHub - webull-inc/webull-openapi-skills · GitHub | Webull | Webull (GitHub) | official | 2026-11-12 |
| [wb-05](sources/wb-05.md): GitHub - webull-inc/webull-openapi-cli · GitHub | Webull | Webull (GitHub) | official | 2026-11-12 |
| [wb-06](sources/wb-06.md): Webull Launches Model Context Protocol, Enabling Investors to Trade Through AI in Plain Language | Webull | PR Newswire | official | 2026-11-12 |
| [wb-07](sources/wb-07.md): Webull Expands Cloud MCP to Enable AI-Powered Trading Without Coding or Installation | Webull | Webull / PR Newswire | official | 2026-11-12 |
| [wb-08](sources/wb-08.md): Webull Launches ChatGPT, Claude & Grok Connectors, CLI, and Enhanced MCP to Expand AI-Powered Investing Tools | Webull | Webull / PR Newswire | official | 2026-11-19 |
| [wb-09](sources/wb-09.md): Webull API: OAuth protected-resource metadata | Webull | Webull (endpoint metadata) | official | 2026-11-12 |
| [wb-10](sources/wb-10.md): 「Webull MCP Server」および「Webull Agent Skills」の提供開始　日本株と米国株の取引ができる公式MCP Serverの提供は日本初（※） | Webull | Webull Securities Japan | official | 2026-11-12 |
| [wb-11](sources/wb-11.md): webull-openapi-mcp release 1.2.8 | Webull | Webull (GitHub) | official | 2026-11-23 |
| [xm-01](sources/xm-01.md): X Money plugin README (cursor/plugins, third_party/x-money) | X Money | cursor/plugins (GitHub) | official | 2026-11-18 |
| [xm-02](sources/xm-02.md): Cross River Powers X Money: The First P2P Payments Experience Built Into a U.S. Social Media Platform | X Money | Cross River Bank | third-party | 2026-11-18 |
| [xm-03](sources/xm-03.md): X Money overview (payments.x.com) | X Money | X Corp | official | 2026-11-18 |
| [xm-04](sources/xm-04.md): X Money Frequently Asked Questions | X Money | X Corp | official | 2026-11-18 |
| [xm-05](sources/xm-05.md): X Payments Money Transmitter Licenses | X Money | X Corp | official | 2026-11-18 |
| [xm-06](sources/xm-06.md): X Money Stored Value Account (CFPB prepaid account agreements database) | X Money | Consumer Financial Protection Bureau | third-party | 2026-11-18 |
| [xm-07](sources/xm-07.md): Weekly Banking Bulletin, July 24, 2026 (New York DFS) | X Money | New York State Department of Financial Services | third-party | 2026-11-18 |
| [xm-08](sources/xm-08.md): X Money on X: "𝕏 Money is rolling out to U.S. Premium and Premium+ subscribers starting today" | X Money | X Money (@XMoney on X) | official | 2026-11-18 |

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20index.md&body=Page%3A%20index.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
