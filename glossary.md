---
type: guide
title: Glossary
summary: Short, plain-English definitions of recurring terms in this wiki, including MCP, OAuth, paper trading, payment tokens, open banking, and related agent-finance vocabulary.
page_status: current
last_verified: '2026-11-27'
---

# Glossary

Short, plain-English definitions of recurring terms in this wiki. These entries describe general concepts, not a particular product. Provider-specific meanings stay on the provider pages.

## 2FA

Two-factor authentication. A second check, besides a password, that a person is who they say they are.

## A2A

Agent2Agent. An open protocol for AI agents to talk to and hand tasks to other agents. AP2 is offered as an extension to it.

## Account-to-account payment

A bank payment from one account to another, rather than a card. GoCardless uses the term for Direct Debit and open-banking payments set up by an agent.[^gc-02][^gc-03]

## Agent Detection

A service that tells a bank or merchant whether a session is a person or an AI agent, and which AI provider the agent belongs to, by looking at signals such as device, behavior and network. It detects an agent; it does not prove who the agent is.

## Agent Gateway (Walmart)

Walmart's connection point for shopping agents. An agent, such as Meta's [Muse](personal-money/meta-muse.md), passes a shopping list to Walmart through the gateway rather than browsing the site as a person would.[^wm-01][^wm-02]

## Agent Profile

Walmart's term for the settings a shopper creates in their Walmart account the first time an agent adds an item to the cart. The shopper can set a spending limit, approve purchases, check which purchases the agent made, and delete the profile.[^wm-01][^wm-02]

## Agent skill

A packaged set of instructions, often a SKILL.md file, that an AI agent loads to learn how to use a particular tool or service. A skill teaches the agent; it does not give it any access by itself.

## Agentic commerce

Shopping and paying done by an AI agent on a person's behalf, from finding an item to checking out.

## Agentic Mobile Protocol (AMP)

