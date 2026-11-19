---
type: payment
title: Merchants and outside agents
summary: Some merchants forbid AI agents from buying. eBay, United and Booking.com ban them without permission, and Target allows only a short list of approved agents.
page_status: current
last_verified: '2026-11-19'
---

# Merchants and outside agents

An agent that can pay still needs the merchant to accept it. Some merchants now forbid AI agents in their terms. Each line below comes from the merchant's own terms or help pages.

## The short version

- **eBay** bans buy-for-me agents and LLM-driven bots unless eBay gives prior express permission.[^eb-01]
- **United Airlines** bans the use of AI agents to make, change or service a ticket, or to buy any product, and restricts agents through travel agencies and aggregators too.[^ua-01][^ua-02]
- **Target** allows only agents on its Approved Agents list, currently its own AI Shopping Assistant, OAI, Google and Microsoft, and prohibits all other agentic commerce tools.[^tg-01]
- **Booking.com** bars automated assistants, including AI-powered assistants, from its platform without its prior express written permission, and does not authorize them to make bookings.[^bk-01]
- Payment programs are trying to make agents easier to accept. OpenAI warns that some sites may block agent purchases by accident, and asks merchants to recognize signed agent requests with [Web Bot Auth](../glossary.md#web-bot-auth).[^oa-01]

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

## Why merchants say they restrict agents

- United says agents with account access could expose personal information or make bookings, account changes or use of miles without the customer's approval. It wants standard integrations with privacy, security, authorization and accountability protections first.[^ua-02]
- United also says an agent that checks a passenger in automatically could violate FAA and DOT rules, because check-in requires a person to confirm that bags hold no banned substances.[^ua-02]
- eBay's agreement gives no reason in the cited text.[^eb-01] The cited Booking.com terms give none for their agent rule either.[^bk-01]
- Target's terms give no reason for limiting agents to a list. They say Target may restrict an agent's access for suspected fraud, misuse, policy violations or security concerns, and that it is not responsible for third-party agents' conduct.[^tg-01]

## What do merchants say about agent virtual cards?

When an agent pays through Stripe's [Link wallet](link-wallet-for-agents.md) with a one-time [virtual card](../glossary.md#virtual-card), the merchant is paid by that card, not by the shopper's own. The Wall Street Journal reported on 2026-11-13, citing people familiar with the matter, that merchants are complaining to Visa and Mastercard that the virtual card costs more on average to accept, because it is classified as a commercial card rather than a consumer card. It also reported that the temporary cards have made returns harder to process, according to some merchant executives.[^bl-12][^bl-13] These are third-party reports. How large the extra cost is, and whether Visa or Mastercard have responded, is unknown.

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
[^oa-01]: [Introducing ChatGPT Wallet](../sources/oa-01.md). OpenAI, official, retrieved 2026-11-15.
[^bl-12]: [AI bots are using credit cards. Banks are racing to keep up. (The Wall Street Journal, via Mint)](../sources/bl-12.md). The Wall Street Journal (syndicated on Mint), third-party, retrieved 2026-11-19.
[^bl-13]: [JPMorgan Stops AI Agents From Using Customer Credit Cards (PYMNTS)](../sources/bl-13.md). PYMNTS, third-party, retrieved 2026-11-19.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20payments%2Fmerchants-and-outside-agents.md&body=Page%3A%20payments%2Fmerchants-and-outside-agents.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
