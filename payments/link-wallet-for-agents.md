---
type: payment
id: link-wallet-for-agents
title: Link wallet for agents
summary: Stripe's Link wallet for agents lets a person approve each purchase an agent makes, with a one-time card or shared payment token. Muse, Grok Bot, Instinct and Claude Duet use Link or a wallet like it.
page_status: current
last_verified: '2026-11-22'
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
- **Replit Agent.** On 2026-11-12 Replit said its Agent can buy supplies for a business, such as shipping boxes, with Link and Visa.[^rp-01] See [Replit Agent](#how-does-replit-agent-buy-with-link) below.

## Does Link work with Chase cards?

A Wall Street Journal report of 2026-11-13, citing people familiar with the matter, says JPMorgan Chase has been blocking agents when consumers give the bots their card information. It says Stripe has a separate mechanism that can be used for Chase cards and other issuers: Stripe's wallet uses a one-time virtual card equal to the purchase amount, then charges the purchase amount to the consumer's actual card.[^bl-12] PYMNTS describes the same flow: the shopper sees one charge on the card they chose, and the merchant is paid by a different card.[^bl-13] Both are third-party reports. See [Banks and outside agents](../personal-money/banks-and-outside-agents.md#what-about-shopping-with-a-card).

- **Agentic tokens.** The report says Link also uses [agentic tokens](../glossary.md#agentic-token) from Visa and Mastercard, and that Chase has been slow to implement them.[^bl-12]
- **Cost to merchants.** Merchants are complaining to Visa and Mastercard that the virtual card costs them higher fees on average than the shopper's own card, because it is classified as a commercial card rather than a consumer card. Some merchant executives also say the temporary cards make returns harder to process.[^bl-12] See [Merchants and outside agents](merchants-and-outside-agents.md#what-do-merchants-say-about-agent-virtual-cards).

## How does Replit Agent buy with Link?

Replit says its Agent finds options and prepares the merchant's checkout, then waits for the business owner to approve the final total before anything is charged.[^rp-01]

- **Link's part.** Replit says Link lets the user choose a saved payment method and approve the final total while protecting their payment details, and that Link facilitates the transaction scoped to the approved purchase.[^rp-01]
- **The browser.** A browser subagent works on the merchant's site, prepares checkout and returns the purchase details to the Agent for approval. Replit says it uses a browser provided by Browserbase, so it does not need a separate integration with each store.[^rp-01]
- **Limits.** Replit says the browser session is isolated and the Agent stops at the checkout for approval. It says the Agent never gets open-ended permission to spend, shell access and general browsing are disabled during payment, and approval checks are enforced in code, not left to the model.[^rp-01]
- **Who can use it.** Replit says it is available for Core and Pro users, starting in the US and limited to one-time purchases.[^rp-01]
- **Visa.** Replit says Visa provides trusted payment infrastructure and capabilities designed to support secure agent-initiated transactions. See [Visa Intelligent Commerce](visa-intelligent-commerce.md).[^rp-01]

## What else did Stripe add?

- **Incremental authorization.** An agent can request a higher approved amount when the final price exceeds the original, for example when a checked bag is added to a flight.[^sp-03]
- **Payment guidance.** When a payment hits an obstacle, Link tells the agent how to proceed, such as a URL for the person to complete a 3D Secure challenge, or a prompt to choose another payment method.[^sp-03]
- **Purchase protections.** Eligible Link purchases made by an agent may carry free protections for damage, loss, price drops and returns. Stripe says Muse is the first agent to offer them.[^sp-03]
- **Financial insights.** With a consumer's permission, an agent can use Link's financial insights, which Stripe says come from its Financial Connections open banking product, to recommend purchases. Stripe says Financial Connections covers more than 12,000 institutions and that people can revoke access at any time.[^sp-03]

## How much are agents spending?

On 2026-11-20 Stripe's chief economist, writing on a personal X account rather than as an official Stripe release, shared figures for spend through Link Agent Wallet.[^sp-04]

| Field | Details |
|---|---|
| Growth | Daily spend was nearly 80-fold higher in mid-November than at the start of September, measured using a [seven-day rolling average](../glossary.md#seven-day-rolling-average). A callout on the attached chart reads "7,982% of Sep 1 level" (the chart's index is September 1 = 100, through November 19, 2026). |
| Last month | Spend doubled in the last month. The article does not give exact dates for that month. |
| Categories | The article says that last week, over 40% of Link agentic spending volume was on airfare, travel, and lodging, roughly a third on retail, and a quarter on other categories. The attached chart, for the last seven days through November 19, 2026, labels airfare, travel, and lodging 43%, retail 34%, life admin 7%, events and performances 4%, and other 11% (those shares add to 99%; the chart does not explain the remaining 1%). A retail inset for November 13–19, 2026 gives a split of retail dollars; those shares are on the [source card](../sources/sp-04.md). |
| Repeat purchases | The article says more than half of consumers who make one agentic purchase come back to make at least a second, typically in the same spending category. The attached chart labels that first repeat rate as 56%, among customers whose first agentic purchase was approved by October 15, with data through November 15, 2026. Among those who had made nine purchases, 78% made a tenth. |
| Who is included | The article says Link Agent Wallet powers payments for personal agents including Muse, Instinct, and Grok. The spend figures are for Link agent spend as a whole, not for any one app. |
| Unknown | Dollar amounts and user counts. |

## Unknown

- Whether Link's agent wallet has an official MCP server or a public endpoint for consumer agents. The cited posts describe a command-line tool and APIs but no MCP address.
- Which countries beyond the US can connect Link to agents.
- How much more the virtual card costs merchants, and which other issuers' cards depend on it. The cited reports give no figure.
- When spending limits that skip per-purchase approval will launch. Stripe gives no date.
- Replit Agent's price, which countries beyond the US it will reach, and whether Link's purchase protections apply to its purchases. The Replit post does not say.[^rp-01]

More on payments: [Payments](README.md).

## Sources

[^sp-02]: [Giving agents the ability to pay (Stripe)](../sources/sp-02.md). Stripe, official, retrieved 2026-11-18.
[^sp-01]: [Stripe helps Meta Muse shop with Link](../sources/sp-01.md). Stripe, official, retrieved 2026-11-18.
[^gb-05]: [Grok Bot changelog](../sources/gb-05.md). xAI, official, retrieved 2026-11-18.
[^cl-03]: [Claude Duet safety, privacy and security](../sources/cl-03.md). Anthropic, official, retrieved 2026-11-18.
[^rp-01]: [Replit Agent can now buy for your business and help you reach customers](../sources/rp-01.md). Replit, official, retrieved 2026-11-20.
[^bl-12]: [AI bots are using credit cards. Banks are racing to keep up. (The Wall Street Journal, via Mint)](../sources/bl-12.md). The Wall Street Journal (syndicated on Mint), third-party, retrieved 2026-11-19.
[^bl-13]: [JPMorgan Stops AI Agents From Using Customer Credit Cards (PYMNTS)](../sources/bl-13.md). PYMNTS, third-party, retrieved 2026-11-19.
[^sp-03]: [Helping personal agents shop more intelligently and reliably with Link (Stripe)](../sources/sp-03.md). Stripe, official, retrieved 2026-11-18.
[^sp-04]: [Ernie Tedeschi on X: "The agentic story on the eve of the 2026 holiday season"](../sources/sp-04.md). Ernie Tedeschi (@ernietedeschi on X), Stripe's chief economist, personal account, third-party, retrieved 2026-11-22.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20payments%2Flink-wallet-for-agents.md&body=Page%3A%20payments%2Flink-wallet-for-agents.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
