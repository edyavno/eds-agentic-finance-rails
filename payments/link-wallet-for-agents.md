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


<figure class="afr-cheatsheet-visual afr-cheatsheet-visual--desktop">
<svg role="img" viewBox="0 0 800 230" xmlns="http://www.w3.org/2000/svg" aria-labelledby="link-flow-d-title link-flow-d-desc">
  <title id="link-flow-d-title">How a Link purchase works</title>
  <desc id="link-flow-d-desc">Four steps. One: the person grants an agent access to their Link wallet. Two: the agent creates a spend request that can be scoped by amount, currency and merchant. Three: the person approves the request in Link. Four: Link returns a one-time-use card or a shared payment token to complete the purchase.</desc>
  <rect width="800" height="230" fill="var(--light)"/>
  <defs>
    <marker id="link-flow-d-arrow" markerWidth="9" markerHeight="9" refX="7" refY="4.5" orient="auto">
      <path d="M0,0 L9,4.5 L0,9 z" fill="var(--tertiary)"/>
    </marker>
  </defs>
<rect x="16" y="36" width="168" height="150" rx="12" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.5"/>
<circle cx="38" cy="58" r="12" fill="var(--light)" stroke="var(--dark)" stroke-width="1.75"/>
<text x="38" y="62" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan x="38" y="62">1</tspan></text>
<text x="58" y="62" text-anchor="start" fill="var(--darkgray)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan>Person</tspan></text>
<text x="100.0" y="90" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="100.0" y="90">Grants the agent</tspan>
<tspan x="100.0" dy="16">access to their</tspan>
<tspan x="100.0" dy="16">Link wallet</tspan>
  </text>
<rect x="216" y="36" width="168" height="150" rx="12" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.5"/>
<circle cx="238" cy="58" r="12" fill="var(--light)" stroke="var(--dark)" stroke-width="1.75"/>
<text x="238" y="62" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan x="238" y="62">2</tspan></text>
<text x="258" y="62" text-anchor="start" fill="var(--darkgray)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan>Agent</tspan></text>
<text x="300.0" y="90" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="300.0" y="90">Creates a spend</tspan>
<tspan x="300.0" dy="16">request, scoped by</tspan>
<tspan x="300.0" dy="16">amount, currency</tspan>
<tspan x="300.0" dy="16">and merchant</tspan>
  </text>
<rect x="416" y="36" width="168" height="150" rx="12" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.5"/>
<circle cx="438" cy="58" r="12" fill="var(--light)" stroke="var(--dark)" stroke-width="1.75"/>
<text x="438" y="62" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan x="438" y="62">3</tspan></text>
<text x="458" y="62" text-anchor="start" fill="var(--darkgray)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan>Link</tspan></text>
<text x="500.0" y="90" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="500.0" y="90">The person</tspan>
<tspan x="500.0" dy="16">approves the</tspan>
<tspan x="500.0" dy="16">request in Link</tspan>
  </text>
<rect x="616" y="36" width="168" height="150" rx="12" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.5"/>
<circle cx="638" cy="58" r="12" fill="var(--light)" stroke="var(--dark)" stroke-width="1.75"/>
<text x="638" y="62" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan x="638" y="62">4</tspan></text>
<text x="658" y="62" text-anchor="start" fill="var(--darkgray)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan>Merchant</tspan></text>
<text x="700.0" y="90" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="700.0" y="90">A one-time-use card</tspan>
<tspan x="700.0" dy="16">or shared payment</tspan>
<tspan x="700.0" dy="16">token completes</tspan>
<tspan x="700.0" dy="16">the purchase</tspan>
  </text>
  <path d="M188,111.0 L210,111.0" fill="none" stroke="var(--tertiary)" stroke-width="2.25" marker-end="url(#link-flow-d-arrow)"/>
  <path d="M388,111.0 L410,111.0" fill="none" stroke="var(--tertiary)" stroke-width="2.25" marker-end="url(#link-flow-d-arrow)"/>
  <path d="M588,111.0 L610,111.0" fill="none" stroke="var(--tertiary)" stroke-width="2.25" marker-end="url(#link-flow-d-arrow)"/>
