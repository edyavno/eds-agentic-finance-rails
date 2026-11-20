---
type: payment
id: agentcore-payments
title: Amazon Bedrock AgentCore payments
summary: AWS service that lets an agent pay for APIs, MCP servers and content over x402 and MPP within a per-session budget. Since 2026-11-19 it can also pay AWS Marketplace sellers in US dollars on the AWS bill, with no crypto wallet.
page_status: current
last_verified: '2026-11-20'
kind: payment-protocol
operator: Amazon Web Services (AWS)
agent_can: Pay for paid APIs, MCP servers and web content over x402 and the Machine Payments Protocol, through a configured wallet provider, and pay x402-enabled AWS Marketplace sellers per request in US dollars on the AWS bill
user_controls: Each payment session has a budget limit and an expiry, and further payments are denied once either is reached. Developers can also set spending limits and approved sellers with AgentCore policy, and AWS Marketplace purchases appear in AWS CloudTrail and AWS Cost Explorer
mcp_server: unknown
endpoint: unknown
availability: Generally available since August 2026. AWS Marketplace payments are available in all AWS Regions where AgentCore payments is available, and the list of Regions is unknown
field_sources:
  operator:
  - aw-01
  - aw-02
  agent_can:
  - aw-01
  - aw-02
  - aw-03
  user_controls:
  - aw-01
  - aw-02
  - aw-03
  availability:
  - aw-01
  - aw-02
---

# Amazon Bedrock AgentCore payments

Amazon Bedrock AgentCore payments is an AWS service that lets an AI agent pay for paid APIs, [MCP](../glossary.md#mcp) servers and web content. AWS says it became generally available in August 2026, and that agents pay over open protocols like [x402](../glossary.md#x402) and [MPP](../glossary.md#mpp) with payment limits and full observability.[^aw-02]

## What does AgentCore payments do?

- AWS calls it a fully managed service for microtransaction payments, so agents can reach paid APIs, MCP servers and content.[^aw-03]
- It uses x402 and the Machine Payments Protocol (MPP). AWS says both use the HTTP 402 Payment Required status code.[^aw-03]
- AgentCore payments handles the agent side of the exchange: it receives the merchant's payment request, signs the transaction with the configured wallet provider, and returns the payment proof.[^aw-03]
- AWS lists research, financial analysis, browser agents and pay-per-intelligence among its use cases.[^aw-03]

## What can you control?

- **Session budget and expiry.** Each payment session has a configurable budget limit and an expiry time. When the session expires or the budget is reached, further payment requests are denied.[^aw-03]
- **Failed payments.** AWS says that if signing fails after the budget is deducted, the failed payment is not deducted from the budget.[^aw-03]
- **Approved sellers and spending limits.** For AWS Marketplace purchases, AWS says developers can set spending limits and approved sellers using AgentCore policy, and that the session cap is enforced by AgentCore payments so an agent cannot overspend.[^aw-02]
- **Private Marketplace.** If an organization uses Private Marketplace, AWS says agents can only buy the products it allows.[^aw-02]
- **Separate roles.** In AWS's sample setup, the session role can set budgets but cannot pay, and the agent role can pay but cannot create sessions, so the agent cannot raise its own budget.[^aw-02]
- **Audit.** AWS says transactions appear in AWS CloudTrail and AWS Cost Explorer.[^aw-01]

## How does paying AWS Marketplace sellers work?

AWS announced on 2026-11-19 that AWS Marketplace supports agentic payments over x402 through AgentCore payments. Agents can discover and buy select products and pay per request in US dollars. AWS says customers skip per-seller sign-up, and charges settle on their existing AWS bill with no crypto wallet required.[^aw-01]

1. **Quote.** The agent calls the seller's endpoint. The seller answers with HTTP 402 and a signed quote, and AWS Marketplace checks the signature against the seller's registered key.[^aw-02]
2. **Pay.** The agent passes the quote to AgentCore payments, which checks the session budget and returns a payment token. If no budget remains, AWS says the call fails and the developer is not charged.[^aw-02]
3. **Redeem.** The agent retries with the token and gets the content. AWS says payment tokens are valid for about five minutes.[^aw-02]
4. **Settle.** The first purchase from a seller creates an agreement for the AWS account, and later charges are metered against it. AWS says settlement runs asynchronously and shows up on the AWS bill monthly.[^aw-02]

AWS says that at launch the AWS Billing option supports the x402 `exact` scheme, where the seller quotes a fixed price for each request.[^aw-02] In AWS's sample, the default session budget is $0.05 and the per-request cap is $0.02.[^aw-02]

For sellers, AWS says they register with AWS Marketplace, configure agentic payments for their listings and integrate the AWS Marketplace x402 SDK. AWS Marketplace collects the customer payments and pays sellers through the usual seller disbursements.[^aw-01]

## Which wallets does it use?

For payments outside AWS Marketplace, AWS says the service integrates with two wallet providers, CoinbaseCDP and Stripe (Privy), for embedded stablecoin wallet operations. It says API keys and wallet secrets are stored through AgentCore Identity.[^aw-03]

AWS also says AgentCore payments offers a ready-to-use Coinbase x402 Bazaar MCP server that exposes more than 10,000 pay-per-use x402 endpoints through AgentCore Gateway.[^aw-03] Coinbase's own post says it is partnering with AWS to unlock native agent payments on AWS AgentCore.[^cb-12] See [x402](x402.md) and [Coinbase](../providers/coinbase.md).

## What is still unknown?

- The list of AWS Regions where AgentCore payments is available. AWS says only "all AWS Regions where AgentCore payments is available".[^aw-01]
- Pricing for AgentCore payments and any fees on Marketplace purchases. The pages cited here do not give them.
- Which sellers are live beyond the one AWS names, Tavily, in its example.[^aw-02]
- Whether the budget and approved-seller limits apply to wallet-based payments in the same way as to AWS Marketplace purchases. AWS describes the session budget for both, but names approved sellers only for AWS Marketplace.[^aw-02][^aw-03]

[Back to payments](README.md)

## Sources

[^aw-02]: [Enable AI agents to pay for AWS Marketplace x402 products with Amazon Bedrock AgentCore payments](../sources/aw-02.md). Amazon Web Services (AWS Machine Learning Blog), official, retrieved 2026-11-20.
[^aw-03]: [Amazon Bedrock AgentCore payments: Enable secure microtransaction payments for AI agents](../sources/aw-03.md). Amazon Web Services (AgentCore Developer Guide), official, retrieved 2026-11-20.
[^aw-01]: [AWS Marketplace now supports agentic payments with AgentCore](../sources/aw-01.md). Amazon Web Services, official, retrieved 2026-11-20.
[^cb-12]: [System Update: Take control of your money with Coinbase](../sources/cb-12.md). Coinbase, official, retrieved 2026-11-20.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20payments%2Fagentcore-payments.md&body=Page%3A%20payments%2Fagentcore-payments.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
