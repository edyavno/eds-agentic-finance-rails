---
type: payment
id: visa-cli
title: Visa CLI
summary: 'A Visa Crypto Labs product: after a US Visa card check, an agent gets a signing key, is listed in the Visa Agent Directory, and can take paid tasks and pay HTTP 402 requests in OUSD within limits the owner set.'
page_status: current
last_verified: '2026-11-23'
kind: card-network-program
operator: Visa (Visa Crypto Labs)
agent_can: Take paid tasks with the reward paid to the owner's wallet, and pay per-request APIs that answer with HTTP 402, in OUSD on Tempo, within limits the owner set. Requests are signed so a server can check them.
user_controls: The owner passes a Visa card check and sets limits on what the agent can pay. One card and one person can connect up to 25 agents, which can share a wallet.
mcp_server: 'yes'
endpoint: https://auth.visacli.sh
availability: Access is by invitation. The card check takes US Visa cards; prepaid, corporate and JPMorgan Chase cards cannot be added yet. New agents have been listed in the Visa Agent Directory since 2026-11-18.
notes: 'The documented host is the API, the registry and the hosted MCP server; the exact MCP path is unknown. Invitation terms, fees and default spend limits are unknown. Whether live HTTP 402 payments use the x402 protocol is unknown; the status docs tell merchants to test payment handling with an MPP server.'
field_sources:
  operator:
  - pm-28
  agent_can:
  - pm-27
  user_controls:
  - pm-27
  - pm-28
  mcp_server:
  - pm-28
  endpoint:
  - pm-28
  availability:
  - pm-27
  - pm-28
---

# Visa CLI

Visa CLI, built by Visa Crypto Labs, gives an AI agent a signing key once its owner passes a US Visa card check. The agent's requests are signed under the [Trusted Agent Protocol](../glossary.md#trusted-agent-protocol-tap), and new agents are listed in the [Visa Agent Directory](../glossary.md#visa-agent-directory). A connected agent can take paid tasks and pay per-request APIs in [OUSD](../glossary.md#ousd), within the limits the owner set.[^pm-27][^pm-28]

This is a Visa product. It is not the same program as [Visa Intelligent Commerce](visa-intelligent-commerce.md), which covers tokenized Visa credentials for approved agent builders.

## How it works

- After the card check, the agent gets a signing key. A check shows that a person is behind the agent and that the agent was verified with a US Visa card, without saying who the person is. Reputation builds from there.[^pm-27]
- Requests are signed so any server can check them with a public lookup and no account. Visa CLI uses TAP, an open standard. For platform onboarding and checkout, Visa's published TAP specification is the reference.[^pm-27]
- Since 18 November 2026, a newly connected agent's key is registered in the Visa Agent Directory at `https://agenticdirectory.visa.com`. Agents connected before then remain in the directory sandbox. Visa CLI's registry at `https://auth.visacli.sh` lists agents and says whether each key is in the production directory or the sandbox. That host is also the API and the hosted MCP server; the exact MCP path is unknown.[^pm-28]
- A connected agent can find paid tasks, do the work, and have the reward paid to its owner's wallet. It can also pay APIs that charge per request. Those APIs answer with HTTP 402, and the agent pays in OUSD, a dollar [stablecoin](../glossary.md#stablecoin), on [Tempo](../glossary.md#tempo), from that wallet and within the limits the owner set. Every paid request carries the agent's signature; without it the payment is refused.[^pm-27]
- The docs describe the card step, wallet money on Tempo mainnet, task payouts, signatures, and new agents' TAP listings as real today.[^pm-28]

## What you control

- The owner passes the card check. Visa CLI takes US Visa cards. Prepaid, corporate and JPMorgan Chase cards cannot be added yet. That limit is Visa CLI's, not TAP's.[^pm-27]
- The current rule is one card, one person, and up to 25 agents, with many agents on the same wallet.[^pm-28]
- Payments stay within the limits the owner set. The docs have a "Limits and approvals" page on what the agent can do alone and what asks the owner first; this wiki has not yet recorded those default limits, so they are unknown.[^pm-27]

## Availability

Access is by invitation. The docs say to ask a Visa CLI partner contact.[^pm-28] Invitation terms and fees are unknown.

## Related

- [Visa Intelligent Commerce](visa-intelligent-commerce.md).
- [Agent identity](../rails/agent-identity.md), including TAP and the Visa Agent Directory.
- [Agent payments](../rails/agent-payments.md) and [x402](x402.md), for HTTP 402 payments. Whether Visa CLI's live 402 path uses the x402 protocol is unknown; the status docs tell merchants to test payment handling with an [MPP](../glossary.md#mpp) server.[^pm-28]
- All programs: [Payments](README.md).

## Unknown

Invitation terms, fees, default spend limits, the exact MCP path, and whether live HTTP 402 payments use the x402 protocol. No cited source confirms them, so the wiki says unknown.

## Sources

[^pm-27]: [Visa CLI docs: Introduction](../sources/pm-27.md). Visa CLI docs (Visa Crypto Labs), official, retrieved 2026-11-23.
[^pm-28]: [Visa CLI docs: What's live today](../sources/pm-28.md). Visa CLI docs (Visa Crypto Labs), official, retrieved 2026-11-23.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20payments%2Fvisa-cli.md&body=Page%3A%20payments%2Fvisa-cli.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