</svg>
<figcaption>The agent creates a spend request that can be scoped by amount, currency and merchant. The person approves the request in Link. Link returns a one-time-use card or a shared payment token to complete the purchase.</figcaption>
</figure>

<figure class="afr-cheatsheet-visual afr-cheatsheet-visual--mobile">
<svg role="img" viewBox="0 0 360 558" xmlns="http://www.w3.org/2000/svg" aria-labelledby="link-flow-m-title link-flow-m-desc">
  <title id="link-flow-m-title">How a Link purchase works</title>
  <desc id="link-flow-m-desc">Four steps. One: the person grants an agent access to their Link wallet. Two: the agent creates a spend request that can be scoped by amount, currency and merchant. Three: the person approves the request in Link. Four: Link returns a one-time-use card or a shared payment token to complete the purchase.</desc>
  <rect width="360" height="558" fill="var(--light)"/>
  <defs>
    <marker id="link-flow-m-arrow" markerWidth="9" markerHeight="9" refX="7" refY="4.5" orient="auto">
      <path d="M0,0 L9,4.5 L0,9 z" fill="var(--tertiary)"/>
    </marker>
  </defs>
<rect x="16" y="16" width="328" height="112" rx="12" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.5"/>
<circle cx="38" cy="38" r="12" fill="var(--light)" stroke="var(--dark)" stroke-width="1.75"/>
<text x="38" y="42" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan x="38" y="42">1</tspan></text>
<text x="58" y="42" text-anchor="start" fill="var(--darkgray)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan>Person</tspan></text>
<text x="180.0" y="68" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="180.0" y="68">Grants the agent access to</tspan>
<tspan x="180.0" dy="16">their Link wallet</tspan>
  </text>
<rect x="16" y="154" width="328" height="112" rx="12" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.5"/>
<circle cx="38" cy="176" r="12" fill="var(--light)" stroke="var(--dark)" stroke-width="1.75"/>
<text x="38" y="180" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan x="38" y="180">2</tspan></text>
<text x="58" y="180" text-anchor="start" fill="var(--darkgray)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan>Agent</tspan></text>
<text x="180.0" y="206" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="180.0" y="206">Creates a spend request, scoped</tspan>
<tspan x="180.0" dy="16">by amount, currency and merchant</tspan>
  </text>
<rect x="16" y="292" width="328" height="112" rx="12" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.5"/>
<circle cx="38" cy="314" r="12" fill="var(--light)" stroke="var(--dark)" stroke-width="1.75"/>
<text x="38" y="318" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan x="38" y="318">3</tspan></text>
<text x="58" y="318" text-anchor="start" fill="var(--darkgray)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan>Link</tspan></text>
<text x="180.0" y="344" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="180.0" y="344">The person approves the</tspan>
<tspan x="180.0" dy="16">request in Link</tspan>
  </text>
<rect x="16" y="430" width="328" height="112" rx="12" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.5"/>
<circle cx="38" cy="452" r="12" fill="var(--light)" stroke="var(--dark)" stroke-width="1.75"/>
<text x="38" y="456" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan x="38" y="456">4</tspan></text>
<text x="58" y="456" text-anchor="start" fill="var(--darkgray)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan>Merchant</tspan></text>
<text x="180.0" y="482" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="180.0" y="482">A one-time-use card or shared</tspan>
<tspan x="180.0" dy="16">payment token completes the purchase</tspan>
  </text>
  <path d="M180,132 L180,148" fill="none" stroke="var(--tertiary)" stroke-width="2.25" marker-end="url(#link-flow-m-arrow)"/>
  <path d="M180,270 L180,286" fill="none" stroke="var(--tertiary)" stroke-width="2.25" marker-end="url(#link-flow-m-arrow)"/>
  <path d="M180,408 L180,424" fill="none" stroke="var(--tertiary)" stroke-width="2.25" marker-end="url(#link-flow-m-arrow)"/>
</svg>
<figcaption>The agent creates a spend request that can be scoped by amount, currency and merchant. The person approves the request in Link. Link returns a one-time-use card or a shared payment token to complete the purchase.</figcaption>
</figure>

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

