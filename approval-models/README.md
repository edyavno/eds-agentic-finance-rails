---
type: approval-model
title: Approval models
summary: The five ways brokers decide who approves an agent's order, from a walled-off account to no broker-side approval at all.
page_status: current
last_verified: '2026-11-27'
---

# Approval models

An approval model answers one question: **before an agent's order reaches the market, who or what has to say yes?** Providers often offer more than one, so provider pages list every model they document, default path first.

| Model | One line | Launch-broker examples |
|---|---|---|
| [Separate account](separate-account.md) | The agent trades only in an account you fund for it | Robinhood, Coinbase (optional) |
| [AI Partition](ai-partition.md) | A funded partition inside your account where an eligible AI may trade without per-order approval | Interactive Brokers Autonomous Trading |
| [Per-order confirm](per-order-confirm.md) | The agent prepares each order; you confirm it in the broker's app | Webull Cloud MCP, Robinhood with Trade approvals on |
| [Draft, then you submit](draft-then-submit.md) | The agent writes a non-binding instruction; you review and submit it | Interactive Brokers AI Integration |
| [None at the broker](none.md) | The broker executes what the agent sends; any approval lives in your client | Alpaca, Webull local OpenAPI MCP |

**Blocked is not an approval model.** A provider that refuses outside agents is marked blocked on its page instead. See the [overview](../overview.md#who-is-blocking-agents).

## Can a broker use more than one approval model?

Models stack. Robinhood puts the agent in a separate account and lets you add per-order approval on top.[^rh-04][^rh-01] Interactive Brokers starts every client on draft-then-submit and requires a track record there before the AI Partition opens.[^ib-06]

## Is the guardrail enforced by the broker or by your client?

The key builder question is whether the guardrail is enforced by the broker (server side) or by your agent or MCP client (client side). Client-side approval can be skipped by a different client or a prompt; broker-side approval cannot. Coinbase documents that one client previews and asks before ordering while another orders in one turn, against the same server.[^cb-01]

See the [approval model comparison](../comparisons/launch-brokers.md).

## Who says yes, and who enforces it?

The five launch brokers, placed by who has to say yes and whether the [broker or your client](#is-the-guardrail-enforced-by-the-broker-or-by-your-client) enforces that guardrail. A broker can appear in more than one cell when its models stack. See also the [approval model comparison](../comparisons/launch-brokers.md).

<figure class="afr-cheatsheet-visual afr-cheatsheet-visual--desktop">
<svg role="img" viewBox="0 0 800 560" xmlns="http://www.w3.org/2000/svg" aria-labelledby="am-d-title am-d-desc">
  <title id="am-d-title">Approval models spectrum for the five launch brokers</title>
  <desc id="am-d-desc">A two-axis chart. Across: who says yes, from you approve each order, to draft then you submit, to a funded partition or separate account, to no broker approval. Up: who enforces it, the broker or your client. Robinhood sits in a separate account and, when Trade approvals are on, also in you approve each order, both enforced by the broker. Interactive Brokers starts at draft then you submit and, for Autonomous Trading, uses a funded AI Partition, both enforced by the broker. Webull Cloud MCP is you approve each order, enforced by the broker. Webull local OpenAPI MCP and Alpaca are no broker approval, enforced by your client or server. Coinbase per-order approval depends on the client. Coinbase's dedicated portfolio is an optional separate account, enforced by the broker.</desc>
  <rect width="800" height="560" fill="var(--light)"/>
<text x="14" y="28" text-anchor="start" fill="var(--darkgray)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="14" y="28">Who enforces it</tspan>
  </text>
<text x="185" y="30" text-anchor="middle" fill="var(--darkgray)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="185" y="30">You approve</tspan>
  <tspan x="185" dy="15">each order</tspan>
  </text>
<text x="355" y="30" text-anchor="middle" fill="var(--darkgray)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="355" y="30">Draft, then</tspan>
  <tspan x="355" dy="15">you submit</tspan>
  </text>
<text x="525" y="30" text-anchor="middle" fill="var(--darkgray)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="525" y="30">Funded partition or</tspan>
  <tspan x="525" dy="15">separate account</tspan>
  </text>
<text x="695" y="30" text-anchor="middle" fill="var(--darkgray)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="695" y="30">No broker</tspan>
  <tspan x="695" dy="15">approval</tspan>
  </text>
  <rect x="100" y="68" width="680" height="430" fill="none" stroke="var(--lightgray)" stroke-width="1"/>
  <line x1="270" y1="68" x2="270" y2="498" stroke="var(--lightgray)"/>
  <line x1="440" y1="68" x2="440" y2="498" stroke="var(--lightgray)"/>
  <line x1="610" y1="68" x2="610" y2="498" stroke="var(--lightgray)"/>
  <line x1="100" y1="300" x2="780" y2="300" stroke="var(--lightgray)"/>
<text x="16" y="180" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="16" y="180">Broker</tspan>
  </text>
<text x="16" y="390" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="16" y="390">Your</tspan>
  <tspan x="16" dy="16">client</tspan>
  </text>
<rect x="110" y="84" width="140" height="52" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="180.0" y="105.6" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="180.0" y="105.6">Webull Cloud MCP</tspan>
  </text>
<text x="180.0" y="125.19999999999999" text-anchor="middle" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="180.0" y="125.19999999999999">confirm in the app</tspan>
  </text>
<rect x="110" y="146" width="140" height="72" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="180.0" y="169.8" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="180.0" y="169.8">Robinhood +</tspan>
  <tspan x="180.0" dy="16.2">Trade approvals</tspan>
  </text>
<text x="180.0" y="205.0" text-anchor="middle" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="180.0" y="205.0">stacks with separate account</tspan>
  </text>
<rect x="280" y="130" width="140" height="64" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="350.0" y="149.8" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="350.0" y="149.8">Interactive Brokers</tspan>
  <tspan x="350.0" dy="16.2">AI Integration</tspan>
  </text>
<text x="350.0" y="185.0" text-anchor="middle" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="350.0" y="185.0">default</tspan>
  </text>
<rect x="450" y="84" width="140" height="56" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="520.0" y="107.6" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="520.0" y="107.6">Robinhood</tspan>
  </text>
<text x="520.0" y="127.19999999999999" text-anchor="middle" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="520.0" y="127.19999999999999">default · separate account</tspan>
  </text>
<rect x="450" y="152" width="140" height="56" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="520.0" y="177.4" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="520.0" y="177.4">Interactive Brokers</tspan>
  <tspan x="520.0" dy="16.2">AI Partition</tspan>
  </text>
<rect x="450" y="220" width="140" height="64" rx="9" fill="var(--light)" stroke="var(--secondary)" stroke-width="1.25" stroke-dasharray="5 4"/><text x="520.0" y="239.8" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="520.0" y="239.8">Coinbase dedicated</tspan>
  <tspan x="520.0" dy="16.2">portfolio</tspan>
  </text>
<text x="520.0" y="275.0" text-anchor="middle" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="520.0" y="275.0">optional · spot crypto only</tspan>
  </text>
  <circle cx="258" cy="182" r="9" fill="var(--light)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="258" y="186" text-anchor="middle" fill="var(--dark)" font-size="11" font-family="system-ui, -apple-system, sans-serif" font-weight="700">
  <tspan x="258" y="186">1</tspan>
  </text>
  <circle cx="598" cy="112" r="9" fill="var(--light)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="598" y="116" text-anchor="middle" fill="var(--dark)" font-size="11" font-family="system-ui, -apple-system, sans-serif" font-weight="700">
  <tspan x="598" y="116">1</tspan>
  </text>
  <circle cx="428" cy="162" r="9" fill="var(--light)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="428" y="166" text-anchor="middle" fill="var(--dark)" font-size="11" font-family="system-ui, -apple-system, sans-serif" font-weight="700">
  <tspan x="428" y="166">2</tspan>
  </text>
  <circle cx="598" cy="180" r="9" fill="var(--light)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="598" y="184" text-anchor="middle" fill="var(--dark)" font-size="11" font-family="system-ui, -apple-system, sans-serif" font-weight="700">
  <tspan x="598" y="184">2</tspan>
  </text>
<text x="695" y="190" text-anchor="middle" fill="var(--gray)" font-size="18" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="695" y="190">—</tspan>
  </text>
<rect x="110" y="324" width="140" height="80" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="180.0" y="353.0" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="180.0" y="353.0">Coinbase per-order</tspan>
  </text>
<text x="180.0" y="372.6" text-anchor="middle" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="180.0" y="372.6">depends on the client</tspan>
  <tspan x="180.0" dy="13.8">ChatGPT shows cards</tspan>
  </text>
<text x="355" y="400" text-anchor="middle" fill="var(--gray)" font-size="18" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="355" y="400">—</tspan>
  </text>
<text x="525" y="400" text-anchor="middle" fill="var(--gray)" font-size="18" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="525" y="400">—</tspan>
  </text>
<rect x="620" y="324" width="150" height="56" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="695.0" y="347.6" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="695.0" y="347.6">Alpaca</tspan>
  </text>
<text x="695.0" y="367.20000000000005" text-anchor="middle" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="695.0" y="367.20000000000005">no broker-side approval</tspan>
  </text>
<rect x="620" y="392" width="150" height="64" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="695.0" y="411.8" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="695.0" y="411.8">Webull local</tspan>
  <tspan x="695.0" dy="16.2">OpenAPI MCP</tspan>
  </text>
<text x="695.0" y="447.0" text-anchor="middle" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="695.0" y="447.0">your server enforces limits</tspan>
  </text>
  <circle cx="128" cy="538" r="9" fill="var(--light)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="128" y="542" text-anchor="middle" fill="var(--dark)" font-size="11" font-family="system-ui, -apple-system, sans-serif" font-weight="700">
  <tspan x="128" y="542">1</tspan>
  </text>
  <circle cx="150" cy="538" r="9" fill="var(--light)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="150" y="542" text-anchor="middle" fill="var(--dark)" font-size="11" font-family="system-ui, -apple-system, sans-serif" font-weight="700">
  <tspan x="150" y="542">2</tspan>
  </text>
<text x="166" y="542" text-anchor="start" fill="var(--darkgray)" font-size="12" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="166" y="542">Models that stack (same number)</tspan>
  </text>
  <rect x="430" y="528" width="28" height="16" rx="4" fill="var(--light)" stroke="var(--secondary)" stroke-width="1.25" stroke-dasharray="4 3"/>
<text x="464" y="542" text-anchor="start" fill="var(--darkgray)" font-size="12" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="464" y="542">Optional, not a default path</tspan>
  </text>
</svg>
<figcaption>Cards that share a stack number are models that stack. A dashed card is optional, not a default path. A dash means the wiki does not place a launch broker there.</figcaption>
</figure>

<figure class="afr-cheatsheet-visual afr-cheatsheet-visual--mobile">
<svg role="img" viewBox="0 0 360 1180" xmlns="http://www.w3.org/2000/svg" aria-labelledby="am-m-title am-m-desc">
  <title id="am-m-title">Approval models spectrum for the five launch brokers</title>
  <desc id="am-m-desc">A two-axis chart. Across: who says yes, from you approve each order, to draft then you submit, to a funded partition or separate account, to no broker approval. Up: who enforces it, the broker or your client. Robinhood sits in a separate account and, when Trade approvals are on, also in you approve each order, both enforced by the broker. Interactive Brokers starts at draft then you submit and, for Autonomous Trading, uses a funded AI Partition, both enforced by the broker. Webull Cloud MCP is you approve each order, enforced by the broker. Webull local OpenAPI MCP and Alpaca are no broker approval, enforced by your client or server. Coinbase per-order approval depends on the client. Coinbase's dedicated portfolio is an optional separate account, enforced by the broker.</desc>
  <rect width="360" height="1180" fill="var(--light)"/>
<text x="16" y="28" text-anchor="start" fill="var(--darkgray)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="16" y="28">Who enforces it</tspan>
  </text>
  <rect x="12" y="44" width="336" height="28" rx="6" fill="var(--highlight)"/>
<text x="180" y="63" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="180" y="63">Broker</tspan>
  </text>
<text x="16" y="96" text-anchor="start" fill="var(--darkgray)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="16" y="96">You approve each order</tspan>
  </text>
<rect x="16" y="106" width="328" height="48" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="180.0" y="125.6" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="180.0" y="125.6">Webull Cloud MCP</tspan>
  </text>
<text x="180.0" y="145.2" text-anchor="middle" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="180.0" y="145.2">confirm in the app</tspan>
  </text>
<rect x="16" y="162" width="328" height="56" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="180.0" y="185.6" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="180.0" y="185.6">Robinhood + Trade approvals</tspan>
  </text>
<text x="180.0" y="205.2" text-anchor="middle" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="180.0" y="205.2">stacks with the separate account</tspan>
  </text>
<text x="16" y="244" text-anchor="start" fill="var(--darkgray)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="16" y="244">Draft, then you submit</tspan>
  </text>
<rect x="16" y="254" width="328" height="56" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="180.0" y="277.6" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="180.0" y="277.6">Interactive Brokers AI Integration</tspan>
  </text>
<text x="180.0" y="297.20000000000005" text-anchor="middle" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="180.0" y="297.20000000000005">default</tspan>
  </text>
<text x="16" y="356" text-anchor="start" fill="var(--darkgray)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="16" y="356">Funded partition or separate account</tspan>
  </text>
<rect x="16" y="366" width="328" height="48" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="180.0" y="385.6" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="180.0" y="385.6">Robinhood</tspan>
  </text>
<text x="180.0" y="405.20000000000005" text-anchor="middle" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="180.0" y="405.20000000000005">default · separate agentic account</tspan>
  </text>
<rect x="16" y="422" width="328" height="48" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="180.0" y="451.2" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="180.0" y="451.2">Interactive Brokers AI Partition</tspan>
  </text>
<rect x="16" y="478" width="328" height="56" rx="9" fill="var(--light)" stroke="var(--secondary)" stroke-width="1.25" stroke-dasharray="5 4"/><text x="180.0" y="501.6" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="180.0" y="501.6">Coinbase dedicated portfolio</tspan>
  </text>
<text x="180.0" y="521.2" text-anchor="middle" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="180.0" y="521.2">optional · spot crypto only</tspan>
  </text>
  <circle cx="32" cy="190" r="9" fill="var(--light)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="32" y="194" text-anchor="middle" fill="var(--dark)" font-size="11" font-family="system-ui, -apple-system, sans-serif" font-weight="700">
  <tspan x="32" y="194">1</tspan>
  </text>
  <circle cx="32" cy="282" r="9" fill="var(--light)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="32" y="286" text-anchor="middle" fill="var(--dark)" font-size="11" font-family="system-ui, -apple-system, sans-serif" font-weight="700">
  <tspan x="32" y="286">2</tspan>
  </text>
  <circle cx="32" cy="390" r="9" fill="var(--light)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="32" y="394" text-anchor="middle" fill="var(--dark)" font-size="11" font-family="system-ui, -apple-system, sans-serif" font-weight="700">
  <tspan x="32" y="394">1</tspan>
  </text>
  <circle cx="32" cy="446" r="9" fill="var(--light)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="32" y="450" text-anchor="middle" fill="var(--dark)" font-size="11" font-family="system-ui, -apple-system, sans-serif" font-weight="700">
  <tspan x="32" y="450">2</tspan>
  </text>
<text x="16" y="556" text-anchor="start" fill="var(--darkgray)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="16" y="556">No broker approval</tspan>
  </text>
<text x="180" y="582" text-anchor="middle" fill="var(--gray)" font-size="18" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="180" y="582">—</tspan>
  </text>
  <rect x="12" y="610" width="336" height="28" rx="6" fill="var(--highlight)"/>
<text x="180" y="629" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="180" y="629">Your client</tspan>
  </text>
<text x="16" y="662" text-anchor="start" fill="var(--darkgray)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="16" y="662">You approve each order</tspan>
  </text>
<rect x="16" y="672" width="328" height="64" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="180.0" y="693.0" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="180.0" y="693.0">Coinbase per-order</tspan>
  </text>
<text x="180.0" y="712.6" text-anchor="middle" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="180.0" y="712.6">depends on the client</tspan>
  <tspan x="180.0" dy="13.8">ChatGPT shows confirmation cards</tspan>
  </text>
<text x="16" y="758" text-anchor="start" fill="var(--darkgray)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="16" y="758">Draft, then you submit</tspan>
  </text>
<text x="180" y="784" text-anchor="middle" fill="var(--gray)" font-size="18" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="180" y="784">—</tspan>
  </text>
<text x="16" y="814" text-anchor="start" fill="var(--darkgray)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="16" y="814">Funded partition or separate account</tspan>
  </text>
<text x="180" y="840" text-anchor="middle" fill="var(--gray)" font-size="18" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="180" y="840">—</tspan>
  </text>
<text x="16" y="870" text-anchor="start" fill="var(--darkgray)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="16" y="870">No broker approval</tspan>
  </text>
<rect x="16" y="880" width="328" height="48" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="180.0" y="899.6" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="180.0" y="899.6">Alpaca</tspan>
  </text>
<text x="180.0" y="919.2" text-anchor="middle" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="180.0" y="919.2">no broker-side approval</tspan>
  </text>
<rect x="16" y="936" width="328" height="56" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="180.0" y="959.6" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="180.0" y="959.6">Webull local OpenAPI MCP</tspan>
  </text>
<text x="180.0" y="979.2" text-anchor="middle" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="180.0" y="979.2">your server enforces limits</tspan>
  </text>
  <line x1="16" y1="1016" x2="344" y2="1016" stroke="var(--lightgray)"/>
  <circle cx="32" cy="1048" r="9" fill="var(--light)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="32" y="1052" text-anchor="middle" fill="var(--dark)" font-size="11" font-family="system-ui, -apple-system, sans-serif" font-weight="700">
  <tspan x="32" y="1052">1</tspan>
  </text>
  <circle cx="54" cy="1048" r="9" fill="var(--light)" stroke="var(--secondary)" stroke-width="1.5"/>
<text x="54" y="1052" text-anchor="middle" fill="var(--dark)" font-size="11" font-family="system-ui, -apple-system, sans-serif" font-weight="700">
  <tspan x="54" y="1052">2</tspan>
  </text>
<text x="70" y="1052" text-anchor="start" fill="var(--darkgray)" font-size="12" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="70" y="1052">Models that stack (same number)</tspan>
  </text>
  <rect x="24" y="1078" width="28" height="16" rx="4" fill="var(--light)" stroke="var(--secondary)" stroke-width="1.25" stroke-dasharray="4 3"/>
<text x="60" y="1091" text-anchor="start" fill="var(--darkgray)" font-size="12" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="60" y="1091">Optional, not a default path</tspan>
  </text>
<text x="16" y="1130" text-anchor="start" fill="var(--gray)" font-size="11" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="16" y="1130">A dash means the wiki does not place a launch broker there.</tspan>
  </text>
</svg>
<figcaption>Cards that share a stack number are models that stack. A dashed card is optional, not a default path. A dash means the wiki does not place a launch broker there.</figcaption>
</figure>

<details class="afr-cheatsheet-sources">
<summary>Sources and full table</summary>

| Who enforces | You approve each order | Draft, then you submit | Funded partition or separate account | No broker approval | Sources |
|---|---|---|---|---|---|
| Broker | [Webull](../providers/webull.md) Cloud MCP: you confirm each trade in the Webull app. [Robinhood](../providers/robinhood.md) with Trade approvals on, which stacks with the separate account. | [Interactive Brokers](../providers/interactive-brokers.md) AI Integration (default): you review and submit every instruction. A track record here is required before the AI Partition opens. | Robinhood (default): the agent trades in a separate agentic account, with Trade approvals off. Interactive Brokers Autonomous Trading: a funded [AI Partition](ai-partition.md). [Coinbase](../providers/coinbase.md) optional dedicated portfolio (spot crypto only); Coinbase also enforces limits on trade size, 24-hour volume and loss (auto-stop). Coinbase's default path is the portfolios you pick at sign-in, which can include the main account. | — | [^wb-07][^rh-04][^rh-01][^ib-01][^ib-07][^ib-06][^cb-03][^cb-07][^cb-10] |
| Your client | Coinbase: per-order approval depends on the client. The official ChatGPT plugin shows Coinbase confirmation cards. | — | — | [Alpaca](../providers/alpaca.md): no broker-side approval documented. Webull local OpenAPI MCP: direct orders with local limits enforced by your server. | [^cb-01][^cb-09][^al-05][^al-03][^wb-03] |

</details>

Outside the broker chart, a shopper can also set limits and approvals in a merchant [Agent Profile](../glossary.md#agent-profile), as Walmart describes for its [Agent Gateway](../glossary.md#agent-gateway-walmart).[^wm-02] The UK's Financial Conduct Authority tells consumers to consider whether they want to consent to every transaction, set limits, or let decisions be made for them.[^fc-02] In [Tasks in Gemini](../personal-money/gemini-tasks.md), you can set a hard spending cap, and Gemini is designed to ask for confirmation or pre-approval before clicking "Buy," unless you set a routine action to "Always allow".[^gg-04] See [Meta Muse](../personal-money/meta-muse.md#where-can-muse-shop) and [Mandates and data access](../rails/mandates-and-data-access.md#what-have-a-regulator-and-two-banks-said-about-agent-authority).

## Sources

[^rh-04]: [Trading with your agent - Robinhood](../sources/rh-04.md). Robinhood, official, retrieved 2026-11-19.
[^rh-01]: [Onboarding an external agent - Robinhood](../sources/rh-01.md). Robinhood, official, retrieved 2026-11-19.
[^ib-06]: [AI-Powered Portfolio Analysis & Trading Tools (IBKR AI Integrations)](../sources/ib-06.md). Interactive Brokers, official, retrieved 2026-11-12.
[^cb-01]: [Coinbase MCP - Coinbase Developer Documentation](../sources/cb-01.md). Coinbase Developer Platform, official, retrieved 2026-11-12.
[^wb-07]: [Webull Expands Cloud MCP to Enable AI-Powered Trading Without Coding or Installation](../sources/wb-07.md). Webull / PR Newswire, official, retrieved 2026-11-12.
[^ib-01]: [Interactive Brokers AI Hub](../sources/ib-01.md). Interactive Brokers, official, retrieved 2026-11-12.
[^ib-07]: [AI Instructions](../sources/ib-07.md). IBKR Guides, official, retrieved 2026-11-12.
[^cb-03]: [Coinbase for Agents setup skill (skill.md)](../sources/cb-03.md). Coinbase Developer Platform, official, retrieved 2026-11-12.
[^cb-07]: [Coinbase for Agents: Your AI Agent Can Now Trade and Pay with Coinbase](../sources/cb-07.md). Coinbase, official, retrieved 2026-11-12.
[^cb-10]: [Coinbase for Agents introduces new Agent Controls](../sources/cb-10.md). Coinbase, official, retrieved 2026-11-18.
[^cb-09]: [Coinbase MCP - Coinbase Developer Documentation](../sources/cb-09.md). Coinbase Developer Platform, official, retrieved 2026-11-19.
[^al-05]: [GitHub - alpacahq/cli: CLI for Trading API · GitHub](../sources/al-05.md). Alpaca (GitHub), official, retrieved 2026-11-12.
[^al-03]: [GitHub - alpacahq/agentic: Multi-platform plugin marketplace for Alpaca APIs · GitHub](../sources/al-03.md). Alpaca (GitHub), official, retrieved 2026-11-19.
[^wb-03]: [GitHub - webull-inc/webull-openapi-mcp: Webull OpenAPI MCP · GitHub](../sources/wb-03.md). Webull (GitHub), official, retrieved 2026-11-19.
[^wm-02]: [Making It Possible for Agents to Shop on Behalf of Customers](../sources/wm-02.md). Walmart, official, retrieved 2026-11-25.
[^fc-02]: [Using AI agents](../sources/fc-02.md). Financial Conduct Authority, official, retrieved 2026-11-25.
[^gg-04]: [Put Gemini to work for you](../sources/gg-04.md). Google, official, retrieved 2026-11-27.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20approval-models%2FREADME.md&body=Page%3A%20approval-models%2FREADME.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
