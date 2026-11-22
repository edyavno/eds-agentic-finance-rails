---
title: Trading
summary: Which brokers let AI agents trade and who approves each order, plus key fields for every provider. Every value is sourced or says unknown.
page_status: current
last_verified: '2026-11-21'
---

# Trading

## Which brokers let AI agents trade, and who approves the order?

All eight providers here publish an official [MCP](glossary.md#mcp) server for AI agents.[^al-02][^cb-01][^ib-01][^kr-01][^pu-01][^rh-01][^sc-01][^wb-02] The providers differ on who says yes before an order reaches the market.

- [Robinhood:](providers/robinhood.md) The agent trades only in a separate account you fund. Per-order approval is an optional toggle, off by default for MCP accounts.[^rh-01][^rh-04]
- [Coinbase:](providers/coinbase.md) The agent trades in the portfolios you pick when you sign in, which can include your main account. You can limit it to a dedicated portfolio.[^cb-03][^cb-07]
- [Webull:](providers/webull.md) With the hosted Cloud MCP, you confirm each trade in the Webull app. The local OpenAPI MCP places orders directly, with limits you set.[^wb-07][^wb-03]
- [Interactive Brokers:](providers/interactive-brokers.md) By default, the AI drafts instructions you review and submit. Eligible accounts can turn on Autonomous Trading inside a separately funded [AI Partition](glossary.md#ai-partition).[^ib-01][^ib-07][^ib-06]
- [Alpaca:](providers/alpaca.md) No broker-side approval is documented, so approval has to live in your agent or client.[^al-05][^al-03] [Paper trading](glossary.md#paper-trading) is built in.[^al-01][^al-03]
- [Public:](providers/public.md) Trades through its hosted MCP are real orders, with no paper mode, and Public says to review the preflight details before confirming. Whether the hosted server enforces that confirmation is unknown. Dedicated accounts for MCP connections are optional.[^pu-02][^pu-06][^pu-01]
- [Scalable Capital:](providers/scalable-capital.md) Orders need the Full access level. A preview does not place an order, and the agent cannot place one without your renewed, explicit confirmation.[^sc-03]
- [Kraken:](providers/kraken.md) The MCP server runs locally on your machine and asks you to approve each order, withdrawal or transfer, unless you start it with `--allow-dangerous`.[^kr-01]

Who approves is explained in [approval models](approval-models/README.md). [Compare the launch brokers side by side](comparisons/launch-brokers.md), or see the [rails](rails/README.md) underneath.

## Compare every broker

<a id="broker-fields"></a>

<figure class="afr-cheatsheet-visual afr-cheatsheet-visual--desktop">
<svg role="img" viewBox="0 0 800 488" xmlns="http://www.w3.org/2000/svg" aria-labelledby="trading-appr-d-title trading-appr-d-desc">
<title id="trading-appr-d-title">Who approves an order, by broker</title>
<desc id="trading-appr-d-desc">Brokers grouped by who approves an order, using each broker's approval-model field. Per-order confirm by you — Kraken, Public, Robinhood, Scalable Capital, Webull; Separate or dedicated account — Coinbase, Public, Robinhood; Draft, then you submit — Interactive Brokers; No broker-side approval — Alpaca, Webull. A numbered mark means the broker appears in more than one group.</desc>
<rect width="800" height="488" fill="var(--light)"/>
<rect x="16" y="16" width="184" height="48" rx="10" fill="var(--light)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="108.0" y="36" text-anchor="middle" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan x="108.0" y="36">Per-order confirm</tspan><tspan x="108.0" dy="14">by you</tspan></text>
<rect x="16" y="74" width="184" height="62" rx="10" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="28" y="96" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan x="28" y="96">Kraken</tspan></text>
<circle cx="184" cy="90" r="5.5" fill="var(--secondary)"/>
<rect x="16" y="144" width="184" height="62" rx="10" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="28" y="166" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan x="28" y="166">Public</tspan></text>
<circle cx="184" cy="160" r="5.5" fill="var(--light)" stroke="var(--dark)" stroke-width="1.5"/>
<circle cx="162" cy="160" r="8" fill="var(--light)" stroke="var(--dark)" stroke-width="1.5"/><text x="162" y="163.5" text-anchor="middle" fill="var(--dark)" font-size="10" font-family="system-ui, -apple-system, sans-serif" font-weight="700">1</text>
<rect x="16" y="214" width="184" height="62" rx="10" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="28" y="236" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan x="28" y="236">Robinhood</tspan></text>
<circle cx="184" cy="230" r="5.5" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/><text x="184" y="233.5" text-anchor="middle" fill="var(--darkgray)" font-size="8" font-family="system-ui, -apple-system, sans-serif" font-weight="700">?</text>
<circle cx="162" cy="230" r="8" fill="var(--light)" stroke="var(--dark)" stroke-width="1.5"/><text x="162" y="233.5" text-anchor="middle" fill="var(--dark)" font-size="10" font-family="system-ui, -apple-system, sans-serif" font-weight="700">2</text>
<rect x="16" y="284" width="184" height="62" rx="10" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="28" y="306" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan x="28" y="306">Scalable Capital</tspan></text>
<circle cx="184" cy="300" r="5.5" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/><text x="184" y="303.5" text-anchor="middle" fill="var(--darkgray)" font-size="8" font-family="system-ui, -apple-system, sans-serif" font-weight="700">?</text>
<rect x="16" y="354" width="184" height="62" rx="10" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="28" y="376" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan x="28" y="376">Webull</tspan></text>
<circle cx="184" cy="370" r="5.5" fill="var(--secondary)"/>
<circle cx="162" cy="370" r="8" fill="var(--light)" stroke="var(--dark)" stroke-width="1.5"/><text x="162" y="373.5" text-anchor="middle" fill="var(--dark)" font-size="10" font-family="system-ui, -apple-system, sans-serif" font-weight="700">3</text>
<rect x="212" y="16" width="184" height="48" rx="10" fill="var(--light)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="304.0" y="36" text-anchor="middle" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan x="304.0" y="36">Separate or</tspan><tspan x="304.0" dy="14">dedicated account</tspan></text>
<rect x="212" y="74" width="184" height="62" rx="10" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="224" y="96" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan x="224" y="96">Coinbase</tspan></text>
<circle cx="380" cy="90" r="5.5" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/><text x="380" y="93.5" text-anchor="middle" fill="var(--darkgray)" font-size="8" font-family="system-ui, -apple-system, sans-serif" font-weight="700">?</text>
<rect x="212" y="144" width="184" height="62" rx="10" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="224" y="166" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan x="224" y="166">Public</tspan></text>
<circle cx="380" cy="160" r="5.5" fill="var(--light)" stroke="var(--dark)" stroke-width="1.5"/>
<circle cx="358" cy="160" r="8" fill="var(--light)" stroke="var(--dark)" stroke-width="1.5"/><text x="358" y="163.5" text-anchor="middle" fill="var(--dark)" font-size="10" font-family="system-ui, -apple-system, sans-serif" font-weight="700">1</text>
<rect x="212" y="214" width="184" height="62" rx="10" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="224" y="236" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan x="224" y="236">Robinhood</tspan></text>
<circle cx="380" cy="230" r="5.5" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/><text x="380" y="233.5" text-anchor="middle" fill="var(--darkgray)" font-size="8" font-family="system-ui, -apple-system, sans-serif" font-weight="700">?</text>
<circle cx="358" cy="230" r="8" fill="var(--light)" stroke="var(--dark)" stroke-width="1.5"/><text x="358" y="233.5" text-anchor="middle" fill="var(--dark)" font-size="10" font-family="system-ui, -apple-system, sans-serif" font-weight="700">2</text>
<rect x="408" y="16" width="184" height="48" rx="10" fill="var(--light)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="500.0" y="36" text-anchor="middle" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan x="500.0" y="36">Draft, then you</tspan><tspan x="500.0" dy="14">submit</tspan></text>
<rect x="408" y="74" width="184" height="62" rx="10" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="420" y="92" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan x="420" y="92">Interactive</tspan><tspan x="420" dy="14">Brokers</tspan></text>
<text x="420" y="122" text-anchor="start" fill="var(--darkgray)" font-size="10" font-family="system-ui, -apple-system, sans-serif" font-weight="500">also AI Partition</text>
<circle cx="576" cy="90" r="5.5" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/><text x="576" y="93.5" text-anchor="middle" fill="var(--darkgray)" font-size="8" font-family="system-ui, -apple-system, sans-serif" font-weight="700">?</text>
<rect x="604" y="16" width="184" height="48" rx="10" fill="var(--light)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="696.0" y="36" text-anchor="middle" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan x="696.0" y="36">No broker-side</tspan><tspan x="696.0" dy="14">approval</tspan></text>
<rect x="604" y="74" width="184" height="62" rx="10" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="616" y="96" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan x="616" y="96">Alpaca</tspan></text>
<circle cx="772" cy="90" r="5.5" fill="var(--secondary)"/>
<rect x="604" y="144" width="184" height="62" rx="10" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="616" y="166" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan x="616" y="166">Webull</tspan></text>
<text x="616" y="192" text-anchor="start" fill="var(--darkgray)" font-size="10" font-family="system-ui, -apple-system, sans-serif" font-weight="500">local OpenAPI</text>
<circle cx="772" cy="160" r="5.5" fill="var(--secondary)"/>
<circle cx="750" cy="160" r="8" fill="var(--light)" stroke="var(--dark)" stroke-width="1.5"/><text x="750" y="163.5" text-anchor="middle" fill="var(--dark)" font-size="10" font-family="system-ui, -apple-system, sans-serif" font-weight="700">3</text>
<circle cx="16" cy="438" r="5.5" fill="var(--secondary)"/>
<text x="26" y="442" text-anchor="start" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif">Paper: yes</text>
<circle cx="134" cy="438" r="5.5" fill="var(--light)" stroke="var(--dark)" stroke-width="1.5"/>
<text x="144" y="442" text-anchor="start" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif">Paper: no</text>
<circle cx="252" cy="438" r="5.5" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/><text x="252" y="441.5" text-anchor="middle" fill="var(--darkgray)" font-size="8" font-family="system-ui, -apple-system, sans-serif" font-weight="700">?</text>
<text x="262" y="442" text-anchor="start" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif">Paper: unknown</text>
<text x="16" y="460" text-anchor="start" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif">A numbered mark means the broker appears in more than one group.</text>
</svg>
<figcaption>Brokers are grouped by the approval models on their pages. A numbered mark means the broker appears in more than one group. Paper trading is marked yes, no, or unknown.</figcaption>
</figure>

<figure class="afr-cheatsheet-visual afr-cheatsheet-visual--mobile">
<svg role="img" viewBox="0 0 360 1058" xmlns="http://www.w3.org/2000/svg" aria-labelledby="trading-appr-m-title trading-appr-m-desc">
<title id="trading-appr-m-title">Who approves an order, by broker</title>
<desc id="trading-appr-m-desc">Brokers grouped by who approves an order, using each broker's approval-model field. Per-order confirm by you — Kraken, Public, Robinhood, Scalable Capital, Webull; Separate or dedicated account — Coinbase, Public, Robinhood; Draft, then you submit — Interactive Brokers; No broker-side approval — Alpaca, Webull. A numbered mark means the broker appears in more than one group.</desc>
<rect width="360" height="1058" fill="var(--light)"/>
<rect x="16" y="16" width="328" height="36" rx="10" fill="var(--light)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="180" y="39" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">Per-order confirm by you</text>
<rect x="16" y="60" width="328" height="62" rx="10" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="28" y="82" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan x="28" y="82">Kraken</tspan></text>
<circle cx="328" cy="76" r="5.5" fill="var(--secondary)"/>
<rect x="16" y="130" width="328" height="62" rx="10" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="28" y="152" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan x="28" y="152">Public</tspan></text>
<circle cx="328" cy="146" r="5.5" fill="var(--light)" stroke="var(--dark)" stroke-width="1.5"/>
<circle cx="306" cy="146" r="8" fill="var(--light)" stroke="var(--dark)" stroke-width="1.5"/><text x="306" y="149.5" text-anchor="middle" fill="var(--dark)" font-size="10" font-family="system-ui, -apple-system, sans-serif" font-weight="700">1</text>
<rect x="16" y="200" width="328" height="62" rx="10" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="28" y="222" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan x="28" y="222">Robinhood</tspan></text>
<circle cx="328" cy="216" r="5.5" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/><text x="328" y="219.5" text-anchor="middle" fill="var(--darkgray)" font-size="8" font-family="system-ui, -apple-system, sans-serif" font-weight="700">?</text>
<circle cx="306" cy="216" r="8" fill="var(--light)" stroke="var(--dark)" stroke-width="1.5"/><text x="306" y="219.5" text-anchor="middle" fill="var(--dark)" font-size="10" font-family="system-ui, -apple-system, sans-serif" font-weight="700">2</text>
<rect x="16" y="270" width="328" height="62" rx="10" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="28" y="292" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan x="28" y="292">Scalable Capital</tspan></text>
<circle cx="328" cy="286" r="5.5" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/><text x="328" y="289.5" text-anchor="middle" fill="var(--darkgray)" font-size="8" font-family="system-ui, -apple-system, sans-serif" font-weight="700">?</text>
<rect x="16" y="340" width="328" height="62" rx="10" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="28" y="362" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan x="28" y="362">Webull</tspan></text>
<circle cx="328" cy="356" r="5.5" fill="var(--secondary)"/>
<circle cx="306" cy="356" r="8" fill="var(--light)" stroke="var(--dark)" stroke-width="1.5"/><text x="306" y="359.5" text-anchor="middle" fill="var(--dark)" font-size="10" font-family="system-ui, -apple-system, sans-serif" font-weight="700">3</text>
<rect x="16" y="418" width="328" height="36" rx="10" fill="var(--light)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="180" y="441" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">Separate or dedicated account</text>
<rect x="16" y="462" width="328" height="62" rx="10" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="28" y="484" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan x="28" y="484">Coinbase</tspan></text>
<circle cx="328" cy="478" r="5.5" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/><text x="328" y="481.5" text-anchor="middle" fill="var(--darkgray)" font-size="8" font-family="system-ui, -apple-system, sans-serif" font-weight="700">?</text>
<rect x="16" y="532" width="328" height="62" rx="10" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="28" y="554" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan x="28" y="554">Public</tspan></text>
<circle cx="328" cy="548" r="5.5" fill="var(--light)" stroke="var(--dark)" stroke-width="1.5"/>
<circle cx="306" cy="548" r="8" fill="var(--light)" stroke="var(--dark)" stroke-width="1.5"/><text x="306" y="551.5" text-anchor="middle" fill="var(--dark)" font-size="10" font-family="system-ui, -apple-system, sans-serif" font-weight="700">1</text>
<rect x="16" y="602" width="328" height="62" rx="10" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="28" y="624" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan x="28" y="624">Robinhood</tspan></text>
<circle cx="328" cy="618" r="5.5" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/><text x="328" y="621.5" text-anchor="middle" fill="var(--darkgray)" font-size="8" font-family="system-ui, -apple-system, sans-serif" font-weight="700">?</text>
<circle cx="306" cy="618" r="8" fill="var(--light)" stroke="var(--dark)" stroke-width="1.5"/><text x="306" y="621.5" text-anchor="middle" fill="var(--dark)" font-size="10" font-family="system-ui, -apple-system, sans-serif" font-weight="700">2</text>
<rect x="16" y="680" width="328" height="36" rx="10" fill="var(--light)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="180" y="703" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">Draft, then you submit</text>
<rect x="16" y="724" width="328" height="62" rx="10" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="28" y="746" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan x="28" y="746">Interactive Brokers</tspan></text>
<text x="28" y="772" text-anchor="start" fill="var(--darkgray)" font-size="10" font-family="system-ui, -apple-system, sans-serif" font-weight="500">also AI Partition</text>
<circle cx="328" cy="740" r="5.5" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/><text x="328" y="743.5" text-anchor="middle" fill="var(--darkgray)" font-size="8" font-family="system-ui, -apple-system, sans-serif" font-weight="700">?</text>
<rect x="16" y="802" width="328" height="36" rx="10" fill="var(--light)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="180" y="825" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">No broker-side approval</text>
<rect x="16" y="846" width="328" height="62" rx="10" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="28" y="868" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan x="28" y="868">Alpaca</tspan></text>
<circle cx="328" cy="862" r="5.5" fill="var(--secondary)"/>
<rect x="16" y="916" width="328" height="62" rx="10" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="28" y="938" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600"><tspan x="28" y="938">Webull</tspan></text>
<text x="28" y="964" text-anchor="start" fill="var(--darkgray)" font-size="10" font-family="system-ui, -apple-system, sans-serif" font-weight="500">local OpenAPI</text>
<circle cx="328" cy="932" r="5.5" fill="var(--secondary)"/>
<circle cx="306" cy="932" r="8" fill="var(--light)" stroke="var(--dark)" stroke-width="1.5"/><text x="306" y="935.5" text-anchor="middle" fill="var(--dark)" font-size="10" font-family="system-ui, -apple-system, sans-serif" font-weight="700">3</text>
<circle cx="16" cy="1008" r="5.5" fill="var(--secondary)"/>
<text x="26" y="1012" text-anchor="start" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif">Paper: yes</text>
<circle cx="134" cy="1008" r="5.5" fill="var(--light)" stroke="var(--dark)" stroke-width="1.5"/>
<text x="144" y="1012" text-anchor="start" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif">Paper: no</text>
<circle cx="252" cy="1008" r="5.5" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/><text x="252" y="1011.5" text-anchor="middle" fill="var(--darkgray)" font-size="8" font-family="system-ui, -apple-system, sans-serif" font-weight="700">?</text>
<text x="262" y="1012" text-anchor="start" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif">Paper: unknown</text>
<text x="16" y="1030" text-anchor="start" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif">A numbered mark means the broker appears in</text>
<text x="16" y="1044" text-anchor="start" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif">more than one group.</text>
</svg>
<figcaption>Brokers are grouped by the approval models on their pages. A numbered mark means the broker appears in more than one group. Paper trading is marked yes, no, or unknown.</figcaption>
</figure>

<details class="afr-cheatsheet-sources">
<summary>Sources and full table</summary>

Every broker side by side. Each value is sourced on its own page, and `unknown` means no source confirms it yet. Lists show the default path first. Machine-readable copies: [data/providers.json](data/providers.json), [data/providers.csv](data/providers.csv).

| Provider | Status | Can place orders | Approval model | Assets | Auth | Endpoint | Paper trading | Updated | Page status | Unknown fields |
|---|---|---|---|---|---|---|---|---|---|---|
| [Alpaca](providers/alpaca.md) | official-mcp | yes | none | stocks; ETFs; fractional equities; options (including multi-leg); crypto | Hosted Trading MCP: OAuth sign-in with an Alpaca account (plugins for Cursor, Claude Code and Codex). Local Trading MCP and CLI: API key and secret in environment variables | `https://api.alpaca.markets/mcp` | yes | 2026-11-19 | current | 2 of 12 |
| [Coinbase](providers/coinbase.md) | official-mcp | yes | separate-account | crypto spot; US derivatives (futures); eligible US equities; x402 payments | OAuth via login.coinbase.com for the remote MCP; Dynamic Client Registration and Client ID Metadata Documents supported, but clients are allowlisted; the local CLI uses a CDP API key | `https://agents.coinbase.com/mcp` | unknown | 2026-11-21 | current | 3 of 12 |
| [Interactive Brokers](providers/interactive-brokers.md) | official-mcp | draft-only; yes | draft-then-submit; ai-partition | stocks; equity options | IBKR's own login and authorization flow; credentials are never shared with the AI app; revoke in Client Portal > Settings > Manage Third-Party Consents | `https://api.ibkr.com/v1/api/mcp-public` | unknown | 2026-11-12 | current | 3 of 12 |
| [Kraken](providers/kraken.md) | official-mcp | yes | per-order-confirm | crypto spot; xStocks (tokenized US stocks and ETFs); forex; perpetual futures; inverse and fixed-date futures; earn and staking | API key and secret in environment variables, or a stored key: a browser sign-in key from kraken auth login (restricted, no withdrawal rights, expires after 90 days by default) or a key you created, stored with kraken setup | none (self-hosted only) | yes | 2026-11-19 | current | 1 of 12 |
| [Public](providers/public.md) | official-mcp | yes | separate-account; per-order-confirm | US-listed stocks and ETFs; options; crypto; bonds; prediction markets | OAuth for Claude, ChatGPT, Codex, Perplexity and Grok; a Public API key as the bearer token for Meta Muse and for the Public Agent Skill | `https://mcp.public.com/mcp` | no | 2026-11-19 | current | 1 of 12 |
| [Robinhood](providers/robinhood.md) | official-mcp | yes | separate-account; per-order-confirm | long equities; options (single-leg only); crypto (not in some states, including New York) | OAuth to the remote MCP server; protected-resource metadata lists the scope "internal"; an independent test reports PKCE and dynamic client registration | `https://agent.robinhood.com/mcp/trading` | unknown | 2026-11-19 | current | 2 of 12 |
| [Scalable Capital](providers/scalable-capital.md) | official-mcp | yes | per-order-confirm | unknown | Browser sign-in to Scalable through the AI app, with two-factor authentication; the MCP access level is set in the web version under Profile > Security > Agentic Investing | `https://mcp.scalable.capital/mcp` | unknown | 2026-11-19 | current | 5 of 12 |
| [Webull](providers/webull.md) | official-mcp | confirm-in-app; yes | per-order-confirm; none | stocks; options (single-leg and strategies); futures; crypto; event contracts | Cloud MCP: OAuth authorization code flow with a per-account Non-Trading or Trading capability. Local OpenAPI MCP: App Key and App Secret, with a 2FA flow | `https://api.webull.com/mcp` | yes | 2026-11-19 | current | 2 of 12 |

</details>

## Other sections

Payment programs and personal money agents are not brokers, so they have their own pages: [Payments](payments/README.md), [Personal money agents](personal-money/README.md). Their records are also in [data/programs.json](data/programs.json).

Approval models are explained in [approval-models/](approval-models/README.md).
A page marked stale or archived should not be treated as current; check last_verified.

## Sources

[^al-02]: [GitHub - alpacahq/alpaca-mcp-server: Alpaca’s official MCP Server lets you trade stocks, ETFs, crypto, and options, run data analysis, and build strat](sources/al-02.md). Alpaca (GitHub), official, retrieved 2026-11-19.
[^cb-01]: [Coinbase MCP - Coinbase Developer Documentation](sources/cb-01.md). Coinbase Developer Platform, official, retrieved 2026-11-12.
[^ib-01]: [Interactive Brokers AI Hub](sources/ib-01.md). Interactive Brokers, official, retrieved 2026-11-12.
[^kr-01]: [MCP server - Kraken docs](sources/kr-01.md). Kraken, official, retrieved 2026-11-19.
[^pu-01]: [Public MCP Server for trading on AI platforms](sources/pu-01.md). Public.com, official, retrieved 2026-11-19.
[^rh-01]: [Onboarding an external agent - Robinhood](sources/rh-01.md). Robinhood, official, retrieved 2026-11-19.
[^sc-01]: [How do I connect to Scalable MCP? - Scalable Capital Help Center](sources/sc-01.md). Scalable Capital Help Center, official, retrieved 2026-11-19.
[^wb-02]: [Webull Cloud MCP Server - Webull API](sources/wb-02.md). Webull Developer, official, retrieved 2026-11-19.
[^rh-04]: [Trading with your agent - Robinhood](sources/rh-04.md). Robinhood, official, retrieved 2026-11-19.
[^cb-03]: [Coinbase for Agents setup skill (skill.md)](sources/cb-03.md). Coinbase Developer Platform, official, retrieved 2026-11-12.
[^cb-07]: [Coinbase for Agents: Your AI Agent Can Now Trade and Pay with Coinbase](sources/cb-07.md). Coinbase, official, retrieved 2026-11-12.
[^wb-07]: [Webull Expands Cloud MCP to Enable AI-Powered Trading Without Coding or Installation](sources/wb-07.md). Webull / PR Newswire, official, retrieved 2026-11-12.
[^wb-03]: [GitHub - webull-inc/webull-openapi-mcp: Webull OpenAPI MCP · GitHub](sources/wb-03.md). Webull (GitHub), official, retrieved 2026-11-19.
[^ib-07]: [AI Instructions](sources/ib-07.md). IBKR Guides, official, retrieved 2026-11-12.
[^ib-06]: [AI-Powered Portfolio Analysis & Trading Tools (IBKR AI Integrations)](sources/ib-06.md). Interactive Brokers, official, retrieved 2026-11-12.
[^al-05]: [GitHub - alpacahq/cli: CLI for Trading API · GitHub](sources/al-05.md). Alpaca (GitHub), official, retrieved 2026-11-12.
[^al-03]: [GitHub - alpacahq/agentic: Multi-platform plugin marketplace for Alpaca APIs · GitHub](sources/al-03.md). Alpaca (GitHub), official, retrieved 2026-11-19.
[^al-01]: [Alpaca - Trade with AI Using Alpaca's MCP Server](sources/al-01.md). Alpaca, official, retrieved 2026-11-19.
[^pu-02]: [Connect the Public Hosted MCP Server to Claude, ChatGPT, Codex, Muse, Perplexity, and Grok - AI Trading Setup](sources/pu-02.md). Public.com API docs, official, retrieved 2026-11-19.
[^pu-06]: [How to Trade Stocks, Options & Crypto Using Claude](sources/pu-06.md). Public.com, official, retrieved 2026-11-12.
[^sc-03]: [How are orders approved and protected when using Scalable MCP? - Scalable Capital Help Center](sources/sc-03.md). Scalable Capital Help Center, official, retrieved 2026-11-19.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20trading.md&body=Page%3A%20trading.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
