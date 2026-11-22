---
type: approval-model
title: Approval models
summary: The five ways brokers decide who approves an agent's order, from a walled-off account to no broker-side approval at all.
page_status: current
last_verified: '2026-11-12'
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

**Blocked is not an approval model.** A provider that refuses outside agents gets `status: blocked` in its YAML header instead. See the [overview](../overview.md#who-is-blocking-agents).

## Can a broker use more than one approval model?

Models stack. Robinhood puts the agent in a separate account and lets you add per-order approval on top.[^rh-04][^rh-01] Interactive Brokers starts every client on draft-then-submit and requires a track record there before the AI Partition opens.[^ib-06]

## Is the guardrail enforced by the broker or by your client?

The key builder question is whether the guardrail is enforced by the broker (server side) or by your agent or MCP client (client side). Client-side approval can be skipped by a different client or a prompt; broker-side approval cannot. Coinbase documents that one client previews and asks before ordering while another orders in one turn, against the same server.[^cb-01]

See the [approval model comparison](../comparisons/launch-brokers.md).

## Who says yes, and who enforces it?

The five launch brokers, placed by who has to say yes and whether the [broker or your client](#is-the-guardrail-enforced-by-the-broker-or-by-your-client) enforces that guardrail. A broker can appear in more than one cell when its models stack. A dash means the wiki does not place a launch broker there. See also the [approval model comparison](../comparisons/launch-brokers.md).

<figure class="afr-cheatsheet-visual">
<svg role="img" viewBox="0 0 920 430" xmlns="http://www.w3.org/2000/svg" aria-labelledby="am-vis-title am-vis-desc">
  <title id="am-vis-title">Approval models spectrum for the five launch brokers</title>
  <desc id="am-vis-desc">A two-axis chart. Across: who says yes, from you approve each order, to draft then you submit, to a funded partition or separate account, to no broker approval. Up: who enforces it, the broker or your client. Robinhood sits in a separate account and, when Trade approvals are on, also in you approve each order, both enforced by the broker. Interactive Brokers starts at draft then you submit and, for Autonomous Trading, uses a funded AI Partition, both enforced by the broker. Webull Cloud MCP is you approve each order, enforced by the broker. Webull local OpenAPI MCP and Alpaca are no broker approval, enforced by your client or server. Coinbase per-order approval depends on the client. Coinbase's optional dedicated portfolio is in the table, not drawn as a default placement.</desc>
  <rect width="920" height="430" fill="var(--light)"/>
  <text x="16" y="28" fill="var(--darkgray)" font-size="13" font-family="system-ui, sans-serif">Who enforces it</text>
  <text x="200" y="54" text-anchor="middle" fill="var(--darkgray)" font-size="12" font-family="system-ui, sans-serif">You approve each order</text>
  <text x="410" y="54" text-anchor="middle" fill="var(--darkgray)" font-size="12" font-family="system-ui, sans-serif">Draft, then you submit</text>
  <text x="620" y="54" text-anchor="middle" fill="var(--darkgray)" font-size="11" font-family="system-ui, sans-serif">Funded partition or separate account</text>
  <text x="830" y="54" text-anchor="middle" fill="var(--darkgray)" font-size="12" font-family="system-ui, sans-serif">No broker approval</text>
  <rect x="95" y="66" width="210" height="155" fill="none" stroke="var(--lightgray)"/>
  <rect x="305" y="66" width="210" height="155" fill="none" stroke="var(--lightgray)"/>
  <rect x="515" y="66" width="210" height="155" fill="none" stroke="var(--lightgray)"/>
  <rect x="725" y="66" width="180" height="155" fill="none" stroke="var(--lightgray)"/>
  <rect x="95" y="221" width="210" height="155" fill="none" stroke="var(--lightgray)"/>
  <rect x="305" y="221" width="210" height="155" fill="none" stroke="var(--lightgray)"/>
  <rect x="515" y="221" width="210" height="155" fill="none" stroke="var(--lightgray)"/>
  <rect x="725" y="221" width="180" height="155" fill="none" stroke="var(--lightgray)"/>
  <text x="16" y="150" fill="var(--darkgray)" font-size="13" font-family="system-ui, sans-serif">Broker</text>
  <text x="16" y="305" fill="var(--darkgray)" font-size="13" font-family="system-ui, sans-serif">Your client</text>
  <rect x="108" y="80" width="184" height="40" rx="6" fill="var(--highlight)" stroke="var(--secondary)"/>
  <text x="200" y="104" text-anchor="middle" fill="var(--dark)" font-size="11" font-family="system-ui, sans-serif">Webull Cloud MCP</text>
  <rect x="108" y="150" width="184" height="48" rx="6" fill="var(--highlight)" stroke="var(--secondary)"/>
  <text x="200" y="168" text-anchor="middle" fill="var(--dark)" font-size="11" font-family="system-ui, sans-serif">Robinhood + Trade approvals</text>
  <text x="200" y="184" text-anchor="middle" fill="var(--darkgray)" font-size="10" font-family="system-ui, sans-serif">stacks with separate account</text>
  <rect x="318" y="110" width="184" height="52" rx="6" fill="var(--highlight)" stroke="var(--secondary)"/>
  <text x="410" y="130" text-anchor="middle" fill="var(--dark)" font-size="11" font-family="system-ui, sans-serif">Interactive Brokers</text>
  <text x="410" y="146" text-anchor="middle" fill="var(--darkgray)" font-size="10" font-family="system-ui, sans-serif">AI Integration (default)</text>
  <rect x="528" y="80" width="184" height="48" rx="6" fill="var(--highlight)" stroke="var(--secondary)"/>
  <text x="620" y="98" text-anchor="middle" fill="var(--dark)" font-size="11" font-family="system-ui, sans-serif">Robinhood (default)</text>
  <text x="620" y="114" text-anchor="middle" fill="var(--darkgray)" font-size="10" font-family="system-ui, sans-serif">separate agentic account</text>
  <rect x="528" y="150" width="184" height="48" rx="6" fill="var(--highlight)" stroke="var(--secondary)"/>
  <text x="620" y="168" text-anchor="middle" fill="var(--dark)" font-size="11" font-family="system-ui, sans-serif">Interactive Brokers</text>
  <text x="620" y="184" text-anchor="middle" fill="var(--darkgray)" font-size="10" font-family="system-ui, sans-serif">AI Partition</text>
  <defs>
    <marker id="am-arrow" markerWidth="8" markerHeight="8" refX="6" refY="4" orient="auto">
      <path d="M0,0 L8,4 L0,8 z" fill="var(--tertiary)"/>
    </marker>
  </defs>
  <path d="M528,104 C 430,104 330,174 292,174" fill="none" stroke="var(--tertiary)" stroke-width="2" marker-end="url(#am-arrow)"/>
  <path d="M502,136 L528,166" fill="none" stroke="var(--tertiary)" stroke-width="2" marker-end="url(#am-arrow)"/>
  <rect x="108" y="250" width="184" height="68" rx="6" fill="var(--highlight)" stroke="var(--secondary)"/>
  <text x="200" y="270" text-anchor="middle" fill="var(--dark)" font-size="11" font-family="system-ui, sans-serif">Coinbase per-order</text>
  <text x="200" y="286" text-anchor="middle" fill="var(--darkgray)" font-size="10" font-family="system-ui, sans-serif">depends on the client</text>
  <text x="200" y="302" text-anchor="middle" fill="var(--darkgray)" font-size="10" font-family="system-ui, sans-serif">ChatGPT shows confirmation cards</text>
  <rect x="736" y="240" width="156" height="44" rx="6" fill="var(--highlight)" stroke="var(--secondary)"/>
  <text x="814" y="257" text-anchor="middle" fill="var(--dark)" font-size="11" font-family="system-ui, sans-serif">Alpaca</text>
  <text x="814" y="273" text-anchor="middle" fill="var(--darkgray)" font-size="10" font-family="system-ui, sans-serif">no broker-side approval</text>
  <rect x="736" y="296" width="156" height="52" rx="6" fill="var(--highlight)" stroke="var(--secondary)"/>
  <text x="814" y="315" text-anchor="middle" fill="var(--dark)" font-size="11" font-family="system-ui, sans-serif">Webull local OpenAPI</text>
  <text x="814" y="331" text-anchor="middle" fill="var(--darkgray)" font-size="10" font-family="system-ui, sans-serif">your server enforces limits</text>
  <text x="510" y="412" text-anchor="middle" fill="var(--darkgray)" font-size="13" font-family="system-ui, sans-serif">Who says yes →</text>
</svg>
<figcaption>The table below has the same placements and the sources. Arrows show models that stack: Robinhood's separate account plus Trade approvals, and Interactive Brokers' draft-then-submit path then the AI Partition.</figcaption>
</figure>


| Who enforces | You approve each order | Draft, then you submit | Funded partition or separate account | No broker approval | Sources |
|---|---|---|---|---|---|
| Broker | [Webull](../providers/webull.md) Cloud MCP: you confirm each trade in the Webull app. [Robinhood](../providers/robinhood.md) with Trade approvals on, which stacks with the separate account. | [Interactive Brokers](../providers/interactive-brokers.md) AI Integration (default): you review and submit every instruction. A track record here is required before the AI Partition opens. | Robinhood (default): the agent trades in a separate agentic account, with Trade approvals off. Interactive Brokers Autonomous Trading: a funded [AI Partition](ai-partition.md). [Coinbase](../providers/coinbase.md) optional dedicated portfolio (spot crypto only); Coinbase also enforces limits on trade size, 24-hour volume and loss (auto-stop). Coinbase's default path is the portfolios you pick at sign-in, which can include the main account. | — | [^wb-07][^rh-04][^rh-01][^ib-01][^ib-07][^ib-06][^cb-03][^cb-07][^cb-10] |
| Your client | Coinbase: per-order approval depends on the client. The official ChatGPT plugin shows Coinbase confirmation cards. | — | — | [Alpaca](../providers/alpaca.md): no broker-side approval documented. Webull local OpenAPI MCP: direct orders with local limits enforced by your server. | [^cb-01][^cb-09][^al-05][^al-03][^wb-03] |

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

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20approval-models%2FREADME.md&body=Page%3A%20approval-models%2FREADME.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