The attached chart's category split, for the last seven days through November 19, 2026:[^sp-04]

<figure class="afr-cheatsheet-visual afr-cheatsheet-visual--desktop">
<svg role="img" viewBox="0 0 800 250" xmlns="http://www.w3.org/2000/svg" aria-labelledby="link-cat-d-title link-cat-d-desc">
  <title id="link-cat-d-title">Link agentic spending by category</title>
  <desc id="link-cat-d-desc">A split bar of Link agentic spending for the last seven days through November 19, 2026. Airfare, travel, and lodging 43 percent, retail 34 percent, life admin 7 percent, events and performances 4 percent, and other 11 percent. The labeled shares add to 99 percent; the chart does not explain the remaining 1 percent.</desc>
  <rect width="800" height="250" fill="var(--light)"/>
  <defs>
    <clipPath id="link-cat-d-clip">
      <rect x="24" y="28" width="752" height="40" rx="8"/>
    </clipPath>
  </defs>
  <g clip-path="url(#link-cat-d-clip)">
    <rect x="24" y="28" width="323.36" height="40" fill="var(--secondary)"/>
    <rect x="347.36" y="28" width="255.68" height="40" fill="var(--tertiary)"/>
    <rect x="603.04" y="28" width="52.64" height="40" fill="color-mix(in srgb, var(--secondary) 50%, var(--light))"/>
    <rect x="655.68" y="28" width="30.08" height="40" fill="color-mix(in srgb, var(--tertiary) 50%, var(--light))"/>
    <rect x="685.76" y="28" width="82.72" height="40" fill="var(--darkgray)"/>
  </g>
  <rect x="24" y="28" width="752" height="40" rx="8" fill="none" stroke="var(--lightgray)" stroke-width="1.5"/>
  <rect x="24" y="92" width="16" height="16" rx="3" fill="var(--secondary)" stroke="var(--lightgray)" stroke-width="1"/>
  <text x="50" y="105" text-anchor="start" fill="var(--dark)" font-size="14" font-family="system-ui, -apple-system, sans-serif" font-weight="500"><tspan>Airfare, travel, and lodging</tspan></text>
  <text x="776" y="105" text-anchor="end" fill="var(--dark)" font-size="14" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan>43%</tspan></text>
  <rect x="24" y="122" width="16" height="16" rx="3" fill="var(--tertiary)" stroke="var(--lightgray)" stroke-width="1"/>
  <text x="50" y="135" text-anchor="start" fill="var(--dark)" font-size="14" font-family="system-ui, -apple-system, sans-serif" font-weight="500"><tspan>Retail</tspan></text>
  <text x="776" y="135" text-anchor="end" fill="var(--dark)" font-size="14" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan>34%</tspan></text>
  <rect x="24" y="152" width="16" height="16" rx="3" fill="color-mix(in srgb, var(--secondary) 50%, var(--light))" stroke="var(--lightgray)" stroke-width="1"/>
  <text x="50" y="165" text-anchor="start" fill="var(--dark)" font-size="14" font-family="system-ui, -apple-system, sans-serif" font-weight="500"><tspan>Life admin</tspan></text>
  <text x="776" y="165" text-anchor="end" fill="var(--dark)" font-size="14" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan>7%</tspan></text>
  <rect x="24" y="182" width="16" height="16" rx="3" fill="color-mix(in srgb, var(--tertiary) 50%, var(--light))" stroke="var(--lightgray)" stroke-width="1"/>
  <text x="50" y="195" text-anchor="start" fill="var(--dark)" font-size="14" font-family="system-ui, -apple-system, sans-serif" font-weight="500"><tspan>Events and performances</tspan></text>
  <text x="776" y="195" text-anchor="end" fill="var(--dark)" font-size="14" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan>4%</tspan></text>
  <rect x="24" y="212" width="16" height="16" rx="3" fill="var(--darkgray)" stroke="var(--lightgray)" stroke-width="1"/>
  <text x="50" y="225" text-anchor="start" fill="var(--dark)" font-size="14" font-family="system-ui, -apple-system, sans-serif" font-weight="500"><tspan>Other</tspan></text>
  <text x="776" y="225" text-anchor="end" fill="var(--dark)" font-size="14" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan>11%</tspan></text>
