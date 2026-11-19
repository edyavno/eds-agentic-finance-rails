---
type: provider
id: scalable-capital
title: Scalable Capital
summary: 'Scalable Capital runs an MCP server with four access levels you set in its web app. Buy and sell orders need Full access, and each order needs your fresh, explicit confirmation of a preview.'
provider: Scalable Capital
page_status: current
last_verified: '2026-11-19'
status: official-mcp
can_place_orders: ['yes']
approval_model: [per-order-confirm]
assets: unknown
order_types: unknown
auth: Browser sign-in to Scalable through the AI app, with two-factor authentication; the MCP access level is set in the web version under Profile > Security > Agentic Investing
endpoint: https://mcp.scalable.capital/mcp
transport: [remote-http]
reads_portfolio: 'yes'
paper_trading: unknown
limits: unknown
notifications: unknown
notes: One access level applies to every connected AI assistant and every portfolio. Orders need the Full access level. The Scalable CLI's access setting is managed separately. Personal Broker, Overnight and Fixed-Term accounts are supported; Junior accounts are not.
field_sources:
  status: [sc-01, sc-03]
  can_place_orders: [sc-02, sc-03]
  approval_model: [sc-02, sc-03]
  auth: [sc-01]
  endpoint: [sc-01]
  transport: [sc-01]
  reads_portfolio: [sc-02]
---

# Scalable Capital

## Can an AI agent trade at Scalable Capital?

Yes, at the Full access level, and only after you confirm each order. Scalable MCP connects a compatible AI app to selected Scalable services. Scalable says it is an additional way to access your account and does not replace the Scalable App or website.[^sc-01]

Buy and sell orders use a mandatory two-step process. Your AI assistant prepares an order preview with the order details, costs, disclosures and warnings, and you give a fresh, explicit confirmation in a separate step. An order preview does not place an order.[^sc-02][^sc-03]

Scalable MCP supports personal Broker, Overnight and Fixed-Term accounts. Junior accounts are not supported.[^sc-02]

## What can an AI agent do at Scalable Capital?

What the assistant can do depends on the access level you choose. There are four levels:[^sc-01][^sc-02]

| Access level | What a connected assistant can do | Sources |
|---|---|---|
| No access | Nothing. Scalable MCP cannot be used | [^sc-02] |
| Read-only | Retrieve supported information about your account, portfolios and markets. No changes and no orders | [^sc-02] |
| Limited changes | Also manage watchlists, price alerts and portfolio groups. No savings plan changes and no orders. One article calls this level "Limited access" | [^sc-01][^sc-02] |
| Full access | Everything Scalable MCP supports, including savings plan changes and supported buy and sell orders | [^sc-02][^sc-03] |

| Feature | Value | Sources |
|---|---|---|
| Read portfolio | Yes. Account profile, portfolios, holdings, cash and buying power, transactions, and Overnight and Fixed-Term accounts | [^sc-02] |
| Place orders | Yes, at Full access only, after your explicit confirmation of each order preview | [^sc-03] |
| Order types | unknown. The docs list preview and submit tools for buy and sell orders, not order types | [^sc-02] |
| Assets | unknown | |
| Limits (size, spend) | unknown | |
| Notifications | unknown | |
| Paper or sandbox | unknown | |

An AI app may restrict functions further under its own policies, so even at Full access it may show fewer functions than Scalable MCP supports. It cannot turn on functions your access level does not allow.[^sc-01][^sc-02]

## How does Scalable Capital's agent connection work?

