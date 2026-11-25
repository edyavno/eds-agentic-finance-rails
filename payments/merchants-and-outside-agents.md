---
type: payment
title: Merchants and outside agents
summary: Some merchants forbid AI agents from buying. eBay, United and Booking.com ban them without permission, and Target allows only a short list of approved agents.
page_status: current
last_verified: '2026-11-25'
---

# Merchants and outside agents

An agent that can pay still needs the merchant to accept it. Some merchants now forbid AI agents in their terms. Each line below comes from the merchant's own terms or help pages.

## The short version

- **eBay** bans buy-for-me agents and LLM-driven bots unless eBay gives prior express permission.[^eb-01]
- **United Airlines** bans the use of AI agents to make, change or service a ticket, or to buy any product, and restricts agents through travel agencies and aggregators too.[^ua-01][^ua-02]
- **Target** allows only agents on its Approved Agents list, currently its own AI Shopping Assistant, OAI, Google and Microsoft, and prohibits all other agentic commerce tools.[^tg-01]
- **Booking.com** bars automated assistants, including AI-powered assistants, from its platform without its prior express written permission, and does not authorize them to make bookings.[^bk-01]
- **Walmart** runs its own [Agent Gateway](../glossary.md#agent-gateway-walmart). From 2026-11-24, Meta's [Muse](../personal-money/meta-muse.md) can shop Walmart through it, under an [Agent Profile](../glossary.md#agent-profile) the shopper sets in their Walmart account, including a spending limit and purchase approvals.[^wm-01][^wm-02]
- Payment programs are trying to make agents easier to accept. OpenAI warns that some sites may block agent purchases by accident, and asks merchants to recognize signed agent requests with [Web Bot Auth](../glossary.md#web-bot-auth).[^oa-01]
- Sardine, a fraud-prevention company, says merchants decline legitimate agent purchases because agents look like bots, and proposes Know Your Human to fix it. These are Sardine's own claims.[^sd-01] See [Sardine below](#what-does-sardine-say-about-agent-checkouts).

## Merchant by merchant

- **eBay.** Its User Agreement says users may not use "any robot, spider, scraper" or other automated means to access eBay, "including, without limitation buy-for-me agents, LLM-driven bots, or any end-to-end flow that attempts to place orders without human review", except with eBay's prior express permission. The current version took effect on 2026-06-28 for existing users. The previous amendment took effect on 2026-02-20.[^eb-01]
- **United Airlines.** Its Contract of Carriage, revised 2026-11-11, lists "The use of AI Agents to make, modify or service a Ticket, and/or to purchase any service or product" among prohibited practices.[^ua-01] Its definition of an AI agent covers assistants, AI-enabled browsers and standalone agents, whether or not a person supervises or approves what the agent does, including agents reached through a travel agency's tools.[^ua-01] United's help page says:
  - AI research and planning is fine if the tool does not access united.com or the United app.[^ua-02]
  - Agent bookings made before 2026-11-11 will not be canceled.[^ua-02]
  - Assistive technology for customers with disabilities is not affected.[^ua-02]
  - Travel agencies can use their own AI tools only with United's permission, and United does not work with any third-party AI agents yet.[^ua-02]

- **Target.** Its Terms & Conditions, which the page marks as last updated 2026-09-10, have an "Agentic Commerce and Delegated Access" section. It applies when you expressly authorize an AI agent to act in your Target account without continuous human oversight. Only agents that Target provides, or that you approve and Target authorizes, may interact with the site; Target calls them Approved Agents. The current list is Target's AI Shopping Assistant, OAI, Google and Microsoft, and Target may change it at any time. All other agentic commerce tools are "unauthorized, expressly prohibited".[^tg-01]
  - An Approved Agent may sign in, create or change carts, place orders and start returns, subject to limits you approve. Actions within those permissions are treated as authorized by you, and you are responsible for reviewing the agent's activity.[^tg-01]
  - Target can suspend or revoke a third-party agent's access, for example for suspected fraud, misuse or security concerns, and you can revoke access in your Target profile settings.[^tg-01]
- **Booking.com.** Its Customer terms of service, which the page marks as updated 2025-08-25, bar anyone from accessing or scraping the platform with robots or other automated means, "or automated assistants", including AI-powered assistants that work through your browser, without Booking.com's prior, express written permission. Booking.com says it does not authorize automated assistants to make bookings or reservations. It also says it will block anyone it suspects of using automated assistants, including AI-powered assistants, without express permission.[^bk-01]
- **Walmart.** From 2026-11-24, [Muse](../personal-money/meta-muse.md) can shop Walmart through the [Walmart Agent Gateway](../glossary.md#agent-gateway-walmart). The shopper sets up an [Agent Profile](../glossary.md#agent-profile) in their Walmart account, including a spending limit, and can approve purchases and check which purchases the agent made. Checkout uses a card saved in the Walmart account. Walmart's 2026-10-21 announcement said customers must approve agent purchases by default, that Walmart may require additional approvals even within the spending limit, that an Agent Profile can be deleted at any time, and that agents do not receive payment-card information. Which other agents can use the Gateway, and the default spending-limit figures, are unknown.[^wm-01][^wm-02]

## Why merchants say they restrict agents

- United says agents with account access could expose personal information or make bookings, account changes or use of miles without the customer's approval. It wants standard integrations with privacy, security, authorization and accountability protections first.[^ua-02]
- United also says an agent that checks a passenger in automatically could violate FAA and DOT rules, because check-in requires a person to confirm that bags hold no banned substances.[^ua-02]
- eBay's agreement gives no reason in the cited text.[^eb-01] The cited Booking.com terms give none for their agent rule either.[^bk-01]
- Target's terms give no reason for limiting agents to a list. They say Target may restrict an agent's access for suspected fraud, misuse, policy violations or security concerns, and that it is not responsible for third-party agents' conduct.[^tg-01]

## What do merchants say about agent virtual cards?

When an agent pays through Stripe's [Link wallet](link-wallet-for-agents.md) with a one-time [virtual card](../glossary.md#virtual-card), the merchant is paid by that card, not by the shopper's own. The Wall Street Journal reported on 2026-11-13, citing people familiar with the matter, that merchants are complaining to Visa and Mastercard that the virtual card costs more on average to accept, because it is classified as a commercial card rather than a consumer card. It also reported that the temporary cards have made returns harder to process, according to some merchant executives.[^bl-12][^bl-13] These are third-party reports. How large the extra cost is, and whether Visa or Mastercard have responded, is unknown.

PayPal's Agentic Commerce Merchant Virtual Card Terms, last updated 2026-11-23, describe what happens when a buyer pays with PayPal through an agent commerce service and PayPal settles to the merchant with a one-time virtual card (an [Agentic VC](../glossary.md#agentic-vc)). The merchant is responsible for the card-processor fees on that card, must refund to the same Agentic VC, and must show the buyer's payment method as "PayPal". These payments are not eligible under PayPal's Seller Protection program; disputes go through the card network's chargeback process. Which agent services trigger an Agentic VC is not listed in the terms, so it is unknown.[^pm-34] See [PayPal](paypal.md#agentic-vc-merchant-virtual-card-terms).

## What does Sardine say about agent checkouts?

Sardine's blog and product page describe how it says merchants can tell a person's shopping agent from a malicious bot. Everything in this section is Sardine's own claim about its own product. The wiki found no independent test of it.[^sd-01][^sd-02]

- **The problem, per Sardine.** Sardine says shopping agents often convert poorly because merchants mistake them for malicious bots and decline the order. It says an agent usually shops through a cloud browser in a data center, so the merchant sees a data center IP address and a headless browser.[^sd-01] Sardine names [Instinct](../personal-money/instinct.md), [Muse by Meta](../personal-money/meta-muse.md) and [Dots by OpenAI](../personal-money/openai-dots.md) as personal shopping agents that are gaining traction.[^sd-01]
- **What Know Your Human does, per Sardine.** [Know Your Human](../glossary.md#know-your-human-kyh) (KYH) binds the customer's own device to the agent's session.[^sd-01]
- **The flow, per Sardine.** The merchant sends the customer a secure, short-lived link by SMS or email. The customer opens it on their phone, and a page with Sardine's device and behavior SDK captures signals including device ID, fingerprint and IP address, then shows a one-time code. The customer enters the code in the shopping agent's window, the agent submits it at checkout, and the merchant validates it.[^sd-01] Sardine's product page says a link expires 5 minutes after it is created.[^sd-02]
- **What the agent passes.** Sardine says the agent passes a few extra HTTP headers to the merchant, which uses Sardine to retrieve the customer's device and IP signals.[^sd-02] Sardine says KYH is complementary to agentic commerce protocols.[^sd-02]
- **Disputes, per Sardine.** Sardine says Visa's Compelling Evidence 3.0 (CE 3.0) needs at least two matching data elements across the disputed purchase and two qualifying earlier undisputed transactions, and that at least one must be a device ID, fingerprint or IP address match.[^sd-01] It says KYH records those signals against the agent's session and can satisfy the device factor under Mastercard's First-Party Trust program.[^sd-01]
- **Sardine's own caution.** Its product page says Visa CE 3.0 and Mastercard First-Party Trust have their own eligibility and evidence requirements, and that collecting a signal alone does not guarantee a successful dispute response.[^sd-02]
- **Scope.** Sardine's page says its proposal describes possible extensions to email, phone, KYC and identity verification data.[^sd-02]

No merchant or agent is named in these two pages as using KYH today, so that is unknown.

## Related

- [Banks and outside agents](../personal-money/banks-and-outside-agents.md): the same question for bank accounts.
- [Agent identity](../rails/agent-identity.md): how a merchant can tell which agent is calling.
- All programs: [Payments](README.md).

## Unknown

How these merchants detect agents, whether eBay, United or Booking.com grant permission to any agent today, how Target decides who joins its list, and which other large merchants have similar rules. No cited source confirms it, so the wiki says unknown.

## Sources

[^eb-01]: [User Agreement - eBay](../sources/eb-01.md). eBay, official, retrieved 2026-11-15.
[^ua-01]: [Contract of Carriage Document - United Airlines](../sources/ua-01.md). United Airlines, official, retrieved 2026-11-15.
[^ua-02]: [Unauthorized third-party AI agents or assistants - United Airlines](../sources/ua-02.md). United Airlines, official, retrieved 2026-11-15.
[^tg-01]: [Terms & Conditions : Target](../sources/tg-01.md). Target, official, retrieved 2026-11-18.
[^bk-01]: [Booking.com: Terms and Conditions (Customer terms of service)](../sources/bk-01.md). Booking.com, official, retrieved 2026-11-18.
[^wm-01]: [Walmart’s Black Friday Deals Continue. Meta’s Muse Can Now Shop Them, Too.](../sources/wm-01.md). Walmart, official, retrieved 2026-11-25.
[^wm-02]: [Making It Possible for Agents to Shop on Behalf of Customers](../sources/wm-02.md). Walmart, official, retrieved 2026-11-25.
[^oa-01]: [Introducing ChatGPT Wallet](../sources/oa-01.md). OpenAI, official, retrieved 2026-11-15.
[^sd-01]: [Know Your Human (KYH): Fraud prevention for agentic commerce](../sources/sd-01.md). Sardine, official, retrieved 2026-11-20.
[^bl-12]: [AI bots are using credit cards. Banks are racing to keep up. (The Wall Street Journal, via Mint)](../sources/bl-12.md). The Wall Street Journal (syndicated on Mint), third-party, retrieved 2026-11-19.
[^bl-13]: [JPMorgan Stops AI Agents From Using Customer Credit Cards (PYMNTS)](../sources/bl-13.md). PYMNTS, third-party, retrieved 2026-11-19.
[^pm-34]: [PayPal Agentic Commerce Merchant Virtual Card Terms](../sources/pm-34.md). PayPal, official, retrieved 2026-11-25.
[^sd-02]: [Know Your Human (KYH) for Agentic Commerce - Sardine](../sources/sd-02.md). Sardine, official, retrieved 2026-11-20.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20payments%2Fmerchants-and-outside-agents.md&body=Page%3A%20payments%2Fmerchants-and-outside-agents.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
