---
type: payment
id: lightspark-agent-accounts
title: Lightspark Agent Accounts
summary: Lightspark accounts where an AI agent holds, spends, sends and receives money within limits and approvals the account holder sets. It pays Visa merchants with a card valid for one purchase. Sold to companies that build agents.
page_status: current
last_verified: '2026-11-20'
kind: agent-card
operator: Lightspark Group, Inc.
agent_can: Hold, spend, send and receive money for a person or business, pay a merchant that accepts Visa with a card valid for that purchase alone or a saved card seen only as a card ID, and settle directly with a merchant that has an Agent Account
user_controls: The account holder sets spending limits and decides which payments need their approval. The customer authorizes a delegated key once and can pause the agent, revoke the key or delete the agent at any time
mcp_server: unknown
endpoint: unknown
availability: Launched 2026-11-17 for companies building agents for consumers, small businesses and merchants. The Agents API must be enabled for each platform
field_sources:
  operator:
  - ls-01
  agent_can:
  - ls-01
  - ls-02
  user_controls:
  - ls-01
  - ls-02
  availability:
  - ls-01
  - ls-02
---

# Lightspark Agent Accounts

Lightspark launched Agent Accounts on 2026-11-17. It lets AI agents hold, spend, send and receive money on behalf of a person or business. Lightspark says agent platforms, marketplaces and fintechs can offer the accounts under their own brands.[^ls-01]

## How it works

- **Limits and approvals.** Lightspark says account holders set spending limits and decide which payments need their approval.[^ls-01]
- **Paying merchants.** Lightspark says a purchase by an agent at a merchant that accepts Visa comes through as a standard card transaction. When a consumer pays from their account balance, the agent uses a Visa card valid for that purchase alone.[^ls-01]
- **Saved cards.** Consumers can also pay with a saved card. Lightspark says the card number stays in a secure vault and the agent sees only a card ID.[^ls-01]
- **Between agents.** Merchants with an Agent Account can receive funds directly in their preferred currency and withdraw them to their bank.[^ls-01]
- **Businesses.** Lightspark says a business owner can authorize an agent to pay a US supplier over ACH and a contractor in Brazil through Pix, then review a record of both. It says Lightspark connects the account to banks and local payment networks in 65 countries.[^ls-01]
- **Balances and funding.** Lightspark says business owners can keep balances in dollars, euros, other local currencies or stablecoins, and that funding options include bank transfers, cards, stablecoins and bitcoin.[^ls-01]

## What does the documentation add?

- Lightspark's docs say every money movement an agent asks for becomes an agent action. Lightspark's Grid platform either runs it at once or holds it as pending approval until the platform approves or rejects it.[^ls-02]
- The docs say Grid checks every agent action against the policy the customer set, and either runs it, refuses it or holds it for the customer to approve. The customer keeps ownership of the account.[^ls-02]
- A spending pool is a limit several of a customer's agents share, on top of each agent's own policy. The docs say a pool holds no money.[^ls-02]
- The docs say an agent's sends and purchase cards are paid from the customer's Global Account, a self-custodial embedded wallet. Instead of signing every send, the customer authorizes a delegated key once for that agent and wallet. Grid signs only the sends the policy and the customer's approvals allow, and the customer can pause the agent, revoke the key or delete the agent at any time.[^ls-02]
- The docs say Grid does not run the agent. It provides the agent's credentials, policy checks, approvals and the audit trail.[^ls-02]

## How do companies offer it?

Lightspark's docs describe two routes. An AI company can list Lightspark as a connector in its app, where users sign up, verify and approve payments with Lightspark and the assistant calls Lightspark over [MCP](../glossary.md#mcp). Or a platform on Lightspark's Grid can add agents to its own product.[^ls-02] The docs say the Agents API must be enabled for a platform, and until it is, agent endpoints answer 403.[^ls-02]

## What is still unknown?

- Pricing. Lightspark says only that platforms can earn revenue when agents hold and move money.[^ls-01]
- Which countries consumers can use it in. The 65 countries are where Lightspark connects to banks and local networks.[^ls-01]
- The address of the MCP connector, and whether it is a public server for individuals. The docs describe it for AI companies to list.[^ls-02]

## How does it compare with other agent accounts?

[Rain Agent Vaults](rain-agent-vaults.md) and [AgentBank](agentbank.md) are also accounts or vaults an agent can spend from. Each is described on its own page from its own sources.

[Back to payments](README.md)

## Sources

[^ls-01]: [Lightspark Launches Agent Accounts for AI Agents to Make and Receive Payments](../sources/ls-01.md). Lightspark (via GlobeNewswire), official, retrieved 2026-11-20.
[^ls-02]: [Agent Accounts (Lightspark documentation)](../sources/ls-02.md). Lightspark (documentation), official, retrieved 2026-11-20.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20payments%2Flightspark-agent-accounts.md&body=Page%3A%20payments%2Flightspark-agent-accounts.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
