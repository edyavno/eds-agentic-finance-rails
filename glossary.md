---
type: guide
title: Glossary
summary: Short, plain-English definitions of recurring terms in this wiki, including MCP, OAuth, paper trading, payment tokens, open banking, and related agent-finance vocabulary.
page_status: current
last_verified: '2026-11-19'
---

# Glossary

Short, plain-English definitions of recurring terms in this wiki. These entries describe general concepts, not a particular product. Provider-specific meanings stay on the provider pages.

## 2FA

Two-factor authentication. A second check, besides a password, that a person is who they say they are.

## A2A

Agent2Agent. An open protocol for AI agents to talk to and hand tasks to other agents. AP2 is offered as an extension to it.

## Agent Detection

A service that tells a bank or merchant whether a session is a person or an AI agent, and which AI provider the agent belongs to, by looking at signals such as device, behavior and network. It detects an agent; it does not prove who the agent is.

## Agent skill

A packaged set of instructions, often a SKILL.md file, that an AI agent loads to learn how to use a particular tool or service. A skill teaches the agent; it does not give it any access by itself.

## Agentic commerce

Shopping and paying done by an AI agent on a person's behalf, from finding an item to checking out.

## Agentic Ready

Visa's program for testing agent-initiated payments. Card issuers joined first, and in 2026-11 it opened to merchants, payment providers and acquirers.

## Agentic token

A [payment token](#payment-token) from Visa or Mastercard made for AI agents. It hides the card number and can carry extra data, such as what the shopper wants bought, a spending limit and whether the agent is trusted.

## AI Partition

A separately funded slice of an account reserved for an agent, so the rest of the account stays out of reach.

## Allowlist

A list of apps or clients that are allowed to connect. Anything not on the list is denied.

## API key

A secret string a program uses to prove it is allowed to call a service.

## Approval model

The rule for who or what has to say yes before an agent's order or payment goes through: a person, the provider, limits set in advance, or no one. This wiki sorts brokers into five [approval models](approval-models/README.md).

## Bearer token

A credential sent with a request, usually in an HTTP header, to prove the client is allowed to access a resource.

## CLI

Command-line interface. A program you run by typing commands, rather than clicking in a graphical app.

## Client ID Metadata Documents

A way for an app to describe itself with a document at a URL, so a server can identify the app during [OAuth](#oauth) sign-in.

## Connector

An add-on that links an AI app to an outside service, so the app can read from it or act in it. Apps call this a connector, a plugin or an integration, and where you add one differs by app.

## Data aggregator

A company that connects apps to a person's bank and card accounts, with their permission, and passes along data such as balances and transactions.

## Data Transparency Messaging

A step in Plaid's Link screen that tells a person which types of data an app is asking for and why, before they agree. Plaid introduced it to help its customers comply with the US data-rights rule often called 1033.

## Dead man's switch

A timer that cancels all open orders automatically unless the program that set it keeps checking in. If the agent or its computer stops, the orders do not stay live.

## Dynamic Client Registration

A way for an app to register itself with an [OAuth](#oauth) server as part of connecting, instead of being set up in advance by a person.

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

## llms.txt

A machine-readable index of pages, published so AI agents can find and read a site's documentation.

## Mandates

A record of what a person authorized an agent to do, used so later actions can be checked against that authorization.

## MCP

Model Context Protocol. A standard way for an AI application to connect to a tool or service, such as a broker.

## Merchant of record

The business that legally sells to the buyer and is named on the charge. It handles the payment, taxes, refunds and disputes for that sale.

## Network token

A [payment token](#payment-token) issued by a card network, such as Visa or Mastercard, in place of the card number. The merchant charges the token, and the network maps it to the real card.

## OAuth

A standard sign-in method that lets a person grant an app limited access to an account, without sharing their password with that app.

## Open banking

Sharing bank data with other apps through approved, permissioned connections, instead of handing over a bank password.

## OpenAPI

A standard way to describe a web API, so people and programs can see what requests it accepts.

## Paper trading

Practice trading with simulated money. Also called paper mode.

## Passkey

A sign-in method that uses your device's fingerprint, face scan or PIN instead of a password. It is tied to your device and the site you made it for, so it cannot be typed into a fake page.

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

## Sandbox

A test environment that is not the live production system.

## Scopes

Named permissions in an [OAuth](#oauth) sign-in request, which limit what the app is allowed to do.

## Stablecoin

A digital token designed to hold a steady value, usually pegged to a currency such as the US dollar.

## Stdio

Standard input and output. A local program can talk to a client through these streams instead of over the internet.

## Stored-value account

A balance held for you by a payments company, usually a licensed money transmitter, with a partner bank holding the cash. It works like a bank account in the app but is not itself a bank account. X Money is described this way in a US regulator's database.

## UAT

User acceptance testing. A test environment used to try a system before using the live one. See also [sandbox](#sandbox).

## Verifiable Intent

Mastercard's way of tying a customer's approval of a specific purchase to the payment, so the payment can be checked against what the customer approved.

## Virtual card

A card number that exists only online, often created for one purpose and with its own limits.

## Web Bot Auth

A draft web standard for bots and agents to sign their web requests, so a website can check which agent is calling. See [Agent identity](rails/agent-identity.md).

## x402

A protocol for paying for a resource as part of a web request, often used so an agent can pay for data or a service.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20glossary.md&body=Page%3A%20glossary.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
