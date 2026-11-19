---
type: payment
id: link-wallet-for-agents
title: Link wallet for agents
summary: Stripe's Link wallet for agents lets a person approve each purchase an agent makes, with a one-time card or shared payment token. Muse, Grok Bot, Instinct and Claude Duet use Link or a wallet like it.
page_status: current
last_verified: '2026-11-18'
kind: payment-credential
operator: Stripe
agent_can: Create a spend request in a person's Link wallet to get a one-time-use card or a shared payment token for a purchase, scoped by amount, currency and merchant. Stripe says Link can also tell an agent how to continue, such as a 3D Secure link, and an agent can ask for a higher approved amount
user_controls: The person grants wallet access through OAuth and approves each spend request in Link on web, iOS or Android. They can track agent spending and manage connected agents in Link. Stripe plans spending limits and a way to let agents act without approving each purchase, with no date given
mcp_server: unknown
endpoint: unknown
availability: Stripe announced Link's wallet for agents on 2026-04-29. Its 2026-09-08 release says US consumers can connect Link to Muse, and its 2026-09-29 post says Muse is the first agent to offer Link purchase protections
field_sources:
  operator:
  - sp-02
  agent_can:
  - sp-02
  - sp-03
  user_controls:
  - sp-02
  - sp-03
  availability:
  - sp-01
  - sp-02
  - sp-03
---

# Link wallet for agents

Link is Stripe's consumer wallet. Its agent wallet lets an agent ask for a one-time card or a shared payment token for one purchase, and the person approves that request in Link first.[^sp-02]

## How does a purchase work?

1. The person grants an agent access to their Link wallet through a standard [OAuth](../glossary.md#oauth) flow.[^sp-02]
2. The agent creates a spend request with context on the purchase. Stripe says the credential can be scoped by amount, currency and merchant.[^sp-02]
3. The person gets a notification and approves the request in Link, on the web or in the iOS or Android app. Stripe says each request currently needs the person's review before the credential is shared with the agent.[^sp-02]
4. Link returns a one-time-use card, which is a [virtual card](../glossary.md#virtual-card), or a shared payment token to complete the purchase.[^sp-02] See [Stripe](stripe.md) for shared payment tokens.

Stripe says Link's wallet for agents is built on its Issuing primitives, and it offers Issuing for agents to businesses that want their own agent wallets and cards.[^sp-02]

## Which agents use it?

- **Meta Muse.** Stripe says Meta integrated Link's wallet for agents with Muse for US consumers. At more than 1 million businesses that accept Link, Muse can check out with the payment method saved in Link, and elsewhere Link issues a single-use virtual card scoped to the purchase. The person approves the total in the chat and Muse never sees the underlying payment details.[^sp-01] See [Meta Muse](../personal-money/meta-muse.md).
- **Grok Bot and Instinct.** Stripe says the Link agent wallet helps power payments for Grok Bot and Instinct.[^sp-01] Grok Bot's changelog says Link completes the payment after the person taps Allow on a purchase card.[^gb-05] See [Grok Bot](../personal-money/grok-bot.md) and [Instinct](../personal-money/instinct.md).
- **Claude Duet.** Anthropic says Duet pays with a one-time card from a wallet like Link from Stripe, limited to the merchant and amount, and the person approves in the Link app.[^cl-03] See [Claude Duet](../personal-money/claude-duet.md).

## What else did Stripe add?

- **Incremental authorization.** An agent can request a higher approved amount when the final price exceeds the original, for example when a checked bag is added to a flight.[^sp-03]
- **Payment guidance.** When a payment hits an obstacle, Link tells the agent how to proceed, such as a URL for the person to complete a 3D Secure challenge, or a prompt to choose another payment method.[^sp-03]
- **Purchase protections.** Eligible Link purchases made by an agent may carry free protections for damage, loss, price drops and returns. Stripe says Muse is the first agent to offer them.[^sp-03]
- **Financial insights.** With a consumer's permission, an agent can use Link's financial insights, which Stripe says come from its Financial Connections open banking product, to recommend purchases. Stripe says Financial Connections covers more than 12,000 institutions and that people can revoke access at any time.[^sp-03]

## Unknown

- Whether Link's agent wallet has an official MCP server or a public endpoint for consumer agents. The cited posts describe a command-line tool and APIs but no MCP address.
- Which countries beyond the US can connect Link to agents.
- When spending limits that skip per-purchase approval will launch. Stripe gives no date.

More on payments: [Payments](README.md).

## Sources

[^sp-02]: [Giving agents the ability to pay (Stripe)](../sources/sp-02.md). Stripe, official, retrieved 2026-11-18.
[^sp-01]: [Stripe helps Meta Muse shop with Link](../sources/sp-01.md). Stripe, official, retrieved 2026-11-18.
[^gb-05]: [Grok Bot changelog](../sources/gb-05.md). xAI, official, retrieved 2026-11-18.
[^cl-03]: [Claude Duet safety, privacy and security](../sources/cl-03.md). Anthropic, official, retrieved 2026-11-18.
[^sp-03]: [Helping personal agents shop more intelligently and reliably with Link (Stripe)](../sources/sp-03.md). Stripe, official, retrieved 2026-11-18.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20payments%2Flink-wallet-for-agents.md&body=Page%3A%20payments%2Flink-wallet-for-agents.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