An open payment protocol built by Ant International so AI agents can execute payments through digital wallets, super apps, smart devices and other mobile interfaces. Ant International says it launched in April 2026.[^nt-01] See [Agent payments](rails/agent-payments.md#is-there-an-agent-payment-protocol-for-mobile-wallets).

## Agentic Negotiation Protocol (ANP)

BNY's framework and control layer for authorized agents from different organizations to negotiate with each other. BNY says it is patent pending, and that it verifies the participants and lets their agents exchange offers and counteroffers.[^bn-01] See [Institutional markets](rails/institutional-markets.md).

## Agentic Ready

Visa's program for testing agent-initiated payments. Card issuers joined first, and in 2026-11 it opened to merchants, payment providers and acquirers.

## Agentic token

A [payment token](#payment-token) from Visa or Mastercard made for AI agents. It hides the card number and can carry extra data, such as what the shopper wants bought, a spending limit and whether the agent is trusted.

## Agentic VC

PayPal's term for a one-time [virtual card](#virtual-card) it uses to settle a PayPal payment to a merchant when a buyer pays with PayPal through an agent commerce service. The merchant must show the payment method as "PayPal", and these payments are not eligible under PayPal's Seller Protection program.[^pm-34]

## AI Partition

A separately funded slice of an account reserved for an agent, so the rest of the account stays out of reach.

## Allowlist

A list of apps or clients that are allowed to connect. Anything not on the list is denied.

## AP2

The Agent Payments Protocol, an open protocol that carries signed proof of what the user authorized. [Tasks in Gemini](personal-money/gemini-tasks.md) says it uses AP2 for purchases.[^gg-04] See [AP2](payments/ap2.md).

## API key

A secret string a program uses to prove it is allowed to call a service.

## Approval model

The rule for who or what has to say yes before an agent's order or payment goes through: a person, the provider, limits set in advance, or no one. This wiki sorts brokers into five [approval models](approval-models/README.md).

## BBPS

India's Bharat Bill Payment System, the bill payment network that connects most Indian billers. [Cashfree Wallet](payments/cashfree-wallet.md) pays everyday bills through BBPS.[^cf-02]

## Bearer token

A credential sent with a request, usually in an HTTP header, to prove the client is allowed to access a resource.

## BLIK

A Polish payment method confirmed with a code in the customer's banking app. [paymove](payments/paymove.md) uses a fresh BLIK transaction for each agent payment.[^pv-01]

## BOLT11

A standard format for a Bitcoin [Lightning](#lightning) invoice. In the x402 Lightning scheme, the client pays a fresh BOLT11 invoice and returns the payment preimage.[^xf-01]

## CLI

Command-line interface. A program you run by typing commands, rather than clicking in a graphical app.

## Client ID Metadata Documents

A way for an app to describe itself with a document at a URL, so a server can identify the app during [OAuth](#oauth) sign-in.

## Connector

An add-on that links an AI app to an outside service, so the app can read from it or act in it. Apps call this a connector, a plugin or an integration, and where you add one differs by app.

## Consumer Finance AI Standard

A Consumer Reports standard for testing whether an AI system gives consumers sound, unbiased financial guidance. Affirm and Consumer Reports used it to score tests of their Payment Choice Framework.[^cr-01]

## Data aggregator

A company that connects apps to a person's bank and card accounts, with their permission, and passes along data such as balances and transactions.

## Data Transparency Messaging

A step in Plaid's Link screen that tells a person which types of data an app is asking for and why, before they agree. Plaid introduced it to help its customers comply with the US data-rights rule often called 1033.

## Dead man's switch

A timer that cancels all open orders automatically unless the program that set it keeps checking in. If the agent or its computer stops, the orders do not stay live.

## Direct Debit

A bank payment instruction that lets a business collect money from a customer's account, often on a recurring schedule. [GoCardless](payments/gocardless.md) lets an agent set up a Direct Debit mandate through a hosted MCP server, with the payer confirming in a secure form.[^gc-02]

## Dynamic Client Registration

A way for an app to register itself with an [OAuth](#oauth) server as part of connecting, instead of being set up in advance by a person.

## EIP-712

A way for an Ethereum wallet to sign a structured message, rather than a raw transaction. [Aave MCP](payments/aave-mcp.md) can return EIP-712 typed data for the user to sign.[^aa-01]

## Elicitation

An MCP feature that lets a server stop and ask the person a question through the AI client, such as "confirm this order". The model cannot answer for the person.

## Environment variables

Named settings stored in the environment of a running program, often used for credentials, endpoints, or limits.

## Facilitator

In [x402](#x402), a service that checks a payment and settles it on the payment network, so the website selling the resource does not have to do that itself.

## GenAI

Generative AI. Software that produces text, code, or other content in response to a prompt.

## Greeks

Standard measures of how an option's price may change as things such as the underlying price or time to expiration change.

## Human in the loop

A design where a person reviews or approves an agent's action before it takes effect, instead of letting the agent act alone. See [Build it](build/human-in-the-loop.md) for patterns.

## Item

In Plaid, one login at a financial institution. When you link a bank through Plaid, the app gets an Item with its own identifier and access token. Linking the same account twice makes two Items.

## Know Your Agent (KYA)

A way for a bank or merchant to learn who an agent is and whom it represents, what authority and mandate it has, and what assurance exists about it. The Monetary Authority of Singapore says it will facilitate the development of a Know Your Agent protocol for trusted information exchange between customer agents and financial institutions. Its text and date are unknown.[^ma-01] NETS and Ant International say they will explore interoperability between Know-Your-Agent frameworks.[^nt-01] See [Agent identity](rails/agent-identity.md#what-is-know-your-agent).

## Know Your Human (KYH)

Sardine's name for a way to tie the customer's own device to an agent's session, so a merchant can see signals from the person behind the agent. It is Sardine's own product, and the claims about it are Sardine's.[^sd-01] See [Merchants and outside agents](payments/merchants-and-outside-agents.md#what-does-sardine-say-about-agent-checkouts).

## LLM client

The AI app or tool a person uses to talk to a large language model, such as a chat app or a command-line tool. A service that connects to many of them can report how much activity comes from each.

## llms.txt

A machine-readable index of pages, published so AI agents can find and read a site's documentation.

## Lightning

Bitcoin's network for fast payments, settled with invoices rather than on-chain transactions. An x402 scheme uses Lightning under the `lnbtc` namespace.[^xf-01]

## Mandates

A record of what a person authorized an agent to do, used so later actions can be checked against that authorization.

## MCP

Model Context Protocol. A standard way for an AI application to connect to a tool or service, such as a broker.

## Merchant of record

The business that legally sells to the buyer and is named on the charge. It handles the payment, taxes, refunds and disputes for that sale.

## MPP

Machine Payments Protocol. A way for an agent to pay for a web request using the HTTP 402 Payment Required status code, as [x402](#x402) does. AWS's AgentCore payments guide supports both.[^aw-03]

## Network token

A [payment token](#payment-token) issued by a card network, such as Visa or Mastercard, in place of the card number. The merchant charges the token, and the network maps it to the real card.

## Notional volume

The total dollar value of the trades made, counted at the trade price. It measures how much money was traded, not how many trades there were or how much was gained or lost.

## OAuth

A standard sign-in method that lets a person grant an app limited access to an account, without sharing their password with that app.

## Open banking

Sharing bank data with other apps through approved, permissioned connections, instead of handing over a bank password.

## OpenAPI

A standard way to describe a web API, so people and programs can see what requests it accepts.

## OUSD

A dollar [stablecoin](#stablecoin) used on the Tempo network. [Visa CLI](payments/visa-cli.md) agents can pay HTTP 402 requests in OUSD, within limits the owner set.[^pm-27]

## Paper trading

Practice trading with simulated money. Also called paper mode.

## Passkey

A sign-in method that uses your device's fingerprint, face scan or PIN instead of a password. It is tied to your device and the site you made it for, so it cannot be typed into a fake page.

## Payment handler

A published way for a payment provider to plug into an agent checkout. Adyen built its Klarna integration on Klarna's open payment-handler specification. The announcement does not link that specification, so its URL is unknown.[^pm-29]

## Payment token

A stand-in for a card number or payment method that works only within set limits, such as one seller, a maximum amount or an expiry date. The real card number stays hidden.

## PKCE

Proof Key for Code Exchange. An extra check in an [OAuth](#oauth) sign-in flow that helps make sure the same app that started the sign-in is the one that finishes it.

## Plaid Link

The screen, run by Plaid, where a person chooses their bank, signs in and agrees to share data with an app. The app never sees the bank password. In Plaid's docs it is the only way to connect accounts in production.

## Plaid Portal

Plaid's tool for people to see which apps they connected through Plaid, disconnect them and ask Plaid to delete their data. It is at my.plaid.com.

## Preflight

A preview of an order, including estimated cost or risk, shown before the order is sent.

## Protected-resource metadata

A published description of how a server expects a client to sign in, including the sign-in address and the [scopes](#scopes) it offers.

## Rails

The shared plumbing that agent access to money runs on, separate from any single provider: how agents connect, sign in, prove who they are, carry a person's consent and pay. See [Rails](rails/README.md).

## Refresh token

A credential an app can use to get a new access token without asking the person to sign in again.

## SAFR

Safeguards for Agentic Finance at Runtime. Work published by the Monetary Authority of Singapore. It says agents need bounded autonomy, clearly established identity and authority, clear and specific mandates, and controls proportionate to authority. A new phase will facilitate a [Know Your Agent](#know-your-agent-kya) protocol.[^ma-01]

## Sandbox

A test environment that is not the live production system.

## Scopes

Named permissions in an [OAuth](#oauth) sign-in request, which limit what the app is allowed to do.

## Seven-day rolling average

A way of smoothing a daily series by taking the average of the last seven days at each point, so a single day's jump does not dominate the picture. A seven-day moving average is the same idea.

## Stablecoin

A digital token designed to hold a steady value, usually pegged to a currency such as the US dollar.

## Stdio

Standard input and output. A local program can talk to a client through these streams instead of over the internet.

## Stored-value account

A balance held for you by a payments company, usually a licensed money transmitter, with a partner bank holding the cash. It works like a bank account in the app but is not itself a bank account. X Money is described this way in a US regulator's database.

## Tasks in Gemini

A mode in Google's Gemini app that can carry out tasks, including shopping and checkout with Google Pay. Google says it uses [AP2](#ap2) for purchases, and you can set a hard spending cap.[^gg-04] See [Tasks in Gemini](personal-money/gemini-tasks.md).

## Tempo

A blockchain network that carries dollar [stablecoin](#stablecoin) payments, including [OUSD](#ousd). [Visa CLI](payments/visa-cli.md) uses Tempo for agent payments from the owner's wallet.[^pm-27]

## Trusted Agent Protocol (TAP)

A Visa protocol that lets a merchant check an agent's identity using HTTP Message Signatures. [Visa CLI](payments/visa-cli.md) signs requests under TAP and lists new agents in the [Visa Agent Directory](#visa-agent-directory).[^pm-03][^pm-27]

## UAT

User acceptance testing. A test environment used to try a system before using the live one. See also [sandbox](#sandbox).

## Verifiable Intent

Mastercard's way of tying a customer's approval of a specific purchase to the payment, so the payment can be checked against what the customer approved.

## Visa Agent Directory

Visa's public registry of agents whose signing keys have been checked. [Visa CLI](payments/visa-cli.md) has listed newly connected agents there since 18 November 2026. Agents connected before then remain in a sandbox directory.[^pm-28]

## Virtual card

A card number that exists only online, often created for one purpose and with its own limits.

## Web Bot Auth

A draft web standard for bots and agents to sign their web requests, so a website can check which agent is calling. See [Agent identity](rails/agent-identity.md).

## x402

A protocol for paying for a resource as part of a web request, often used so an agent can pay for data or a service.

## Sources

[^gc-02]: [What we learned building the UK’s first agentic bank payment](sources/gc-02.md). GoCardless, official, retrieved 2026-11-27.
[^gc-03]: [How we collected the UK’s first agentic account-to-account payment with Trussell](sources/gc-03.md). GoCardless, official, retrieved 2026-11-27.
[^wm-01]: [Walmart’s Black Friday Deals Continue. Meta’s Muse Can Now Shop Them, Too.](sources/wm-01.md). Walmart, official, retrieved 2026-11-25.
[^wm-02]: [Making It Possible for Agents to Shop on Behalf of Customers](sources/wm-02.md). Walmart, official, retrieved 2026-11-25.
[^nt-01]: [NETS and Ant International Deepen Partnership to Empower Singapore’s Businesses for a Future in Agentic Commerce with Agentic Mobile Protocol](sources/nt-01.md). NETS (Network for Electronic Transfers), official, retrieved 2026-11-20.
[^bn-01]: [BNY and Microsoft Complete First Agentic Negotiation of a U.S. Treasury Trade](sources/bn-01.md). BNY, official, retrieved 2026-11-20.
[^pm-34]: [PayPal Agentic Commerce Merchant Virtual Card Terms](sources/pm-34.md). PayPal, official, retrieved 2026-11-25.
[^gg-04]: [Put Gemini to work for you](sources/gg-04.md). Google, official, retrieved 2026-11-27.
[^cf-02]: [AgentPay MCP](sources/cf-02.md). Cashfree, official, retrieved 2026-11-25.
[^pv-01]: [AI Payments](sources/pv-01.md). paymove, official, retrieved 2026-11-27.
[^xf-01]: [Scheme: exact on Bitcoin Lightning (lnbtc)](sources/xf-01.md). x402 Foundation, official, retrieved 2026-11-27.
[^cr-01]: [A Consumer-First Standard for AI Payments (Affirm and Consumer Reports case study)](sources/cr-01.md). Affirm and Consumer Reports, official, retrieved 2026-11-23.
[^aa-01]: [Aave MCP](sources/aa-01.md). Aave, official, retrieved 2026-11-23.
[^ma-01]: [Keynote address by the Managing Director of the Monetary Authority of Singapore at the Singapore FinTech Festival 2026](sources/ma-01.md). Monetary Authority of Singapore, official, retrieved 2026-11-20.
[^sd-01]: [Know Your Human (KYH): Fraud prevention for agentic commerce](sources/sd-01.md). Sardine, official, retrieved 2026-11-20.
[^aw-03]: [Amazon Bedrock AgentCore payments: Enable secure microtransaction payments for AI agents](sources/aw-03.md). Amazon Web Services (AgentCore Developer Guide), official, retrieved 2026-11-20.
[^pm-27]: [Visa CLI docs: Introduction](sources/pm-27.md). Visa CLI docs (Visa Crypto Labs), official, retrieved 2026-11-23.
[^pm-29]: [Adyen Merchants Can Now Offer Klarna in AI Agent Checkout](sources/pm-29.md). Klarna and Adyen (Business Wire release on Klarna's investor site), official, retrieved 2026-11-23.
[^pm-03]: [GitHub - visa/trusted-agent-protocol: Establishing a universal standard of trust between AI agents and merchants for the next phase of agentic commerc](sources/pm-03.md). Visa (GitHub), official, retrieved 2026-11-12.
[^pm-28]: [Visa CLI docs: What's live today](sources/pm-28.md). Visa CLI docs (Visa Crypto Labs), official, retrieved 2026-11-23.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20glossary.md&body=Page%3A%20glossary.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