- **Endpoint:** `https://mcp.scalable.capital/mcp`.[^sc-01]
- **Access level:** set in your Scalable account under Profile > Security > Agentic Investing. This setting is only in the web version, not the Scalable App, and the first MCP setup must also be done on the web.[^sc-01]
- **Sign-in:** you open the Scalable sign-in page through your AI app, sign in, complete [two-factor authentication](../glossary.md#2fa), and review and authorize the connection.[^sc-01]
- **One level for everything:** the access level applies to all AI assistants connected to Scalable MCP and to all portfolios available through it. You cannot set different levels per assistant or per portfolio.[^sc-01]
- **CLI:** Scalable also has a CLI. Its access setting is managed separately and is not affected by the MCP access level.[^sc-03]
- **Tools:** account and portfolio, portfolio groups, market data, watchlists, price alerts, savings plans (preview, then submit), orders (`preview_buy_order` and `submit_buy_order`, `preview_sell_order` and `submit_sell_order`, `cancel_order`) and a `ping` check. Tool availability can vary by account type, instrument, eligibility, configuration and rollout status.[^sc-02]

## What guardrails and risks apply at Scalable Capital?

| Guardrail | Where it is enforced | Sources |
|---|---|---|
| Four access levels, from No access to Full access | Server side (broker), set in the web version | [^sc-01][^sc-02] |
| One access level for all assistants and all portfolios | Server side (broker) | [^sc-01] |
| Buy and sell orders only at Full access | Server side (broker) | [^sc-03] |
| Order preview, then a fresh, explicit confirmation in a separate step | Scalable MCP (separate preview and submit tools). Scalable says an agent cannot place an order without your renewed, explicit confirmation | [^sc-02][^sc-03] |
| Savings plan changes also need a preview and a fresh, explicit confirmation | Scalable MCP | [^sc-02] |
| Scalable's standard checks (account permissions, order validation, market availability, and eligibility, appropriateness or suitability where applicable) | Server side (broker) | [^sc-03] |
| Two-factor authentication at sign-in. Do not approve 2FA requests you did not start, and never share your password or backup code in an AI chat | Server side (broker), plus documented advice | [^sc-01] |
| Switching every assistant off | Set the access level to No access; connected assistants then cannot retrieve information or make changes | [^sc-02] |
| Revoking one assistant's access | unknown | |

The docs do not say how your confirmation reaches Scalable, for example in the AI chat or in a Scalable app, so that is unknown.

Scalable says its MCP and CLI are only interfaces to outside AI apps, which work outside its control, and that AI-generated outputs or transactions are not investment advice from Scalable Capital.[^sc-01]

## How do I connect Scalable Capital from my AI app?

First set your access level in the web version (Profile > Security > Agentic Investing). Then add `https://mcp.scalable.capital/mcp` in your app, sign in to Scalable and complete two-factor authentication.[^sc-01]

| App | How to connect | Sources |
|---|---|---|
| ChatGPT | Turn on developer mode under Settings → Security and login (availability can depend on account and workspace policy). In ChatGPT Plugins, select the plus button, enter a name and description, choose Server URL under Connection, enter the server address, and create the connection | [^sc-01] |
| ChatGPT desktop app | Go to Settings > MCP servers, add a Streamable HTTP server, and enter the server address | [^sc-01] |
| Claude | Go to Customize > Connectors, select Add custom connector, and enter the server address | [^sc-01] |
| Google Gemini | Select Customize > Connectors > + Custom, enter the server address, click Next, review the permissions, check the confirmation box and click Connect | [^sc-01] |
| Grok | Open Grok Connectors, select Scalable Capital and follow the steps shown | [^sc-01] |
| Cursor | Open Customize > MCP in the sidebar and add the server address | [^sc-01] |
| Google Antigravity | In the Agent side panel, open MCP Servers > Manage MCP Servers > View raw config and enter the server address | [^sc-01] |
| Other apps | Scalable says its MCP works with supported AI assistants and compatible local agents, and support for more assistants may be added | [^sc-01] |

## What is still unknown about Scalable Capital?

- Assets and order types available through the MCP: unknown.
- Order size, spend or rate limits: unknown.
- Paper trading or a sandbox: unknown.
- How to revoke one assistant without changing the access level for all: unknown.
- Countries where the MCP is available: unknown.
- Agent terms of use: not yet reviewed here.

Every fact on this page links to a source card; "unknown" means no source we cite confirms it.

## What changed on this page?

- 2026-11-19: First version of this page.

## Sources

[^sc-01]: [How do I connect to Scalable MCP? - Scalable Capital Help Center](../sources/sc-01.md). Scalable Capital Help Center, official, retrieved 2026-11-19.
[^sc-02]: [What can my AI assistant do with the Scalable MCP? - Scalable Capital Help Center](../sources/sc-02.md). Scalable Capital Help Center, official, retrieved 2026-11-19.
[^sc-03]: [How are orders approved and protected when using Scalable MCP? - Scalable Capital Help Center](../sources/sc-03.md). Scalable Capital Help Center, official, retrieved 2026-11-19.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20providers%2Fscalable-capital.md&body=Page%3A%20providers%2Fscalable-capital.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
