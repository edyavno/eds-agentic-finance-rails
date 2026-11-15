---
type: provider
id: interactive-brokers
title: Interactive Brokers
summary: Remote MCP connector. By default the AI drafts trade instructions you review and submit; eligible accounts can enable Autonomous Trading inside a separately funded AI Partition.
provider: Interactive Brokers (IBKR)
page_status: current
last_verified: '2026-11-12'
status: official-mcp
can_place_orders: [draft-only, 'yes']
approval_model: [draft-then-submit, ai-partition]
assets: [stocks, equity options]
order_types: unknown
auth: IBKR's own login and authorization flow; credentials are never shared with the AI app; revoke in Client Portal > Settings > Manage Third-Party Consents
endpoint: https://api.ibkr.com/v1/api/mcp-public
endpoint_note: The Claude connector directory lists https://api.ibkr.com/v1/api/mcp for IBKR's certified connector.
transport: [remote-http]
reads_portfolio: 'yes'
paper_trading: unknown
limits: "Autonomous Trading: funding limited to cash allocated to the AI Partition; funding, account and eligibility limits apply at launch (amounts not published in the sources)"
notes: can_place_orders and approval_model list the default AI Integration first, then Autonomous Trading. The exact asset list for Autonomous Trading is unclear; an independent review found IBKR's descriptions inconsistent.
field_sources:
  status: [ib-01, ib-08]
  can_place_orders: [ib-01, ib-07, ib-02, ib-06]
  approval_model: [ib-01, ib-07, ib-02, ib-06]
  assets: [ib-02]
  auth: [ib-08, ib-01]
  endpoint: [ib-08]
  transport: [ib-08]
  reads_portfolio: [ib-01]
  limits: [ib-06, ib-02]
notifications: unknown
---

# Interactive Brokers

> Every fact below links to a source card; "unknown" means no source in the current batch confirms it.

## Overview and current status

Interactive Brokers runs an [MCP](../glossary.md#mcp) server for AI platforms such as ChatGPT, Claude, Grok and Perplexity. With the default **AI Integration**, the AI generates trade instructions and you review and submit every order.[^ib-01] Instructions show up in an IBKR app such as Client Portal, where you confirm or reject them.[^ib-07]

On 2026-10-21 IBKR announced **Autonomous Trading**: eligible clients can let their connected AI submit supported orders without approving each one, inside a separately funded [AI Partition](../glossary.md#ai-partition).[^ib-02][^ib-06]

Since release 1.1.5 (2026-07-17), any MCP client can connect through a custom connector URL.[^ib-08]

## Feature matrix

| Feature | AI Integration (default) | Autonomous Trading | Sources |
|---|---|---|---|
| Read portfolio | Yes | Yes | [^ib-01] |
| Place orders | Draft only. You review and submit in an IBKR app | Yes, inside the AI Partition | [^ib-01][^ib-07][^ib-06] |
| Assets | unknown for instructions | Supported stock and equity-option orders (examples in the announcement) | [^ib-02] |
| Eligibility | IBKR account | Individual, non-margin accounts only, after a Review & Approve track record | [^ib-06] |
| Limits | | Funding limited to cash allocated to the partition; other limits apply, amounts not published | [^ib-06][^ib-02] |
| Paper or sandbox | unknown | unknown | |
| Notifications | unknown | unknown | |

## Implementation details

- **Endpoint:** `https://api.ibkr.com/v1/api/mcp-public` for custom connectors in any MCP client, including Claude Code and Cursor.[^ib-08] The Claude connector directory lists `https://api.ibkr.com/v1/api/mcp` and tools such as `get_order_instructions`, `get_account_positions` and `search_contracts`.[^ib-04]
- **Auth:** you sign in on IBKR's login screen; credentials are never shared with the AI app.[^ib-08][^ib-01]
- **Revoke:** Client Portal > Settings > Manage Third-Party Consents.[^ib-08]
- **Autonomous eligibility:** individual, non-margin accounts; joint, retirement, advisor-managed, organizational and Lite accounts are excluded. You first execute at least 10 trades over two weeks in Review & Approve mode.[^ib-06] An independent review quoted the requirement as 10 trades "of $100 or more each"; the IBKR page retrieved on 2026-11-12 does not show that amount.[^ib-03]
- **Entities:** an independent review reports IBKR's FAQ plans Autonomous Trading for IB LLC, Australia, Singapore and the UK.[^ib-03]

## Guardrails and risks

| Guardrail | Where it is enforced | Sources |
|---|---|---|
| AI Integration: every instruction is reviewed and confirmed by you in an IBKR app | Server side (broker) | [^ib-07][^ib-01] |
| Autonomous: trading only inside the funded AI Partition | Server side (broker) | [^ib-06] |
| Autonomous: eligibility gate (account type plus Review & Approve history) | Server side (broker) | [^ib-06] |
| Autonomous: funding, account and eligibility limits | Server side (broker), amounts unknown | [^ib-02] |
| Revoke access any time | Server side (broker) | [^ib-08][^ib-06] |

IBKR's AI Hub points to an Autonomous Trading Risk Disclosure that names the risk of agents placing unintended or erroneous orders.[^ib-01]

## How to build against it

1. Start with AI Integration: connect the custom connector and have the agent create instructions you review in Client Portal.[^ib-08][^ib-07]
2. Ask the agent to show account, side, quantity, order type, limit price, estimated value and available cash before creating an instruction, as IBKR's own example prompt does.[^ib-06]
3. Move to Autonomous Trading only if the account is eligible and you have funded a partition with what the agent may use.[^ib-06]

See [Connect an MCP client](../build/connect-an-mcp-client.md).

## Unknown so far

- Exact asset and order-type list for Autonomous Trading: unknown (IBKR's own descriptions vary).[^ib-03]
- AI Partition funding limits: stated only as "limits apply".[^ib-02]
- [Paper trading](../glossary.md#paper-trading) through MCP: unknown.
- The connection FAQ could not be captured (it needs JavaScript).

## Changelog

- 2026-11-12: First version of this page.

## Sources

[^ib-01]: [Interactive Brokers AI Hub](../sources/ib-01.md). Interactive Brokers, official, retrieved 2026-11-12.
[^ib-07]: [AI Instructions](../sources/ib-07.md). IBKR Guides, official, retrieved 2026-11-12.
[^ib-02]: [Interactive Brokers Introduces Autonomous Trading](../sources/ib-02.md). Interactive Brokers, official, retrieved 2026-11-12.
[^ib-06]: [AI-Powered Portfolio Analysis & Trading Tools (IBKR AI Integrations)](../sources/ib-06.md). Interactive Brokers, official, retrieved 2026-11-12.
[^ib-08]: [Version 1.1.5 - Custom Connector, Connect From Any MCP Client](../sources/ib-08.md). IBKR Guides, official, retrieved 2026-11-12.
[^ib-04]: [Interactive Brokers (IBKR) connector - Claude by Anthropic](../sources/ib-04.md). Anthropic (Claude connector directory), third-party, retrieved 2026-11-12.
[^ib-03]: [IBKR Autonomous Trading: What the AI Partition Lets an AI Trade Without Asking, Read Off IBKR's Pages — DeskTested](../sources/ib-03.md). DeskTested, third-party, retrieved 2026-11-12.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20providers%2Finteractive-brokers.md&body=Page%3A%20providers%2Finteractive-brokers.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
