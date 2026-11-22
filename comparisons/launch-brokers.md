---
type: comparison
title: "Launch brokers compared: approval and safety posture"
summary: Side-by-side view of how the five launch brokers let agents trade, who approves orders, and where the guardrails are enforced.
page_status: current
last_verified: '2026-11-18'
---

# Launch brokers compared

The five launch brokers differ most on who approves an agent's order and whether the broker or your own client enforces that guardrail. A [cheatsheet of who says yes and who enforces it](../approval-models/README.md#who-says-yes-and-who-enforces-it) places the same five brokers on those two axes. The tables below compare approval, read access and paper trading; every field is on the [Trading](../directory.md) page.

## Who approves the order?

| Provider | Default path | Optional or second path | Guardrail enforced by | Sources |
|---|---|---|---|---|
| [Robinhood](../providers/robinhood.md) | Agent trades in a separate agentic account; Trade approvals off by default for MCP accounts | Turn on Trade approvals to confirm each order | Broker | [^rh-01][^rh-04] |
| [Coinbase](../providers/coinbase.md) | Agent trades in the portfolios you pick at sign-in, which can include the main account | Dedicated portfolio (spot crypto only); Coinbase-enforced limits on trade size, 24-hour volume and loss (auto-stop) | Broker for portfolio scope and limits; per-order approval depends on the client, and the official ChatGPT plugin shows Coinbase confirmation cards | [^cb-03][^cb-07][^cb-01][^cb-10][^cb-09] |
| [Webull](../providers/webull.md) | Cloud MCP: you confirm each trade in the Webull app | Local OpenAPI MCP: direct orders with local limits | Broker (Cloud); your server (local) | [^wb-07][^wb-03] |
| [Interactive Brokers](../providers/interactive-brokers.md) | AI Integration: you review and submit every instruction | Autonomous Trading in a funded AI Partition, for eligible accounts | Broker | [^ib-01][^ib-07][^ib-06] |
| [Alpaca](../providers/alpaca.md) | No broker-side approval documented | Paper endpoint for testing | Your client | [^al-05][^al-03] |

## What can the agent see?

| Provider | Read scope | Sources |
|---|---|---|
| Robinhood | All Robinhood accounts, positions, balances and order history | [^rh-01] |
| Coinbase | Portfolios selected on the approval screen | [^cb-03] |
| Webull | Account info, portfolio and watchlists (Cloud) | [^wb-02] |
| Interactive Brokers | Portfolio analysis and account data through the connector | [^ib-01] |
| Alpaca | Account, orders, positions, portfolio and market data | [^al-03] |

## Paper or sandbox

| Provider | Paper or sandbox for agents | Sources |
|---|---|---|
| Robinhood | unknown | |
| Coinbase | unknown | |
| Webull | Local OpenAPI MCP defaults to the UAT sandbox; Cloud unknown | [^wb-03] |
| Interactive Brokers | unknown | |
| Alpaca | Yes: paper endpoint and $100K simulated balance | [^al-01][^al-03] |

## Sources

[^rh-01]: [Onboarding an external agent - Robinhood](../sources/rh-01.md). Robinhood, official, retrieved 2026-11-19.
[^rh-04]: [Trading with your agent - Robinhood](../sources/rh-04.md). Robinhood, official, retrieved 2026-11-19.
[^cb-03]: [Coinbase for Agents setup skill (skill.md)](../sources/cb-03.md). Coinbase Developer Platform, official, retrieved 2026-11-12.
[^cb-07]: [Coinbase for Agents: Your AI Agent Can Now Trade and Pay with Coinbase](../sources/cb-07.md). Coinbase, official, retrieved 2026-11-12.
[^cb-01]: [Coinbase MCP - Coinbase Developer Documentation](../sources/cb-01.md). Coinbase Developer Platform, official, retrieved 2026-11-12.
[^cb-10]: [Coinbase for Agents introduces new Agent Controls](../sources/cb-10.md). Coinbase, official, retrieved 2026-11-18.
[^cb-09]: [Coinbase MCP - Coinbase Developer Documentation](../sources/cb-09.md). Coinbase Developer Platform, official, retrieved 2026-11-19.
[^wb-07]: [Webull Expands Cloud MCP to Enable AI-Powered Trading Without Coding or Installation](../sources/wb-07.md). Webull / PR Newswire, official, retrieved 2026-11-12.
[^wb-03]: [GitHub - webull-inc/webull-openapi-mcp: Webull OpenAPI MCP · GitHub](../sources/wb-03.md). Webull (GitHub), official, retrieved 2026-11-19.
[^ib-01]: [Interactive Brokers AI Hub](../sources/ib-01.md). Interactive Brokers, official, retrieved 2026-11-12.
[^ib-07]: [AI Instructions](../sources/ib-07.md). IBKR Guides, official, retrieved 2026-11-12.
[^ib-06]: [AI-Powered Portfolio Analysis & Trading Tools (IBKR AI Integrations)](../sources/ib-06.md). Interactive Brokers, official, retrieved 2026-11-12.
[^al-05]: [GitHub - alpacahq/cli: CLI for Trading API · GitHub](../sources/al-05.md). Alpaca (GitHub), official, retrieved 2026-11-12.
[^al-03]: [GitHub - alpacahq/agentic: Multi-platform plugin marketplace for Alpaca APIs · GitHub](../sources/al-03.md). Alpaca (GitHub), official, retrieved 2026-11-19.
[^wb-02]: [Webull Cloud MCP Server - Webull API](../sources/wb-02.md). Webull Developer, official, retrieved 2026-11-19.
[^al-01]: [Alpaca - Trade with AI Using Alpaca's MCP Server](../sources/al-01.md). Alpaca, official, retrieved 2026-11-19.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20comparisons%2Flaunch-brokers.md&body=Page%3A%20comparisons%2Flaunch-brokers.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
