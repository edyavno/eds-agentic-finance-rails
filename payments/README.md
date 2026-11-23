---
type: payment
title: Payments
summary: 'How AI agents pay: card-network agent programs, payment tokens, wallets, protocols and agent cards, each with a sourced page, plus merchants that ban agents.'
page_status: current
last_verified: '2026-11-23'
---

# Payments

This section covers how an AI agent pays for things on a person's behalf, often called [agentic commerce](../glossary.md#agentic-commerce). Each program has its own page. Each page starts with a short record: who runs it, what an agent can do, what the person controls, whether there is an official [MCP](../glossary.md#mcp) server, and how available it is. Every value is sourced or says "unknown." The same records are in [data/programs.json](../data/programs.json).

## The programs

| Program | Type | In one line |
|---|---|---|
| [Visa Intelligent Commerce](visa-intelligent-commerce.md) | Card network | Approved agent builders pay with tokenized Visa credentials, under purchase instructions the consumer approved.[^pm-01] |
| [Visa CLI](visa-cli.md) | Card network | A Visa Crypto Labs product: after a US Visa card check, an agent gets a signing key, is listed in the [Visa Agent Directory](../glossary.md#visa-agent-directory), and can pay HTTP 402 requests in [OUSD](../glossary.md#ousd) within owner-set limits.[^pm-27][^pm-28] |
| [Mastercard Agent Pay](mastercard-agent-pay.md) | Card network | Only registered agents can pay, using Mastercard agentic tokens.[^pm-05][^pm-06] |
| [Agentic Commerce Protocol (ACP)](agentic-commerce-protocol.md) | Commerce protocol | An open standard for buyers, their agents and businesses to complete purchases. OpenAI and Stripe maintain it, and it is in beta.[^pm-07] |
| [Stripe](stripe.md) | Payment tokens and MCP | Shared payment tokens give a seller limited use of a customer's payment method. Stripe also runs an official MCP server.[^pm-08][^pm-09] |
| [PayPal](paypal.md) | MCP server and toolkit | An MCP server and an agent toolkit for PayPal business APIs such as orders and invoices.[^pm-10][^pm-11] |
| [x402](x402.md) | Payment protocol | An open standard for paying inside a web request, built on the HTTP 402 "Payment Required" status.[^pm-14][^pm-15] |
| [AP2 (Agent Payments Protocol)](ap2.md) | Mandate protocol | An open protocol that carries signed proof of what the user authorized.[^pm-13] |
| [Robinhood Agentic Credit Card](robinhood-agentic-credit-card.md) | Agent card | A [virtual card](../glossary.md#virtual-card) for your agent, with approval for each purchase or a required monthly limit.[^rh-09] |
| [ChatGPT Wallet](chatgpt-wallet.md) | Payment token wallet | OpenAI's wallet for agents in ChatGPT. You approve each purchase with a biometric check, and the card network supplies a payment token.[^oa-01] |
| [Link wallet for agents](link-wallet-for-agents.md) | Consumer wallet for agents | Stripe's Link wallet gives an agent a one-time card or shared payment token for each purchase you approve in Link. Muse, Grok Bot, Instinct and Claude Duet use it or a wallet like it.[^sp-01][^sp-02] |
| [X Money](../personal-money/x-money.md) | Money account with an agent plugin | A US account in the X app. Through the Grok Bot plugin an agent can read the balance, pay with the X card and send money, with approval for each money move.[^xm-01] |
| [Rain Agent Vaults](rain-agent-vaults.md) | Agent card | A funded balance for an agent, which pays with a single-use virtual card issued for each purchase under the owner's rules.[^rn-01] |
| [AgentBank](agentbank.md) | Payment MCP | An MCP server for collecting, converting and sending money, with owner confirmation on every payment and an approval threshold.[^ag-01][^ag-02] |
| [Amazon Bedrock AgentCore payments](agentcore-payments.md) | Cloud payment service | AWS service for agents to pay over x402 and MPP within per-session budgets, and to pay AWS Marketplace sellers in US dollars on the AWS bill.[^aw-01][^aw-02] |
| [Lightspark Agent Accounts](lightspark-agent-accounts.md) | Agent account | Accounts where an agent holds and spends money within limits and approvals the owner sets, paying Visa merchants with a card valid for one purchase.[^ls-01][^ls-02] |
| [Merchants and outside agents](merchants-and-outside-agents.md) | Topic | eBay and United forbid AI agents from buying on their sites without permission.[^eb-01][^ua-01] |

## Klarna in Adyen Agentic checkout

On 2026-11-20 Klarna and Adyen said shoppers can pay with Klarna when an AI agent checks out through [Adyen Agentic](https://www.adyen.com/agentic-commerce), Adyen's agentic commerce suite. Klarna is the first payment option beyond cards there. Merchants that already offer Klarna through Adyen can switch it on with no new integration. The agent shows the same Klarna options the merchant already offers, such as paying in full, in interest-free installments or with financing. Shoppers review and confirm every purchase before it is completed.[^pm-29]

Adyen built the integration on Klarna's open [payment handler](../glossary.md#payment-handler), a published specification any payment provider can use. The release does not link that specification, so its URL is unknown, and it does not name the AI platforms where the checkout runs.[^pm-29]

## How the controls work

The sources describe four kinds of control. Most programs use more than one.

- **The network vets the agent.** Visa requires approved participants and agent registration before production use.[^pm-01] Mastercard registers and verifies agents before they can transact.[^pm-06]
- **The credential is limited.** Stripe's shared payment tokens carry usage and expiry limits.[^pm-08] Visa and Mastercard use tokenized credentials instead of the raw card number.[^pm-01][^pm-06] See [payment token](../glossary.md#payment-token).
- **The person approves.** Robinhood lets you approve each purchase in its app. If you turn that off, a monthly limit is required.[^rh-09] AP2 records the user's authorization as signed [mandates](../glossary.md#mandates).[^pm-13] ChatGPT Wallet asks for a biometric check on each purchase.[^oa-01] AgentBank asks the owner to confirm every payment, with an extra approval above a threshold.[^ag-02] When an agent checks out through Adyen Agentic with Klarna, shoppers review and confirm every purchase.[^pm-29]
- **The balance is limited.** Rain Agent Vaults let an agent spend only what its owner put in the vault, one scoped card at a time.[^rn-01]

## Which controls does each program use?

The same four controls, across the programs on this page. The topic page [Merchants and outside agents](merchants-and-outside-agents.md) is not a payment program, so it is not in the diagram.

<figure class="afr-cheatsheet-visual afr-cheatsheet-visual--desktop">
<svg role="img" viewBox="0 0 800 604" xmlns="http://www.w3.org/2000/svg" aria-labelledby="pay-d-title pay-d-desc">
  <title id="pay-d-title">Which controls each payment program uses</title>
  <desc id="pay-d-desc">A matrix of 15 payment programs against four controls: the network vets the agent, the credential is limited, the person approves, and the balance is limited. A filled circle means a cited source describes that control. A hollow circle means unknown: no cited source confirms it. A diamond means a cited source describes a related limit that is not exactly that control: AgentCore has a session budget and expiry; Lightspark lets the owner decide which payments need approval and set spending limits. Visa and Mastercard have a filled circle for the first three controls. Stripe, ChatGPT Wallet, Link, Rain and Lightspark have a limited credential. AP2, Robinhood's agentic card, ChatGPT Wallet, Link, X Money and AgentBank have person approval. Rain has a funded vault. ACP, PayPal and x402 are unknown on all four controls.</desc>
  <rect width="800" height="604" fill="var(--light)"/>
  <rect x="0" y="0" width="800" height="68" fill="var(--light)"/>
<text x="273.0" y="28" text-anchor="middle" fill="var(--darkgray)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="273.0" y="28">Network vets</tspan>
  <tspan x="273.0" dy="16">the agent</tspan>
  </text>
<text x="419.0" y="28" text-anchor="middle" fill="var(--darkgray)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="419.0" y="28">Credential</tspan>
  <tspan x="419.0" dy="16">is limited</tspan>
  </text>
<text x="565.0" y="28" text-anchor="middle" fill="var(--darkgray)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="565.0" y="28">Person</tspan>
  <tspan x="565.0" dy="16">approves</tspan>
  </text>
<text x="711.0" y="28" text-anchor="middle" fill="var(--darkgray)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="711.0" y="28">Balance</tspan>
  <tspan x="711.0" dy="16">is limited</tspan>
  </text>
  <rect x="0" y="68" width="800" height="32" fill="var(--lightgray)" fill-opacity="0.28"/>
<text x="14" y="89.0" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="14" y="89.0">Visa</tspan>
  </text>
  <circle cx="273.0" cy="84.0" r="8" fill="var(--secondary)"/>
  <circle cx="419.0" cy="84.0" r="8" fill="var(--secondary)"/>
  <circle cx="565.0" cy="84.0" r="8" fill="var(--secondary)"/>
  <circle cx="711.0" cy="84.0" r="8" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
<text x="14" y="121.0" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="14" y="121.0">Mastercard</tspan>
  </text>
  <circle cx="273.0" cy="116.0" r="8" fill="var(--secondary)"/>
  <circle cx="419.0" cy="116.0" r="8" fill="var(--secondary)"/>
  <circle cx="565.0" cy="116.0" r="8" fill="var(--secondary)"/>
  <circle cx="711.0" cy="116.0" r="8" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <rect x="0" y="132" width="800" height="32" fill="var(--lightgray)" fill-opacity="0.28"/>
<text x="14" y="153.0" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="14" y="153.0">ACP</tspan>
  </text>
  <circle cx="273.0" cy="148.0" r="8" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="419.0" cy="148.0" r="8" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="565.0" cy="148.0" r="8" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="711.0" cy="148.0" r="8" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
<text x="14" y="185.0" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="14" y="185.0">Stripe</tspan>
  </text>
  <circle cx="273.0" cy="180.0" r="8" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="419.0" cy="180.0" r="8" fill="var(--secondary)"/>
  <circle cx="565.0" cy="180.0" r="8" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="711.0" cy="180.0" r="8" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <rect x="0" y="196" width="800" height="32" fill="var(--lightgray)" fill-opacity="0.28"/>
<text x="14" y="217.0" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="14" y="217.0">PayPal</tspan>
  </text>
  <circle cx="273.0" cy="212.0" r="8" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="419.0" cy="212.0" r="8" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="565.0" cy="212.0" r="8" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="711.0" cy="212.0" r="8" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
<text x="14" y="249.0" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="14" y="249.0">x402</tspan>
  </text>
  <circle cx="273.0" cy="244.0" r="8" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="419.0" cy="244.0" r="8" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="565.0" cy="244.0" r="8" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="711.0" cy="244.0" r="8" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <rect x="0" y="260" width="800" height="32" fill="var(--lightgray)" fill-opacity="0.28"/>
<text x="14" y="281.0" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="14" y="281.0">AP2</tspan>
  </text>
  <circle cx="273.0" cy="276.0" r="8" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="419.0" cy="276.0" r="8" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="565.0" cy="276.0" r="8" fill="var(--secondary)"/>
  <circle cx="711.0" cy="276.0" r="8" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
<text x="14" y="313.0" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="14" y="313.0">Robinhood card</tspan>
  </text>
  <circle cx="273.0" cy="308.0" r="8" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="419.0" cy="308.0" r="8" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="565.0" cy="308.0" r="8" fill="var(--secondary)"/>
  <circle cx="711.0" cy="308.0" r="8" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <rect x="0" y="324" width="800" height="32" fill="var(--lightgray)" fill-opacity="0.28"/>
<text x="14" y="345.0" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="14" y="345.0">ChatGPT Wallet</tspan>
  </text>
  <circle cx="273.0" cy="340.0" r="8" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="419.0" cy="340.0" r="8" fill="var(--secondary)"/>
  <circle cx="565.0" cy="340.0" r="8" fill="var(--secondary)"/>
  <circle cx="711.0" cy="340.0" r="8" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
<text x="14" y="377.0" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="14" y="377.0">Link wallet</tspan>
  </text>
  <circle cx="273.0" cy="372.0" r="8" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="419.0" cy="372.0" r="8" fill="var(--secondary)"/>
  <circle cx="565.0" cy="372.0" r="8" fill="var(--secondary)"/>
  <circle cx="711.0" cy="372.0" r="8" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <rect x="0" y="388" width="800" height="32" fill="var(--lightgray)" fill-opacity="0.28"/>
<text x="14" y="409.0" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="14" y="409.0">X Money</tspan>
  </text>
  <circle cx="273.0" cy="404.0" r="8" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="419.0" cy="404.0" r="8" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="565.0" cy="404.0" r="8" fill="var(--secondary)"/>
  <circle cx="711.0" cy="404.0" r="8" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
<text x="14" y="441.0" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="14" y="441.0">Rain Vaults</tspan>
  </text>
  <circle cx="273.0" cy="436.0" r="8" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="419.0" cy="436.0" r="8" fill="var(--secondary)"/>
  <circle cx="565.0" cy="436.0" r="8" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="711.0" cy="436.0" r="8" fill="var(--secondary)"/>
  <rect x="0" y="452" width="800" height="32" fill="var(--lightgray)" fill-opacity="0.28"/>
<text x="14" y="473.0" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="14" y="473.0">AgentBank</tspan>
  </text>
  <circle cx="273.0" cy="468.0" r="8" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="419.0" cy="468.0" r="8" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="565.0" cy="468.0" r="8" fill="var(--secondary)"/>
  <circle cx="711.0" cy="468.0" r="8" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
<text x="14" y="505.0" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="14" y="505.0">AgentCore</tspan>
  </text>
  <circle cx="273.0" cy="500.0" r="8" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="419.0" cy="500.0" r="8" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="565.0" cy="500.0" r="8" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <path d="M711.0,491.0 L720.0,500.0 L711.0,509.0 L702.0,500.0 Z" fill="var(--tertiary)"/>
  <rect x="0" y="516" width="800" height="32" fill="var(--lightgray)" fill-opacity="0.28"/>
<text x="14" y="537.0" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="14" y="537.0">Lightspark</tspan>
  </text>
  <circle cx="273.0" cy="532.0" r="8" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="419.0" cy="532.0" r="8" fill="var(--secondary)"/>
  <path d="M565.0,523.0 L574.0,532.0 L565.0,541.0 L556.0,532.0 Z" fill="var(--tertiary)"/>
  <path d="M711.0,523.0 L720.0,532.0 L711.0,541.0 L702.0,532.0 Z" fill="var(--tertiary)"/>
  <circle cx="24" cy="570" r="8" fill="var(--secondary)"/>
<text x="38" y="574" text-anchor="start" fill="var(--darkgray)" font-size="12" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="38" y="574">Yes, cited</tspan>
  </text>
  <circle cx="146" cy="570" r="8" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
<text x="160" y="574" text-anchor="start" fill="var(--darkgray)" font-size="12" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="160" y="574">unknown</tspan>
  </text>
  <path d="M266,561 L275,570 L266,579 L257,570 Z" fill="var(--tertiary)"/>
<text x="282" y="574" text-anchor="start" fill="var(--darkgray)" font-size="12" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="282" y="574">Related cited limit, not exactly this control</tspan>
  </text>
</svg>
<figcaption>A filled circle means a cited source describes that control. A hollow circle is unknown. A diamond is a related, cited limit that is not exactly the control in that column.</figcaption>
</figure>

<figure class="afr-cheatsheet-visual afr-cheatsheet-visual--mobile">
<svg role="img" viewBox="0 0 360 736" xmlns="http://www.w3.org/2000/svg" aria-labelledby="pay-m-title pay-m-desc">
  <title id="pay-m-title">Which controls each payment program uses</title>
  <desc id="pay-m-desc">A matrix of 15 payment programs against four controls: the network vets the agent, the credential is limited, the person approves, and the balance is limited. A filled circle means a cited source describes that control. A hollow circle means unknown: no cited source confirms it. A diamond means a cited source describes a related limit that is not exactly that control: AgentCore has a session budget and expiry; Lightspark lets the owner decide which payments need approval and set spending limits. Visa and Mastercard have a filled circle for the first three controls. Stripe, ChatGPT Wallet, Link, Rain and Lightspark have a limited credential. AP2, Robinhood's agentic card, ChatGPT Wallet, Link, X Money and AgentBank have person approval. Rain has a funded vault. ACP, PayPal and x402 are unknown on all four controls.</desc>
  <rect width="360" height="736" fill="var(--light)"/>
  <rect x="0" y="0" width="360" height="68" fill="var(--light)"/>
<text x="158.5" y="40" text-anchor="middle" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="158.5" y="40">Vets</tspan>
  </text>
<text x="211.5" y="40" text-anchor="middle" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="211.5" y="40">Cred</tspan>
  </text>
<text x="264.5" y="40" text-anchor="middle" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="264.5" y="40">Appr</tspan>
  </text>
<text x="317.5" y="40" text-anchor="middle" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="317.5" y="40">Bal</tspan>
  </text>
  <rect x="0" y="68" width="360" height="36" fill="var(--lightgray)" fill-opacity="0.28"/>
<text x="14" y="91.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="14" y="91.0">Visa</tspan>
  </text>
  <circle cx="158.5" cy="86.0" r="7" fill="var(--secondary)"/>
  <circle cx="211.5" cy="86.0" r="7" fill="var(--secondary)"/>
  <circle cx="264.5" cy="86.0" r="7" fill="var(--secondary)"/>
  <circle cx="317.5" cy="86.0" r="7" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
<text x="14" y="127.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="14" y="127.0">Mastercard</tspan>
  </text>
  <circle cx="158.5" cy="122.0" r="7" fill="var(--secondary)"/>
  <circle cx="211.5" cy="122.0" r="7" fill="var(--secondary)"/>
  <circle cx="264.5" cy="122.0" r="7" fill="var(--secondary)"/>
  <circle cx="317.5" cy="122.0" r="7" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <rect x="0" y="140" width="360" height="36" fill="var(--lightgray)" fill-opacity="0.28"/>
<text x="14" y="163.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="14" y="163.0">ACP</tspan>
  </text>
  <circle cx="158.5" cy="158.0" r="7" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="211.5" cy="158.0" r="7" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="264.5" cy="158.0" r="7" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="317.5" cy="158.0" r="7" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
<text x="14" y="199.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="14" y="199.0">Stripe</tspan>
  </text>
  <circle cx="158.5" cy="194.0" r="7" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="211.5" cy="194.0" r="7" fill="var(--secondary)"/>
  <circle cx="264.5" cy="194.0" r="7" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="317.5" cy="194.0" r="7" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <rect x="0" y="212" width="360" height="36" fill="var(--lightgray)" fill-opacity="0.28"/>
<text x="14" y="235.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="14" y="235.0">PayPal</tspan>
  </text>
  <circle cx="158.5" cy="230.0" r="7" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="211.5" cy="230.0" r="7" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="264.5" cy="230.0" r="7" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="317.5" cy="230.0" r="7" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
<text x="14" y="271.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="14" y="271.0">x402</tspan>
  </text>
  <circle cx="158.5" cy="266.0" r="7" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="211.5" cy="266.0" r="7" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="264.5" cy="266.0" r="7" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="317.5" cy="266.0" r="7" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <rect x="0" y="284" width="360" height="36" fill="var(--lightgray)" fill-opacity="0.28"/>
<text x="14" y="307.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="14" y="307.0">AP2</tspan>
  </text>
  <circle cx="158.5" cy="302.0" r="7" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="211.5" cy="302.0" r="7" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="264.5" cy="302.0" r="7" fill="var(--secondary)"/>
  <circle cx="317.5" cy="302.0" r="7" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
<text x="14" y="343.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="14" y="343.0">Robinhood card</tspan>
  </text>
  <circle cx="158.5" cy="338.0" r="7" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="211.5" cy="338.0" r="7" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="264.5" cy="338.0" r="7" fill="var(--secondary)"/>
  <circle cx="317.5" cy="338.0" r="7" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <rect x="0" y="356" width="360" height="36" fill="var(--lightgray)" fill-opacity="0.28"/>
<text x="14" y="379.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="14" y="379.0">ChatGPT Wallet</tspan>
  </text>
  <circle cx="158.5" cy="374.0" r="7" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="211.5" cy="374.0" r="7" fill="var(--secondary)"/>
  <circle cx="264.5" cy="374.0" r="7" fill="var(--secondary)"/>
  <circle cx="317.5" cy="374.0" r="7" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
<text x="14" y="415.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="14" y="415.0">Link wallet</tspan>
  </text>
  <circle cx="158.5" cy="410.0" r="7" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="211.5" cy="410.0" r="7" fill="var(--secondary)"/>
  <circle cx="264.5" cy="410.0" r="7" fill="var(--secondary)"/>
  <circle cx="317.5" cy="410.0" r="7" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <rect x="0" y="428" width="360" height="36" fill="var(--lightgray)" fill-opacity="0.28"/>
<text x="14" y="451.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="14" y="451.0">X Money</tspan>
  </text>
  <circle cx="158.5" cy="446.0" r="7" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="211.5" cy="446.0" r="7" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="264.5" cy="446.0" r="7" fill="var(--secondary)"/>
  <circle cx="317.5" cy="446.0" r="7" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
<text x="14" y="487.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="14" y="487.0">Rain Vaults</tspan>
  </text>
  <circle cx="158.5" cy="482.0" r="7" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="211.5" cy="482.0" r="7" fill="var(--secondary)"/>
  <circle cx="264.5" cy="482.0" r="7" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="317.5" cy="482.0" r="7" fill="var(--secondary)"/>
  <rect x="0" y="500" width="360" height="36" fill="var(--lightgray)" fill-opacity="0.28"/>
<text x="14" y="523.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="14" y="523.0">AgentBank</tspan>
  </text>
  <circle cx="158.5" cy="518.0" r="7" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="211.5" cy="518.0" r="7" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="264.5" cy="518.0" r="7" fill="var(--secondary)"/>
  <circle cx="317.5" cy="518.0" r="7" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
<text x="14" y="559.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="14" y="559.0">AgentCore</tspan>
  </text>
  <circle cx="158.5" cy="554.0" r="7" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="211.5" cy="554.0" r="7" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="264.5" cy="554.0" r="7" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <path d="M317.5,546.0 L325.5,554.0 L317.5,562.0 L309.5,554.0 Z" fill="var(--tertiary)"/>
  <rect x="0" y="572" width="360" height="36" fill="var(--lightgray)" fill-opacity="0.28"/>
<text x="14" y="595.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="14" y="595.0">Lightspark</tspan>
  </text>
  <circle cx="158.5" cy="590.0" r="7" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
  <circle cx="211.5" cy="590.0" r="7" fill="var(--secondary)"/>
  <path d="M264.5,582.0 L272.5,590.0 L264.5,598.0 L256.5,590.0 Z" fill="var(--tertiary)"/>
  <path d="M317.5,582.0 L325.5,590.0 L317.5,598.0 L309.5,590.0 Z" fill="var(--tertiary)"/>
<text x="14" y="622" text-anchor="start" fill="var(--darkgray)" font-size="10" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="14" y="622">Columns: Vets = network vets the agent</tspan>
  <tspan x="14" dy="13">Cred = credential is limited · Appr = person approves</tspan>
  <tspan x="14" dy="13">Bal = balance is limited</tspan>
  </text>
  <circle cx="22" cy="668" r="7" fill="var(--secondary)"/>
<text x="36" y="672" text-anchor="start" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="36" y="672">Yes, a cited source describes this</tspan>
  </text>
  <circle cx="22" cy="690" r="7" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
<text x="36" y="694" text-anchor="start" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="36" y="694">unknown: no cited source confirms it</tspan>
  </text>
  <path d="M22,705 L29,712 L22,719 L15,712 Z" fill="var(--tertiary)"/>
<text x="36" y="716" text-anchor="start" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="36" y="716">A related cited limit, not exactly this control</tspan>
  </text>
</svg>
<figcaption>A filled circle means a cited source describes that control. A hollow circle is unknown. A diamond is a related, cited limit that is not exactly the control in that column.</figcaption>
</figure>

<details class="afr-cheatsheet-sources">
<summary>Sources and full table</summary>

| Program | Network vets the agent | Credential is limited | Person approves | Balance is limited | Sources |
|---|---|---|---|---|---|
| [Visa Intelligent Commerce](visa-intelligent-commerce.md) | Yes | Yes: tokenized credentials, not the raw card number | Yes: purchase instructions the consumer approved | unknown | [^pm-01] |
| [Mastercard Agent Pay](mastercard-agent-pay.md) | Yes | Yes: agentic tokens | Yes: each transaction is checked against authenticated user intent and explicit consent | unknown | [^pm-05][^pm-06] |
| [Agentic Commerce Protocol (ACP)](agentic-commerce-protocol.md) | unknown | unknown | unknown | unknown | |
| [Stripe](stripe.md) | unknown | Yes: shared payment tokens have usage and expiry limits | unknown | unknown | [^pm-08] |
| [PayPal](paypal.md) | unknown | unknown | unknown | unknown | |
| [x402](x402.md) | unknown | unknown | unknown | unknown | |
| [AP2 (Agent Payments Protocol)](ap2.md) | unknown | unknown | Yes: signed [mandates](../glossary.md#mandates) | unknown | [^pm-13] |
| [Robinhood Agentic Credit Card](robinhood-agentic-credit-card.md) | unknown | unknown | Yes: you approve each purchase, or a monthly limit is required if you turn that off | unknown | [^rh-09] |
| [ChatGPT Wallet](chatgpt-wallet.md) | unknown | Yes: a one-purchase [payment token](../glossary.md#payment-token) | Yes: a biometric check on each purchase | unknown | [^oa-01] |
| [Link wallet for agents](link-wallet-for-agents.md) | unknown | Yes: a one-time card or shared payment token, scoped by amount, currency and merchant | Yes: you approve each spend request in Link | unknown | [^sp-01][^sp-02] |
| [X Money](../personal-money/x-money.md) | unknown | unknown | Yes: approval for each money move | unknown | [^xm-01] |
| [Rain Agent Vaults](rain-agent-vaults.md) | unknown | Yes: a scoped virtual card issued for each purchase | unknown | Yes: the agent can spend only what the owner put in the vault | [^rn-01] |
| [AgentBank](agentbank.md) | unknown | unknown | Yes: the owner confirms every payment, with an extra approval above a threshold | unknown | [^ag-02] |
| [Amazon Bedrock AgentCore payments](agentcore-payments.md) | unknown | unknown | unknown | Session budget and expiry: further payments are denied once either is reached | [^aw-01][^aw-02] |
| [Lightspark Agent Accounts](lightspark-agent-accounts.md) | unknown | Yes: a card valid for that purchase alone, or a saved card seen only as a card ID | The owner decides which payments need approval | Spending limits the owner sets | [^ls-01][^ls-02] |

</details>

## What can an agent do with each program?

Every program side by side. Each value is sourced on its own page, and `unknown` means no source confirms it yet. The same records are in [data/programs.json](../data/programs.json).

<details class="afr-cheatsheet-sources">
<summary>Full details for every program</summary>

<!-- records: generated by afr generate from page headers; do not edit -->

| Program | Operator | What an agent can do | What you control | Official MCP | Availability | Updated |
|---|---|---|---|---|---|---|
| [AgentBank](agentbank.md) | AgentBank, operated by Thinking Horizon, Inc. | Collect payments, convert between currencies and crypto assets, pay bank, QR or wallet recipients in local currency, and pay x402 services, through an MCP server | The owner confirms the recipient, amounts, fees and expiry of every payment before it is created. An approval threshold sets when a payment needs an extra approval. ChatGPT and Claude connections can also have a spending limit, and the owner can disconnect an agent at any time | Yes | unknown | 2026-11-19 |
| [Amazon Bedrock AgentCore payments](agentcore-payments.md) | Amazon Web Services (AWS) | Pay for paid APIs, MCP servers and web content over x402 and the Machine Payments Protocol, through a configured wallet provider, and pay x402-enabled AWS Marketplace sellers per request in US dollars on the AWS bill | Each payment session has a budget limit and an expiry, and further payments are denied once either is reached. Developers can also set spending limits and approved sellers with AgentCore policy, and AWS Marketplace purchases appear in AWS CloudTrail and AWS Cost Explorer | unknown | Generally available since August 2026. AWS Marketplace payments are available in all AWS Regions where AgentCore payments is available, and the list of Regions is unknown | 2026-11-20 |
| [Agentic Commerce Protocol (ACP)](agentic-commerce-protocol.md) | OpenAI and Stripe (spec maintainers) | Let a user find and buy from a business inside an AI app, through a checkout API and a delegated-payment spec | unknown | unknown | Beta. OpenAI and Stripe were the first to implement it | 2026-11-14 |
| [AP2 (Agent Payments Protocol)](ap2.md) | Google (reference code on GitHub) | Carry signed proof of what the user authorized: a Checkout Mandate shared with the merchant and a Payment Mandate shared with the credential provider, the card networks and the payment processor | Open mandates hold the user's limits, such as budget and allowed payment methods, before a cart is final. Closed mandates authorize one finalized checkout and amount | unknown | Open protocol, available as an extension for A2A and Universal Commerce Protocol. Samples in Python, Go and Android | 2026-11-20 |
| [ChatGPT Wallet](chatgpt-wallet.md) | OpenAI, built with American Express, Mastercard and Visa | Complete a purchase at a merchant's normal checkout with a one-purchase payment token, after you approve it | You review the items, total and card, then approve each purchase with a biometric check such as Face ID. The terms also allow granting ChatGPT authority to approve purchases in advance | unknown | Rolling out from 2026-11-13 in dots, to ChatGPT Pro users in the US aged 18 or older with eligible US-issued American Express, Chase, Mastercard and Visa cards | 2026-11-23 |
| [Lightspark Agent Accounts](lightspark-agent-accounts.md) | Lightspark Group, Inc. | Hold, spend, send and receive money for a person or business, pay a merchant that accepts Visa with a card valid for that purchase alone or a saved card seen only as a card ID, and settle directly with a merchant that has an Agent Account | The account holder sets spending limits and decides which payments need their approval. The customer authorizes a delegated key once and can pause the agent, revoke the key or delete the agent at any time | unknown | Launched 2026-11-17 for companies building agents for consumers, small businesses and merchants. The Agents API must be enabled for each platform | 2026-11-20 |
| [Link wallet for agents](link-wallet-for-agents.md) | Stripe | Create a spend request in a person's Link wallet to get a one-time-use card or a shared payment token for a purchase, scoped by amount, currency and merchant. Stripe says Link can also tell an agent how to continue, such as a 3D Secure link, and an agent can ask for a higher approved amount | The person grants wallet access through OAuth and approves each spend request in Link on web, iOS or Android. They can track agent spending and manage connected agents in Link. Stripe plans spending limits and a way to let agents act without approving each purchase, with no date given | unknown | Stripe announced Link's wallet for agents on 2026-04-29. Its 2026-09-08 release says US consumers can connect Link to Muse, and its 2026-09-29 post says Muse is the first agent to offer Link purchase protections | 2026-11-22 |
| [Mastercard Agent Pay](mastercard-agent-pay.md) | Mastercard | Pay with agentic tokens once registered and verified, including through a merchant's normal card checkout form | Mastercard says each transaction is checked against authenticated user intent and explicit consent before the action | unknown | unknown | 2026-11-20 |
| [PayPal](paypal.md) | PayPal | Use PayPal APIs for orders, invoices, subscriptions, shipment tracking, transaction details and disputes | Access uses the PayPal account's own credentials: an access token for the local server, or client ID and secret for the hosted one. A sandbox is available for testing | Yes | Local server (Node.js 18 or later) or hosted server. Sandbox address https://mcp.sandbox.paypal.com | 2026-11-23 |
| [Rain Agent Vaults](rain-agent-vaults.md) | Rain | Spend from a funded vault with a scoped virtual card issued for each purchase, send money to bank accounts in local currency, and send stablecoins | The vault owner sets the rules, such as how much the agent can spend, which merchants it can pay and when. Each card's amount, merchant and expiry are fixed when it is issued, and the agent cannot raise its own limit | unknown | Announced 2026-11-10 for companies and developers building agents, through Rain's sales team | 2026-11-15 |
| [Robinhood Agentic Credit Card](robinhood-agentic-credit-card.md) | Robinhood (Robinhood Credit, Inc.) | Fetch the agentic virtual card's number to finish purchases, and read that card's spending history and settings. The MCP does not browse or shop for you | Approve each purchase in the Robinhood Banking app, or set a monthly limit, which is required if you do not approve each purchase. The agent sees only the cards you authorize | Yes | A virtual card in the Robinhood Gold Card. Card setup and agent sign-in work on desktop only. Announced 2026-05-27 | 2026-11-14 |
| [Stripe](stripe.md) | Stripe | Grant a seller a shared payment token for a purchase. Separately, call the Stripe API and search Stripe's docs through the Stripe MCP server | Each token has usage and expiry limits, such as currency, maximum amount and an expiry window. MCP access is granted on Stripe's OAuth consent page and can be revoked, and Stripe can require you to approve certain MCP actions in the Dashboard | Yes | Shared payment tokens are in public preview in the US, Canada and select European countries | 2026-11-23 |
| [Visa CLI](visa-cli.md) | Visa (Visa Crypto Labs) | Take paid tasks with the reward paid to the owner's wallet, and pay per-request APIs that answer with HTTP 402, in OUSD on Tempo, within limits the owner set. Requests are signed so a server can check them. | The owner passes a Visa card check and sets limits on what the agent can pay. One card and one person can connect up to 25 agents, which can share a wallet. | Yes | Access is by invitation. The card check takes US Visa cards; prepaid, corporate and JPMorgan Chase cards cannot be added yet. New agents have been listed in the Visa Agent Directory since 2026-11-18. | 2026-11-23 |
| [Visa Intelligent Commerce](visa-intelligent-commerce.md) | Visa | Buy things for a consumer with tokenized Visa credentials, under purchase instructions the consumer approved | Consumer-approved purchase instructions, Visa Payment Passkeys with device binding, and network-level controls | Yes | Production needs Visa onboarding and approval at each stage: sandbox, certification, production. Intelligent Commerce Connect was in pilot with select partners as of 2026-04-08 | 2026-11-23 |
| [x402](x402.md) | x402 Foundation | Pay for a web resource as part of the request: the server replies 402 Payment Required with its terms, and the client retries with a payment attached | unknown | unknown | Open standard. Specification version 2 is published | 2026-11-23 |

<!-- /records -->

</details>

## What is still unknown

- Fees for agent payments. None of the cited sources give them.
- Which consumer AI apps can use each card-network program today.
- Production MCP addresses for Visa and Mastercard.
- Which merchants accept agent payments. Some, such as eBay and United, forbid agents in their terms.[^eb-01][^ua-01]

See [gaps](../gaps.md) for the full list.

## Related pages

- [Agent payments](../rails/agent-payments.md): the one-table rail overview.
- [Agent identity](../rails/agent-identity.md): how merchants tell which agent is calling, including Visa's [Trusted Agent Protocol](../glossary.md#trusted-agent-protocol-tap) and Web Bot Auth.
- [Mandates and data access](../rails/mandates-and-data-access.md): proof of authorization and the US data-rights rule.
- [Personal money agents](../personal-money/README.md): agents that work with your bank and card data.
- [Merchants and outside agents](merchants-and-outside-agents.md): merchants whose terms forbid AI agents.
- [AP2 vs ACP vs x402](../analyses/ap2-vs-acp-vs-x402.md): the three open agent payment protocols compared side by side.

Not investment advice.

## Sources

[^pm-01]: [Visa Developer Center](../sources/pm-01.md). Visa Developer, official, retrieved 2026-11-12.
[^pm-27]: [Visa CLI docs: Introduction](../sources/pm-27.md). Visa CLI docs (Visa Crypto Labs), official, retrieved 2026-11-23.
[^pm-28]: [Visa CLI docs: What's live today](../sources/pm-28.md). Visa CLI docs (Visa Crypto Labs), official, retrieved 2026-11-23.
[^pm-05]: [Mastercard Agent Pay: secure, scalable and trusted agentic AI](../sources/pm-05.md). Mastercard, official, retrieved 2026-11-12.
[^pm-06]: [Agentic token framework: Driving trusted AI transactions](../sources/pm-06.md). Mastercard, official, retrieved 2026-11-12.
[^pm-07]: [GitHub - agentic-commerce-protocol/agentic-commerce-protocol: The Agentic Commerce Protocol (ACP) is an interaction model and open standard for connec](../sources/pm-07.md). ACP (GitHub), official, retrieved 2026-11-12.
[^pm-08]: [Shared payment tokens - Stripe Documentation](../sources/pm-08.md). Stripe Docs, official, retrieved 2026-11-12.
[^pm-09]: [Model Context Protocol (MCP) - Stripe Documentation](../sources/pm-09.md). Stripe Docs, official, retrieved 2026-11-19.
[^pm-10]: [MCP server quickstart guide - PayPal Developer](../sources/pm-10.md). PayPal Developer, official, retrieved 2026-11-12.
[^pm-11]: [Agent toolkit quickstart guide - PayPal Developer](../sources/pm-11.md). PayPal Developer, official, retrieved 2026-11-12.
[^pm-14]: [GitHub - x402-foundation/x402: A payments protocol for the internet. Built on HTTP. · GitHub](../sources/pm-14.md). x402 Foundation (GitHub), official, retrieved 2026-11-12.
[^pm-15]: [x402 specification v2](../sources/pm-15.md). x402 Foundation (GitHub), official, retrieved 2026-11-12.
[^pm-13]: [AP2 - Agent Payments Protocol Documentation](../sources/pm-13.md). AP2 Protocol, official, retrieved 2026-11-12.
[^rh-09]: [Agentic Credit Card - Robinhood](../sources/rh-09.md). Robinhood, official, retrieved 2026-11-19.
[^oa-01]: [Introducing ChatGPT Wallet](../sources/oa-01.md). OpenAI, official, retrieved 2026-11-15.
[^sp-01]: [Stripe helps Meta Muse shop with Link](../sources/sp-01.md). Stripe, official, retrieved 2026-11-18.
[^sp-02]: [Giving agents the ability to pay (Stripe)](../sources/sp-02.md). Stripe, official, retrieved 2026-11-18.
[^xm-01]: [X Money plugin README (cursor/plugins, third_party/x-money)](../sources/xm-01.md). cursor/plugins (GitHub), official, retrieved 2026-11-18.
[^rn-01]: [Rain Agent Vaults bring embedded payments to AI agents](../sources/rn-01.md). Rain, official, retrieved 2026-11-15.
[^ag-01]: [Connect your AI agent to real-world money - AgentBank](../sources/ag-01.md). AgentBank, official, retrieved 2026-11-19.
[^ag-02]: [Security and wallet control - AgentBank](../sources/ag-02.md). AgentBank, official, retrieved 2026-11-15.
[^aw-01]: [AWS Marketplace now supports agentic payments with AgentCore](../sources/aw-01.md). Amazon Web Services, official, retrieved 2026-11-20.
[^aw-02]: [Enable AI agents to pay for AWS Marketplace x402 products with Amazon Bedrock AgentCore payments](../sources/aw-02.md). Amazon Web Services (AWS Machine Learning Blog), official, retrieved 2026-11-20.
[^ls-01]: [Lightspark Launches Agent Accounts for AI Agents to Make and Receive Payments](../sources/ls-01.md). Lightspark (via GlobeNewswire), official, retrieved 2026-11-20.
[^ls-02]: [Agent Accounts (Lightspark documentation)](../sources/ls-02.md). Lightspark (documentation), official, retrieved 2026-11-20.
[^eb-01]: [User Agreement - eBay](../sources/eb-01.md). eBay, official, retrieved 2026-11-15.
[^ua-01]: [Contract of Carriage Document - United Airlines](../sources/ua-01.md). United Airlines, official, retrieved 2026-11-15.
[^pm-29]: [Adyen Merchants Can Now Offer Klarna in AI Agent Checkout](../sources/pm-29.md). Klarna and Adyen (Business Wire release on Klarna's investor site), official, retrieved 2026-11-23.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20payments%2FREADME.md&body=Page%3A%20payments%2FREADME.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
