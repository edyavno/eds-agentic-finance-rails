---
type: provider
id: webull
title: Webull
summary: Two official paths. The hosted Cloud MCP prepares trade instructions that you confirm in the Webull app; the local OpenAPI MCP places orders directly, with configurable risk limits and a sandbox default.
provider: Webull
page_status: current
last_verified: '2026-11-12'
status: official-mcp
can_place_orders: [confirm-in-app, 'yes']
approval_model: [per-order-confirm, none]
assets: [stocks, options (single-leg and strategies), futures, crypto, event contracts]
order_types: unknown
auth: "Cloud MCP: OAuth authorization code flow with a per-account Non-Trading or Trading capability. Local OpenAPI MCP: App Key and App Secret, with a 2FA flow"
endpoint: https://api.webull.com/mcp
transport: [remote-http, local-stdio, cli]
reads_portfolio: 'yes'
paper_trading: 'yes'
limits: "Local OpenAPI MCP only: per-market maximum order notional (default USD 10,000 for the US market), quantity limits and a symbol whitelist"
notifications: unknown
notes: can_place_orders and approval_model list the Cloud MCP first, then the local OpenAPI MCP. Paper trading refers to the local MCP's UAT sandbox; for Cloud MCP it is unknown.
field_sources:
  status: [wb-02, wb-03, wb-06]
  can_place_orders: [wb-02, wb-07, wb-03]
  approval_model: [wb-02, wb-07, wb-03]
  assets: [wb-02, wb-03]
  auth: [wb-02, wb-09, wb-03]
  endpoint: [wb-02]
  transport: [wb-02, wb-03, wb-05]
  reads_portfolio: [wb-02]
  paper_trading: [wb-03]
  limits: [wb-03]
---

# Webull

> Every fact below links to a source card; "unknown" means no source in the current batch confirms it.

## Overview and current status

Webull has two official agent paths:

1. **Cloud MCP**, hosted by Webull at `https://api.webull.com/mcp`. It prepares trade instructions, and each trade needs your separate confirmation in Webull before it goes to the market.[^wb-02][^wb-07]
2. **Local OpenAPI MCP**, an open-source server you run yourself with API credentials. It can place, modify and cancel orders directly.[^wb-03]

Webull announced its MCP server on 2026-06-11, saying it had been working with clients since April.[^wb-06] On 2026-09-29 it expanded Cloud MCP to trade preparation with no API keys, available to eligible US users through Claude, Perplexity and Grok, with ChatGPT pending.[^wb-07] A separate Japan launch was announced on 2026-05-13.[^wb-10]

## Feature matrix

| Feature | Cloud MCP | Local OpenAPI MCP | Sources |
|---|---|---|---|
| Read portfolio | Yes (account info, portfolio, watchlists) | Yes | [^wb-02][^wb-03] |
| Place orders | Instructions only, confirmed in the Webull app or desktop | Yes: place, modify, cancel | [^wb-02][^wb-03] |
| Assets | Stock, single-leg option, option strategy, futures, crypto, event and algo instructions | Stocks, options, futures, crypto, event contracts | [^wb-02][^wb-03] |
| Regions | US (eligible users) | US, HK, JP, SG, MY, UK, MX, BR, ZA, with region-specific features | [^wb-07][^wb-03] |
| Limits | unknown | Notional limits per market, quantity limits, symbol whitelist | [^wb-03] |
| Paper or sandbox | unknown | Defaults to the UAT sandbox | [^wb-03] |
| Notifications or audit trail | unknown | Audit log of all order operations | [^wb-03] |

## Implementation details

- **Cloud endpoint:** `https://api.webull.com/mcp` (a configuration URL, not a page to open).[^wb-02]
- **Cloud auth:** OAuth authorization code flow. Each account gets a Non-Trading capability (data and account info only) or a Trading capability (adds trade instructions).[^wb-02] The protected-resource metadata lists scopes `account:read`, `order:read`, `order:write`, `market:read`, `instrument:read` and `instruction:all`.[^wb-09]
- **Cloud order tools:** `place_stock_instruction`, `place_option_single_instruction`, `place_option_strategy_instruction`, `place_futures_instruction`, `place_crypto_instruction`, `place_event_instruction` and `place_algo_instruction`, each documented as needing confirmation in the Webull app or desktop.[^wb-02]
- **Local MCP:** runs with `uvx webull-openapi-mcp`, needs an App Key and App Secret, supports 2FA and defaults to the UAT sandbox until you set `WEBULL_ENVIRONMENT=prod`.[^wb-03]
- **CLI:** Webull also publishes an OpenAPI CLI, labelled an alpha preview.[^wb-05]

## Guardrails and risks

| Guardrail | Where it is enforced | Sources |
|---|---|---|
| Cloud: every trade needs separate confirmation in Webull | Server side (broker) | [^wb-07][^wb-02] |
| Cloud: Non-Trading capability blocks order instructions | Server side (broker) | [^wb-02] |
| Local: notional and quantity limits, symbol whitelist | In the local server you run (configurable) | [^wb-03] |
| Local: sandbox by default | In the local server you run | [^wb-03] |
| Local: no broker-side approval step documented | | [^wb-03] |

The local server's limits live in your own configuration, so anyone who can change its environment variables can change them.[^wb-03]

## How to build against it

- **Lowest risk:** connect Cloud MCP with the Non-Trading capability first, then switch the account to Trading when you want instructions you confirm in the app.[^wb-02]
- **Automation:** run the local OpenAPI MCP in UAT, set notional limits and a symbol whitelist, and only then move to `prod`.[^wb-03]

See [Connect an MCP client](../build/connect-an-mcp-client.md).

## Unknown so far

- Cloud MCP limits, notifications and paper mode: unknown.
- Exact order types per region: unknown.
- Agent terms of use: not yet in the source batch.

## Changelog

- 2026-11-12: Page drafted from source batch 1.

## Sources

[^wb-02]: [Webull Cloud MCP Server - Webull API](../sources/wb-02.md). Webull Developer, official, retrieved 2026-11-12.
[^wb-07]: [Webull Expands Cloud MCP to Enable AI-Powered Trading Without Coding or Installation](../sources/wb-07.md). Webull / PR Newswire, official, retrieved 2026-11-12.
[^wb-03]: [GitHub - webull-inc/webull-openapi-mcp: Webull OpenAPI MCP · GitHub](../sources/wb-03.md). Webull (GitHub), official, retrieved 2026-11-12.
[^wb-06]: [Webull Launches Model Context Protocol, Enabling Investors to Trade Through AI in Plain Language](../sources/wb-06.md). PR Newswire, official, retrieved 2026-11-12.
[^wb-10]: [「Webull MCP Server」および「Webull Agent Skills」の提供開始　日本株と米国株の取引ができる公式MCP Serverの提供は日本初（※）](../sources/wb-10.md). Webull Securities Japan, official, retrieved 2026-11-12.
[^wb-09]: [Webull API: OAuth protected-resource metadata](../sources/wb-09.md). Webull (endpoint metadata), official, retrieved 2026-11-12.
[^wb-05]: [GitHub - webull-inc/webull-openapi-cli · GitHub](../sources/wb-05.md). Webull (GitHub), official, retrieved 2026-11-12.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20providers%2Fwebull.md&body=Page%3A%20providers%2Fwebull.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