</svg>
<figcaption>Last seven days through November 19, 2026. The labeled shares add to 99%; the chart does not explain the remaining 1%.</figcaption>
</figure>

<figure class="afr-cheatsheet-visual afr-cheatsheet-visual--mobile">
<svg role="img" viewBox="0 0 360 420" xmlns="http://www.w3.org/2000/svg" aria-labelledby="link-cat-m-title link-cat-m-desc">
  <title id="link-cat-m-title">Link agentic spending by category</title>
  <desc id="link-cat-m-desc">A bar for each category of Link agentic spending for the last seven days through November 19, 2026. Airfare, travel, and lodging 43 percent, retail 34 percent, life admin 7 percent, events and performances 4 percent, and other 11 percent. The labeled shares add to 99 percent; the chart does not explain the remaining 1 percent.</desc>
  <rect width="360" height="420" fill="var(--light)"/>
  <text x="16" y="30" text-anchor="start" fill="var(--dark)" font-size="14" font-family="system-ui, -apple-system, sans-serif" font-weight="500"><tspan>Airfare, travel, and lodging</tspan></text>
  <text x="344" y="30" text-anchor="end" fill="var(--dark)" font-size="14" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan>43%</tspan></text>
  <rect x="16" y="40" width="268" height="18" rx="4" fill="var(--highlight)" stroke="var(--lightgray)" stroke-width="1"/>
  <rect x="16" y="40" width="115.24" height="18" rx="4" fill="var(--secondary)"/>
  <text x="16" y="110" text-anchor="start" fill="var(--dark)" font-size="14" font-family="system-ui, -apple-system, sans-serif" font-weight="500"><tspan>Retail</tspan></text>
  <text x="344" y="110" text-anchor="end" fill="var(--dark)" font-size="14" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan>34%</tspan></text>
  <rect x="16" y="120" width="268" height="18" rx="4" fill="var(--highlight)" stroke="var(--lightgray)" stroke-width="1"/>
  <rect x="16" y="120" width="91.12" height="18" rx="4" fill="var(--tertiary)"/>
  <text x="16" y="190" text-anchor="start" fill="var(--dark)" font-size="14" font-family="system-ui, -apple-system, sans-serif" font-weight="500"><tspan>Life admin</tspan></text>
  <text x="344" y="190" text-anchor="end" fill="var(--dark)" font-size="14" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan>7%</tspan></text>
  <rect x="16" y="200" width="268" height="18" rx="4" fill="var(--highlight)" stroke="var(--lightgray)" stroke-width="1"/>
  <rect x="16" y="200" width="18.76" height="18" rx="4" fill="color-mix(in srgb, var(--secondary) 50%, var(--light))"/>
  <text x="16" y="270" text-anchor="start" fill="var(--dark)" font-size="14" font-family="system-ui, -apple-system, sans-serif" font-weight="500"><tspan>Events and performances</tspan></text>
  <text x="344" y="270" text-anchor="end" fill="var(--dark)" font-size="14" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan>4%</tspan></text>
  <rect x="16" y="280" width="268" height="18" rx="4" fill="var(--highlight)" stroke="var(--lightgray)" stroke-width="1"/>
  <rect x="16" y="280" width="10.72" height="18" rx="4" fill="color-mix(in srgb, var(--tertiary) 50%, var(--light))"/>
  <text x="16" y="350" text-anchor="start" fill="var(--dark)" font-size="14" font-family="system-ui, -apple-system, sans-serif" font-weight="500"><tspan>Other</tspan></text>
  <text x="344" y="350" text-anchor="end" fill="var(--dark)" font-size="14" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan>11%</tspan></text>
  <rect x="16" y="360" width="268" height="18" rx="4" fill="var(--highlight)" stroke="var(--lightgray)" stroke-width="1"/>
  <rect x="16" y="360" width="29.48" height="18" rx="4" fill="var(--darkgray)"/>
</svg>
<figcaption>Last seven days through November 19, 2026. The labeled shares add to 99%; the chart does not explain the remaining 1%.</figcaption>
</figure>

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
