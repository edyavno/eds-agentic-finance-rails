---
title: Directory
summary: Which brokers let AI agents trade and who approves each order, plus key fields for every listed broker, payment program and personal money tool. Every value is sourced or says unknown.
page_status: current
last_verified: '2026-11-14'
---

# Directory

## Which brokers let AI agents trade, and who approves the order?

*Checked Nov 14, 2026.*

All five launch brokers publish an official [MCP](glossary.md#mcp) server for AI agents.[^al-02][^cb-01][^ib-01][^rh-01][^wb-02] The brokers differ on who says yes before an order reaches the market.

- [Robinhood:](providers/robinhood.md) The agent trades only in a separate account you fund. Per-order approval is an optional toggle, off by default for MCP accounts.[^rh-01][^rh-04]
- [Coinbase:](providers/coinbase.md) The agent trades in the portfolios you pick when you sign in, which can include your main account. You can limit it to a dedicated portfolio.[^cb-03][^cb-07]
- [Webull:](providers/webull.md) With the hosted Cloud MCP, you confirm each trade in the Webull app. The local OpenAPI MCP places orders directly, with limits you set.[^wb-07][^wb-03]
- [Interactive Brokers:](providers/interactive-brokers.md) By default, the AI drafts instructions you review and submit. Eligible accounts can turn on Autonomous Trading inside a separately funded [AI Partition](glossary.md#ai-partition).[^ib-01][^ib-07][^ib-06]
- [Alpaca:](providers/alpaca.md) No broker-side approval is documented, so approval has to live in your agent or client.[^al-05][^al-03] [Paper trading](glossary.md#paper-trading) is built in.[^al-01][^al-03]

Who approves is explained in [approval models](approval-models/README.md). [Compare the launch brokers side by side](comparisons/launch-brokers.md), or see the [rails](rails/README.md) underneath.

## Broker fields

Key fields for every provider, generated from the YAML headers in `providers/`. Each value is sourced on the provider page; `unknown` means no source confirms it yet. Lists show the default path first. Machine-readable copies: [data/providers.json](data/providers.json), [data/providers.csv](data/providers.csv).

| Provider | Status | Can place orders | Approval model | Assets | Auth | Endpoint | Paper trading | Last verified | Page status | Unknown fields |
|---|---|---|---|---|---|---|---|---|---|---|
| [Alpaca](providers/alpaca.md) | official-mcp | yes | none | stocks; ETFs; fractional equities; options (including multi-leg); crypto | Hosted Trading MCP: OAuth sign-in with an Alpaca account (plugins for Cursor, Claude Code and Codex). Local Trading MCP and CLI: API key and secret in environment variables | `https://api.alpaca.markets/mcp` | yes | 2026-11-12 | current | 3 of 12 |
| [Coinbase](providers/coinbase.md) | official-mcp | yes | separate-account | crypto spot; US derivatives (futures); eligible US equities; x402 payments | OAuth via login.coinbase.com for the remote MCP; Dynamic Client Registration and Client ID Metadata Documents supported, but clients are allowlisted; the local CLI uses a CDP API key | `https://agents.coinbase.com/mcp` | unknown | 2026-11-14 | current | 4 of 12 |
| [Interactive Brokers](providers/interactive-brokers.md) | official-mcp | draft-only; yes | draft-then-submit; ai-partition | stocks; equity options | IBKR's own login and authorization flow; credentials are never shared with the AI app; revoke in Client Portal > Settings > Manage Third-Party Consents | `https://api.ibkr.com/v1/api/mcp-public` | unknown | 2026-11-12 | current | 3 of 12 |
| [Robinhood](providers/robinhood.md) | official-mcp | yes | separate-account; per-order-confirm | long equities; options (single-leg only); crypto (not in some states, including New York) | OAuth to the remote MCP server; protected-resource metadata lists the scope "internal"; an independent test reports PKCE and dynamic client registration | `https://agent.robinhood.com/mcp/trading` | unknown | 2026-11-14 | current | 2 of 12 |
| [Webull](providers/webull.md) | official-mcp | confirm-in-app; yes | per-order-confirm; none | stocks; options (single-leg and strategies); futures; crypto; event contracts | Cloud MCP: OAuth authorization code flow with a per-account Non-Trading or Trading capability. Local OpenAPI MCP: App Key and App Secret, with a 2FA flow | `https://api.webull.com/mcp` | yes | 2026-11-14 | current | 2 of 12 |


## Payments

How AI agents pay: card-network programs, payment tokens, commerce and payment protocols, and agent cards. Generated from the YAML headers in `payments/`; `unknown` means no source confirms it yet. Section home: [payments/](payments/README.md).

| Program | Operator | What an agent can do | What the person controls | Official MCP server | Availability | Last verified |
|---|---|---|---|---|---|---|
| [Agentic Commerce Protocol (ACP)](payments/agentic-commerce-protocol.md) | OpenAI and Stripe (spec maintainers) | Let a user find and buy from a business inside an AI app, through a checkout API and a delegated-payment spec | unknown | unknown | Beta. OpenAI and Stripe were the first to implement it | 2026-11-14 |
| [AP2 (Agent Payments Protocol)](payments/ap2.md) | Google (reference code on GitHub) | Carry signed proof of what the user authorized: a Checkout Mandate shared with the merchant and a Payment Mandate shared with the credential provider, the card networks and the payment processor | Open mandates hold the user's limits, such as budget and allowed payment methods, before a cart is final. Closed mandates authorize one finalized checkout and amount | unknown | Open protocol, available as an extension for A2A and Universal Commerce Protocol. Samples in Python, Go and Android | 2026-11-14 |
| [Mastercard Agent Pay](payments/mastercard-agent-pay.md) | Mastercard | Pay with agentic tokens once registered and verified, including through a merchant's normal card checkout form | Mastercard says each transaction is checked against authenticated user intent and explicit consent before the action | unknown | unknown | 2026-11-14 |
| [PayPal](payments/paypal.md) | PayPal | Use PayPal APIs for orders, invoices, subscriptions, shipment tracking, transaction details and disputes | Access uses the PayPal account's own credentials: an access token for the local server, or client ID and secret for the hosted one. A sandbox is available for testing | yes | Local server (Node.js 18 or later) or hosted server. Sandbox address https://mcp.sandbox.paypal.com | 2026-11-14 |
| [Robinhood Agentic Credit Card](payments/robinhood-agentic-credit-card.md) | Robinhood (Robinhood Credit, Inc.) | Fetch the agentic virtual card's number to finish purchases, and read that card's spending history and settings. The MCP does not browse or shop for you | Approve each purchase in the Robinhood Banking app, or set a monthly limit, which is required if you do not approve each purchase. The agent sees only the cards you authorize | yes | A virtual card in the Robinhood Gold Card. Card setup and agent sign-in work on desktop only. Announced 2026-05-27 | 2026-11-14 |
| [Stripe](payments/stripe.md) | Stripe | Grant a seller a shared payment token for a purchase. Separately, call the Stripe API and search Stripe's docs through the Stripe MCP server | Each token has usage and expiry limits, such as currency, maximum amount and an expiry window. MCP access is granted on Stripe's OAuth consent page and can be revoked | yes | Shared payment tokens are in public preview in the US, Canada and select European countries | 2026-11-14 |
| [Visa Intelligent Commerce](payments/visa-intelligent-commerce.md) | Visa | Buy things for a consumer with tokenized Visa credentials, under purchase instructions the consumer approved | Consumer-approved purchase instructions, Visa Payment Passkeys with device binding, and network-level controls | yes | Production needs Visa onboarding and approval at each stage: sandbox, certification, production. Intelligent Commerce Connect was in pilot with select partners as of 2026-04-08 | 2026-11-14 |
| [x402](payments/x402.md) | x402 Foundation | Pay for a web resource as part of the request: the server replies 402 Payment Required with its terms, and the client retries with a payment attached | unknown | unknown | Open standard. Specification version 2 is published | 2026-11-14 |


## Personal money agents

Personal AI agents that work with bank and card data, the developer tools behind them, and banks' own AI tools. Generated from the YAML headers in `personal-money/`; `unknown` means no source confirms it yet. Section home: [personal-money/](personal-money/README.md).

| Program | Operator | What an agent can do | What the person controls | Official MCP server | Availability | Last verified |
|---|---|---|---|---|---|---|
| [JPMorgan Smart Cash](personal-money/jpmorgan-smart-cash.md) | JPMorgan Chase | Predict a user's cash flow and move funds to maximize yield, as the bank's CFO described it (news report) | unknown | unknown | A targeted pilot that began in the weeks before 2026-10-13 (news report) | 2026-11-14 |
| [Meta Muse](personal-money/meta-muse.md) | Meta | Give personalized money guidance from accounts you connect through Plaid, such as balances, transactions, investment holdings and mortgage information | You choose whether to connect accounts, and you can manage Plaid-powered connections in Plaid Portal | unknown | Launched 2026-09-08 with Plaid-powered account connections in its finance features | 2026-11-14 |
| [Plaid MCP servers](personal-money/plaid.md) | Plaid | Developer work only: production diagnostics and analytics for a Plaid customer's team, and a local sandbox MCP for building. No access to end users' accounts | The Dashboard MCP needs a Plaid OAuth token, and the team must be approved for Production access | yes | The Dashboard MCP is under active development. Plaid says breaking changes may occur and support is limited | 2026-11-14 |


## Advisor agents

AI tools for financial advisors. These are not launch-broker pages, so they are not in the table above. This section is new and still thin. Section home: [advisors/](advisors/README.md).

| Tool | Summary | Last verified | Page status |
|---|---|---|---|
| [Advisor agents](advisors/README.md) | AI tools that help financial advisors work with client data and firm systems. This section is new and still thin. It currently covers Claude for Financial Advisors, Nitrogen, and Wells Fargo AI Teammate. | 2026-11-13 | current |
| [Claude for Financial Advisors](advisors/claude-for-financial-advisors.md) | Anthropic's advisor product, with official connectors into firm systems. Official pages say Claude does not place trades or move money, and they recommend Enterprise for RIAs. | 2026-11-13 | current |
| [Nitrogen](advisors/nitrogen.md) | Official Nitrogen agents page documents an MCP server and approval-required actions. A Fall 2026 announcement said the suite was brought into Claude and ChatGPT and Nucleus was expanded. | 2026-11-13 | current |
| [Wells Fargo AI Teammate](advisors/wells-fargo-ai-teammate.md) | Official July 15, 2026 launch of a chat-based AI capability embedded in Advisor Gateway for WIM advisors, including FiNet. Later interview figures are company-reported and are labeled as such. | 2026-11-13 | current |

Approval models are explained in [approval-models/](approval-models/README.md).
A page marked stale or archived should not be treated as current; check last_verified.

## Sources

[^al-02]: [GitHub - alpacahq/alpaca-mcp-server: Alpaca’s official MCP Server lets you trade stocks, ETFs, crypto, and options, run data analysis, and build strat](sources/al-02.md). Alpaca (GitHub), official, retrieved 2026-11-12.
[^cb-01]: [Coinbase MCP - Coinbase Developer Documentation](sources/cb-01.md). Coinbase Developer Platform, official, retrieved 2026-11-12.
[^ib-01]: [Interactive Brokers AI Hub](sources/ib-01.md). Interactive Brokers, official, retrieved 2026-11-12.
[^rh-01]: [Onboarding an external agent - Robinhood](sources/rh-01.md). Robinhood, official, retrieved 2026-11-12.
[^wb-02]: [Webull Cloud MCP Server - Webull API](sources/wb-02.md). Webull Developer, official, retrieved 2026-11-12.
[^rh-04]: [Trading with your agent - Robinhood](sources/rh-04.md). Robinhood, official, retrieved 2026-11-12.
[^cb-03]: [Coinbase for Agents setup skill (skill.md)](sources/cb-03.md). Coinbase Developer Platform, official, retrieved 2026-11-12.
[^cb-07]: [Coinbase for Agents: Your AI Agent Can Now Trade and Pay with Coinbase](sources/cb-07.md). Coinbase, official, retrieved 2026-11-12.
[^wb-07]: [Webull Expands Cloud MCP to Enable AI-Powered Trading Without Coding or Installation](sources/wb-07.md). Webull / PR Newswire, official, retrieved 2026-11-12.
[^wb-03]: [GitHub - webull-inc/webull-openapi-mcp: Webull OpenAPI MCP · GitHub](sources/wb-03.md). Webull (GitHub), official, retrieved 2026-11-12.
[^ib-07]: [AI Instructions](sources/ib-07.md). IBKR Guides, official, retrieved 2026-11-12.
[^ib-06]: [AI-Powered Portfolio Analysis & Trading Tools (IBKR AI Integrations)](sources/ib-06.md). Interactive Brokers, official, retrieved 2026-11-12.
[^al-05]: [GitHub - alpacahq/cli: CLI for Trading API · GitHub](sources/al-05.md). Alpaca (GitHub), official, retrieved 2026-11-12.
[^al-03]: [GitHub - alpacahq/agentic: Multi-platform plugin marketplace for Alpaca APIs · GitHub](sources/al-03.md). Alpaca (GitHub), official, retrieved 2026-11-12.
[^al-01]: [Alpaca - Trade with AI Using Alpaca's MCP Server](sources/al-01.md). Alpaca, official, retrieved 2026-11-12.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20directory.md&body=Page%3A%20directory.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
