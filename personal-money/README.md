---
type: personal-money
title: Personal money agents
summary: AI agents that work with a person's bank and card data, the tools that connect them, banks' own AI tools, and how big banks treat outside agents.
page_status: current
last_verified: '2026-11-27'
---

# Personal money agents

This section covers AI agents that help a person manage everyday money: seeing balances, spotting subscriptions, moving cash. It also covers the plumbing that connects them to bank accounts, and how banks respond. Each tool has its own page with a short, sourced record. The same records are in [data/programs.json](../data/programs.json).

## The pages

| Page | Type | In one line |
|---|---|---|
| [Meta Muse](meta-muse.md) | Personal agent | Meta's personal AI agent. People connect bank and card accounts through Plaid for money guidance. From 2026-11-24 it can shop Walmart, and JD Sports is a UK connector.[^pb-01][^wm-01][^jd-01] |
| [Grok Bot](grok-bot.md) | Personal agent | xAI's agent reads balances, spending and investments from accounts linked through Plaid, read-only. It pays with Link or X Money after you approve.[^gb-01][^gb-05] |
| [X Money](x-money.md) | Money account | A US account in the X app. Through the Grok Bot plugin an agent can read the balance, pay with the card and send money, with approval for each money move.[^xm-01] |
| [Claude Personal Finance](claude-personal-finance.md) | Personal agent | Claude reads balances and transactions from banks linked through Plaid. It is read-only and in beta on paid US plans.[^cl-01] |
| [Claude Duet](claude-duet.md) | Personal agent | Anthropic's proactive agent app, in research preview. It asks before paying, pays with a one-time Link card, and cannot trade or move money between accounts.[^cl-03][^cl-04] |
| [Finances in ChatGPT](chatgpt-finances.md) | Personal agent | ChatGPT reads accounts through Plaid and credit reports through Experian in the US. It cannot move money, pay bills or trade.[^oa-05] |
| [OpenAI dots](openai-dots.md) | Personal agent | Always-on OpenAI agents that can buy with a saved merchant card after approval. Whether they can read Finances data is unknown.[^oa-07][^oa-08] |
| [Instinct](instinct.md) | Personal agent | A personal assistant in iMessage and WhatsApp. Plaid says it powers read-only account connections for US users.[^pb-09] |
| [Perplexity Personal CFO](perplexity-personal-cfo.md) | Personal agent | Plaid says Perplexity users can connect accounts and ask about their own money, read-only, in the US and 17 European countries.[^pb-12][^pb-13] |
| [Nous](nous.md) | Personal agent | A UK household agent that switches providers and cancels subscriptions, with a savings mode you choose. It cannot move money.[^ns-01] |
| [Gemini with Google Wallet](gemini-google-wallet.md) | Personal agent | Google's Gemini app answers money questions from Google Wallet and accounts linked through Plaid. It is read-only. From 2026-11-23, Search AI Mode can also connect to Wallet, still read-only.[^gg-01][^gg-03] |
| [Tasks in Gemini](gemini-tasks.md) | Personal agent | Google's task mode can shop and check out with Google Pay, using [AP2](../glossary.md#ap2). You can set a hard spending cap, and it is designed to ask before buying.[^gg-04] |
| [Starling Assistant](starling-assistant.md) | Bank AI tool | A UK bank's in-app assistant that will set up payments from voice or text, with a tap to approve each one.[^st-01] |
| [Plaid MCP servers](plaid.md) | Developer tools | Plaid's MCP servers are for developer diagnostics and a sandbox coding kit, not end-user account access.[^pb-02] |
| [JPMorgan Smart Cash](jpmorgan-smart-cash.md) | Bank AI tool | A JPMorgan pilot that aims to predict a user's cash flow and move funds for yield (news report).[^bl-01] |
| [Banks and outside agents](banks-and-outside-agents.md) | Topic | News reports say several big US banks block outside agents that log in with a customer's password.[^bl-02][^bl-08] Citi and Chase say in their own user agreements that they treat an outside agent's actions as yours.[^ci-01][^jp-02] |

## Read, pay or move money?

What each tool can do, and how it connects. [Banks and outside agents](banks-and-outside-agents.md) is a topic page, not a tool, so it is not in the diagram.

<figure class="afr-cheatsheet-visual afr-cheatsheet-visual--desktop">
<svg role="img" viewBox="0 0 800 560" xmlns="http://www.w3.org/2000/svg" aria-labelledby="pm-d-title pm-d-desc">
  <title id="pm-d-title">Personal money agents: read, pay or move money</title>
  <desc id="pm-d-desc">Three lanes. Each tool sits in the rightmost lane the wiki can confirm: read only, pays with approval, or moves money. Read only holds Claude Personal Finance, Finances in ChatGPT, Perplexity Personal CFO, and Gemini with Google Wallet. Pays with approval holds Meta Muse, Grok Bot, Claude Duet, OpenAI dots, Instinct, and Starling Assistant. Moves money holds X Money and JPMorgan Smart Cash. Nous cannot move money, and whether it pays or only reads is unknown, so it sits in Other. Plaid MCP servers are developer tools, not end-user account access, so they also sit in Other. Marks on each chip show how it connects: Plaid, Link or a wallet like it, an own account, inside the bank, another cited connection, or unknown.</desc>
  <rect width="800" height="560" fill="var(--light)"/>
  <rect x="16.0" y="16" width="248.0" height="336" rx="12" fill="var(--light)" stroke="var(--lightgray)"/>
  <rect x="16.0" y="16" width="248.0" height="40" rx="12" fill="var(--highlight)"/>
  <rect x="16.0" y="32" width="248.0" height="24" fill="var(--highlight)"/>
<text x="140.0" y="42" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="140.0" y="42">Read only</tspan>
  </text>
<rect x="24.0" y="64" width="232.0" height="40" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="34.0" y="89.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="34.0" y="89.0">Claude Personal Finance</tspan>
  </text>
  <circle cx="238.5" cy="84.0" r="5.5" fill="var(--secondary)"/>
<rect x="24.0" y="112" width="232.0" height="40" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="34.0" y="137.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="34.0" y="137.0">Finances in ChatGPT</tspan>
  </text>
  <path d="M238.5,126.5 L244.0,137.5 L233.0,137.5 Z" fill="var(--gray)"/>
  <circle cx="224.5" cy="132.0" r="5.5" fill="var(--secondary)"/>
<rect x="24.0" y="160" width="232.0" height="40" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="34.0" y="185.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="34.0" y="185.0">Perplexity Personal CFO</tspan>
  </text>
  <circle cx="238.5" cy="180.0" r="5.5" fill="var(--secondary)"/>
<rect x="24.0" y="208" width="232.0" height="40" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="34.0" y="233.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="34.0" y="233.0">Gemini + Google Wallet</tspan>
  </text>
  <path d="M238.5,222.5 L244.0,233.5 L233.0,233.5 Z" fill="var(--gray)"/>
  <circle cx="224.5" cy="228.0" r="5.5" fill="var(--secondary)"/>
  <rect x="276.0" y="16" width="248.0" height="336" rx="12" fill="var(--light)" stroke="var(--lightgray)"/>
  <rect x="276.0" y="16" width="248.0" height="40" rx="12" fill="var(--highlight)"/>
  <rect x="276.0" y="32" width="248.0" height="24" fill="var(--highlight)"/>
<text x="400.0" y="42" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="400.0" y="42">Pays with approval</tspan>
  </text>
<rect x="284.0" y="64" width="232.0" height="40" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="294.0" y="89.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="294.0" y="89.0">Meta Muse</tspan>
  </text>
  <path d="M498.5,78.5 L504.0,84.0 L498.5,89.5 L493.0,84.0 Z" fill="var(--tertiary)"/>
  <circle cx="484.5" cy="84.0" r="5.5" fill="var(--secondary)"/>
<rect x="284.0" y="112" width="232.0" height="40" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="294.0" y="137.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="294.0" y="137.0">Grok Bot</tspan>
  </text>
  <rect x="493.0" y="126.5" width="11.0" height="11.0" rx="2" fill="var(--dark)"/>
  <path d="M484.5,126.5 L490.0,132.0 L484.5,137.5 L479.0,132.0 Z" fill="var(--tertiary)"/>
  <circle cx="470.5" cy="132.0" r="5.5" fill="var(--secondary)"/>
<rect x="284.0" y="160" width="232.0" height="40" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="294.0" y="185.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="294.0" y="185.0">Claude Duet</tspan>
  </text>
  <path d="M498.5,174.5 L504.0,180.0 L498.5,185.5 L493.0,180.0 Z" fill="var(--tertiary)"/>
<rect x="284.0" y="208" width="232.0" height="40" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="294.0" y="233.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="294.0" y="233.0">OpenAI dots</tspan>
  </text>
  <path d="M498.5,222.5 L504.0,233.5 L493.0,233.5 Z" fill="var(--gray)"/>
<rect x="284.0" y="256" width="232.0" height="40" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="294.0" y="281.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="294.0" y="281.0">Instinct</tspan>
  </text>
  <path d="M498.5,270.5 L504.0,276.0 L498.5,281.5 L493.0,276.0 Z" fill="var(--tertiary)"/>
  <circle cx="484.5" cy="276.0" r="5.5" fill="var(--secondary)"/>
<rect x="284.0" y="304" width="232.0" height="40" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="294.0" y="329.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="294.0" y="329.0">Starling Assistant</tspan>
  </text>
  <path d="M493.0,329.5 L493.0,323.0 L498.5,318.5 L504.0,323.0 L504.0,329.5 Z" fill="var(--darkgray)"/>
  <rect x="536.0" y="16" width="248.0" height="336" rx="12" fill="var(--light)" stroke="var(--lightgray)"/>
  <rect x="536.0" y="16" width="248.0" height="40" rx="12" fill="var(--highlight)"/>
  <rect x="536.0" y="32" width="248.0" height="24" fill="var(--highlight)"/>
<text x="660.0" y="42" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="660.0" y="42">Moves money</tspan>
  </text>
<rect x="544.0" y="64" width="232.0" height="40" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="554.0" y="89.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="554.0" y="89.0">X Money</tspan>
  </text>
  <rect x="753.0" y="78.5" width="11.0" height="11.0" rx="2" fill="var(--dark)"/>
<rect x="544.0" y="112" width="232.0" height="40" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="554.0" y="137.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="554.0" y="137.0">JPMorgan Smart Cash</tspan>
  </text>
  <path d="M753.0,137.5 L753.0,131.0 L758.5,126.5 L764.0,131.0 L764.0,137.5 Z" fill="var(--darkgray)"/>
  <rect x="16" y="364" width="768" height="126" rx="12" fill="var(--light)" stroke="var(--lightgray)"/>
<text x="28" y="386" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="28" y="386">Other</tspan>
  </text>
<rect x="28" y="398" width="360" height="44" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="38" y="425.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="38" y="425.0">Nous</tspan>
  </text>
  <circle cx="370.5" cy="420.0" r="5.5" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
<text x="28" y="458" text-anchor="start" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="28" y="458">Cannot move money; pay and read are unknown</tspan>
  </text>
<rect x="408" y="398" width="360" height="44" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="418" y="425.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="418" y="425.0">Plaid MCP servers</tspan>
  </text>
  <circle cx="750.5" cy="420.0" r="5.5" fill="var(--secondary)"/>
<text x="408" y="458" text-anchor="start" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="408" y="458">Not for end-user accounts</tspan>
  </text>
  <circle cx="22" cy="510" r="6" fill="var(--secondary)"/>
<text x="34" y="514" text-anchor="start" fill="var(--darkgray)" font-size="12" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="34" y="514">Plaid</tspan>
  </text>
  <path d="M212,504 L218,510 L212,516 L206,510 Z" fill="var(--tertiary)"/>
<text x="224" y="514" text-anchor="start" fill="var(--darkgray)" font-size="12" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="224" y="514">Link, or a wallet like it</tspan>
  </text>
  <rect x="396" y="504" width="12" height="12" rx="2" fill="var(--dark)"/>
<text x="414" y="514" text-anchor="start" fill="var(--darkgray)" font-size="12" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="414" y="514">Own account</tspan>
  </text>
  <path d="M16,538 L16,531 L22,526 L28,531 L28,538 Z" fill="var(--darkgray)"/>
<text x="34" y="536" text-anchor="start" fill="var(--darkgray)" font-size="12" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="34" y="536">Inside the bank</tspan>
  </text>
  <path d="M212,526 L218,538 L206,538 Z" fill="var(--gray)"/>
<text x="224" y="536" text-anchor="start" fill="var(--darkgray)" font-size="12" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="224" y="536">Other cited connection</tspan>
  </text>
  <circle cx="402" cy="532" r="6" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
<text x="414" y="536" text-anchor="start" fill="var(--darkgray)" font-size="12" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="414" y="536">unknown</tspan>
  </text>
</svg>
<figcaption>Each tool sits in the rightmost lane the wiki can confirm. A tool that also reads may still sit in Pays or Moves. Connection marks are in the legend. Other holds tools the wiki cannot place in a lane.</figcaption>
</figure>

<figure class="afr-cheatsheet-visual afr-cheatsheet-visual--mobile">
<svg role="img" viewBox="0 0 360 1058" xmlns="http://www.w3.org/2000/svg" aria-labelledby="pm-m-title pm-m-desc">
  <title id="pm-m-title">Personal money agents: read, pay or move money</title>
  <desc id="pm-m-desc">Three lanes. Each tool sits in the rightmost lane the wiki can confirm: read only, pays with approval, or moves money. Read only holds Claude Personal Finance, Finances in ChatGPT, Perplexity Personal CFO, and Gemini with Google Wallet. Pays with approval holds Meta Muse, Grok Bot, Claude Duet, OpenAI dots, Instinct, and Starling Assistant. Moves money holds X Money and JPMorgan Smart Cash. Nous cannot move money, and whether it pays or only reads is unknown, so it sits in Other. Plaid MCP servers are developer tools, not end-user account access, so they also sit in Other. Marks on each chip show how it connects: Plaid, Link or a wallet like it, an own account, inside the bank, another cited connection, or unknown.</desc>
  <rect width="360" height="1058" fill="var(--light)"/>
  <rect x="12" y="12" width="336" height="248" rx="12" fill="var(--light)" stroke="var(--lightgray)"/>
  <rect x="12" y="12" width="336" height="34" rx="12" fill="var(--highlight)"/>
  <rect x="12" y="28" width="336" height="18" fill="var(--highlight)"/>
<text x="180" y="34" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="180" y="34">Read only</tspan>
  </text>
<rect x="22" y="54" width="316" height="42" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="32" y="80.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="32" y="80.0">Claude Personal Finance</tspan>
  </text>
  <circle cx="320.5" cy="75.0" r="5.5" fill="var(--secondary)"/>
<rect x="22" y="104" width="316" height="42" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="32" y="130.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="32" y="130.0">Finances in ChatGPT</tspan>
  </text>
  <path d="M320.5,119.5 L326.0,130.5 L315.0,130.5 Z" fill="var(--gray)"/>
  <circle cx="306.5" cy="125.0" r="5.5" fill="var(--secondary)"/>
<rect x="22" y="154" width="316" height="42" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="32" y="180.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="32" y="180.0">Perplexity Personal CFO</tspan>
  </text>
  <circle cx="320.5" cy="175.0" r="5.5" fill="var(--secondary)"/>
<rect x="22" y="204" width="316" height="42" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="32" y="230.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="32" y="230.0">Gemini + Google Wallet</tspan>
  </text>
  <path d="M320.5,219.5 L326.0,230.5 L315.0,230.5 Z" fill="var(--gray)"/>
  <circle cx="306.5" cy="225.0" r="5.5" fill="var(--secondary)"/>
  <rect x="12" y="270" width="336" height="348" rx="12" fill="var(--light)" stroke="var(--lightgray)"/>
  <rect x="12" y="270" width="336" height="34" rx="12" fill="var(--highlight)"/>
  <rect x="12" y="286" width="336" height="18" fill="var(--highlight)"/>
<text x="180" y="292" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="180" y="292">Pays with approval</tspan>
  </text>
<rect x="22" y="312" width="316" height="42" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="32" y="338.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="32" y="338.0">Meta Muse</tspan>
  </text>
  <path d="M320.5,327.5 L326.0,333.0 L320.5,338.5 L315.0,333.0 Z" fill="var(--tertiary)"/>
  <circle cx="306.5" cy="333.0" r="5.5" fill="var(--secondary)"/>
<rect x="22" y="362" width="316" height="42" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="32" y="388.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="32" y="388.0">Grok Bot</tspan>
  </text>
  <rect x="315.0" y="377.5" width="11.0" height="11.0" rx="2" fill="var(--dark)"/>
  <path d="M306.5,377.5 L312.0,383.0 L306.5,388.5 L301.0,383.0 Z" fill="var(--tertiary)"/>
  <circle cx="292.5" cy="383.0" r="5.5" fill="var(--secondary)"/>
<rect x="22" y="412" width="316" height="42" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="32" y="438.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="32" y="438.0">Claude Duet</tspan>
  </text>
  <path d="M320.5,427.5 L326.0,433.0 L320.5,438.5 L315.0,433.0 Z" fill="var(--tertiary)"/>
<rect x="22" y="462" width="316" height="42" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="32" y="488.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="32" y="488.0">OpenAI dots</tspan>
  </text>
  <path d="M320.5,477.5 L326.0,488.5 L315.0,488.5 Z" fill="var(--gray)"/>
<rect x="22" y="512" width="316" height="42" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="32" y="538.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="32" y="538.0">Instinct</tspan>
  </text>
  <path d="M320.5,527.5 L326.0,533.0 L320.5,538.5 L315.0,533.0 Z" fill="var(--tertiary)"/>
  <circle cx="306.5" cy="533.0" r="5.5" fill="var(--secondary)"/>
<rect x="22" y="562" width="316" height="42" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="32" y="588.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="32" y="588.0">Starling Assistant</tspan>
  </text>
  <path d="M315.0,588.5 L315.0,582.0 L320.5,577.5 L326.0,582.0 L326.0,588.5 Z" fill="var(--darkgray)"/>
  <rect x="12" y="628" width="336" height="148" rx="12" fill="var(--light)" stroke="var(--lightgray)"/>
  <rect x="12" y="628" width="336" height="34" rx="12" fill="var(--highlight)"/>
  <rect x="12" y="644" width="336" height="18" fill="var(--highlight)"/>
<text x="180" y="650" text-anchor="middle" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="180" y="650">Moves money</tspan>
  </text>
<rect x="22" y="670" width="316" height="42" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="32" y="696.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="32" y="696.0">X Money</tspan>
  </text>
  <rect x="315.0" y="685.5" width="11.0" height="11.0" rx="2" fill="var(--dark)"/>
<rect x="22" y="720" width="316" height="42" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="32" y="746.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="32" y="746.0">JPMorgan Smart Cash</tspan>
  </text>
  <path d="M315.0,746.5 L315.0,740.0 L320.5,735.5 L326.0,740.0 L326.0,746.5 Z" fill="var(--darkgray)"/>
  <rect x="12" y="786" width="336" height="172" rx="12" fill="var(--light)" stroke="var(--lightgray)"/>
<text x="24" y="808" text-anchor="start" fill="var(--dark)" font-size="13" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="24" y="808">Other</tspan>
  </text>
<rect x="22" y="820" width="316" height="42" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="32" y="846.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="32" y="846.0">Nous</tspan>
  </text>
  <circle cx="320.5" cy="841.0" r="5.5" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
<text x="24" y="875" text-anchor="start" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="24" y="875">Cannot move money; pay and read are unknown</tspan>
  </text>
<rect x="22" y="882" width="316" height="42" rx="9" fill="var(--highlight)" stroke="var(--secondary)" stroke-width="1.25"/><text x="32" y="908.0" text-anchor="start" fill="var(--dark)" font-size="12" font-family="system-ui, -apple-system, sans-serif" font-weight="600">
  <tspan x="32" y="908.0">Plaid MCP servers</tspan>
  </text>
  <circle cx="320.5" cy="903.0" r="5.5" fill="var(--secondary)"/>
<text x="24" y="937" text-anchor="start" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="24" y="937">Not for end-user accounts</tspan>
  </text>
  <circle cx="22" cy="984" r="5.5" fill="var(--secondary)"/>
<text x="32" y="988" text-anchor="start" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="32" y="988">Plaid</tspan>
  </text>
  <path d="M190,978.5 L195.5,984 L190,989.5 L184.5,984 Z" fill="var(--tertiary)"/>
<text x="200" y="988" text-anchor="start" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="200" y="988">Link, or a wallet like it</tspan>
  </text>
  <rect x="16.5" y="998.5" width="11.0" height="11.0" rx="2" fill="var(--dark)"/>
<text x="32" y="1008" text-anchor="start" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="32" y="1008">Own account</tspan>
  </text>
  <path d="M184.5,1009.5 L184.5,1003 L190,998.5 L195.5,1003 L195.5,1009.5 Z" fill="var(--darkgray)"/>
<text x="200" y="1008" text-anchor="start" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="200" y="1008">Inside the bank</tspan>
  </text>
  <path d="M22,1018.5 L27.5,1029.5 L16.5,1029.5 Z" fill="var(--gray)"/>
<text x="32" y="1028" text-anchor="start" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="32" y="1028">Other cited connection</tspan>
  </text>
  <circle cx="190" cy="1024" r="5.5" fill="var(--light)" stroke="var(--darkgray)" stroke-width="1.5"/>
<text x="200" y="1028" text-anchor="start" fill="var(--darkgray)" font-size="11" font-family="system-ui, -apple-system, sans-serif">
  <tspan x="200" y="1028">unknown</tspan>
  </text>
</svg>
<figcaption>Each tool sits in the rightmost lane the wiki can confirm. A tool that also reads may still sit in Pays or Moves. Connection marks are in the legend. Other holds tools the wiki cannot place in a lane.</figcaption>
</figure>

<details class="afr-cheatsheet-sources">
<summary>Sources and full table</summary>

| Tool | Read-only | Pays with approval | Moves money | How it connects | Sources |
|---|---|---|---|---|---|
| [Meta Muse](meta-muse.md) | Plaid path is read-only | Yes | unknown | [Plaid](../glossary.md#data-aggregator); [Link](../payments/link-wallet-for-agents.md) for purchases | [^pb-01][^sp-01] |
| [Grok Bot](grok-bot.md) | Finance (Plaid) path is read-only | Yes | unknown | Plaid; Link or [X Money](x-money.md) for purchases | [^gb-01][^gb-05] |
| [X Money](x-money.md) | unknown | Yes: pay with the X Money card | Yes: send money, with approval for each money move | Its own US account, through the Grok Bot plugin | [^xm-01] |
| [Claude Personal Finance](claude-personal-finance.md) | Yes | unknown | No: it cannot move, manage or invest money | Plaid | [^cl-01] |
| [Claude Duet](claude-duet.md) | unknown | Yes: a one-time card from a wallet like Link | No: it cannot move money between accounts | A wallet like Link | [^cl-03][^cl-04] |
| [Finances in ChatGPT](chatgpt-finances.md) | Yes | No: it cannot pay bills | No: it cannot move money | Plaid, and credit reports through Experian | [^oa-05] |
| [OpenAI dots](openai-dots.md) | unknown | Yes: a card saved on a merchant's website, with approval | unknown | A saved merchant card; [ChatGPT Wallet](../payments/chatgpt-wallet.md) is how the pages describe dots paying merchants | [^oa-07][^oa-08][^oa-01] |
| [Instinct](instinct.md) | Plaid path is read-only | Yes | unknown | Plaid; Link (Stripe says Link's agent wallet helps power its payments) | [^pb-09][^sp-01] |
| [Perplexity Personal CFO](perplexity-personal-cfo.md) | Yes | unknown | unknown | Plaid | [^pb-12][^pb-13] |
| [Nous](nous.md) | unknown | unknown | No: it cannot move or transfer money | unknown | [^ns-01] |
| [Gemini with Google Wallet](gemini-google-wallet.md) | Yes | unknown | No: it cannot move, manage or invest money | Google Wallet, and accounts linked to Wallet through Plaid | [^gg-01] |
| [Starling Assistant](starling-assistant.md) | unknown | Yes: a tap to approve each payment | unknown | Inside the bank | [^st-01] |
| [Plaid MCP servers](plaid.md) | Not for end-user accounts | Not for end-user accounts | Not for end-user accounts | Plaid, for developer diagnostics and a sandbox coding kit | [^pb-02] |
| [JPMorgan Smart Cash](jpmorgan-smart-cash.md) | unknown | unknown | Yes: move funds to maximize yield (news report) | Inside the bank | [^bl-01] |

</details>

## What can an agent do with each tool?

Every tool side by side. Each value is sourced on its own page, and `unknown` means no source confirms it yet. The same records are in [data/programs.json](../data/programs.json).

<details class="afr-cheatsheet-sources">
<summary>Full details for every tool</summary>

<!-- records: generated by afr generate from page headers; do not edit -->

| Tool | Operator | What an agent can do | What you control | Official MCP | Availability | Updated |
|---|---|---|---|---|---|---|
| [Finances in ChatGPT](chatgpt-finances.md) | OpenAI | Read balances, transactions, investments and liabilities from accounts connected through Plaid, and credit report data through Experian, to show a dashboard and answer questions. It cannot move money, pay bills, change account settings, make trades, change retirement contributions, open or close accounts or file taxes | You choose to connect each source, and Plaid and Experian are separate connections. You can disconnect Finances in Settings, which removes the connected data from ChatGPT, and view or delete financial memories. Temporary chats do not access connected accounts | unknown | In the US for Free, Go, Plus and Pro users on web, iOS and Android. Launched as a Pro preview on 2026-05-15, then Plus and Pro on 2026-06-25 and Free and Go from 2026-10-02 | 2026-11-18 |
| [Claude Duet](claude-duet.md) | Anthropic | Work as a proactive agent with its own virtual machine and browser, across connected apps. For purchases it pays with a one-time card from a wallet like Link from Stripe, limited to that merchant and amount. Trading securities and banking actions such as moving money between accounts stay off-limits even with approval | It shows the action, destination and content and waits for approval before sending a sensitive message, paying or deleting, with a separate automated check running alongside. Paying or sending money cannot be covered by a don't-ask-again rule. You approve a purchase in your Link app | unknown | Research preview on iOS, Android and claude.ai, included in Pro, Max and Ultra plans. It starts with Pro, Max and Ultra users in the US, through a waitlist | 2026-11-18 |
| [Claude Personal Finance](claude-personal-finance.md) | Anthropic | Read linked accounts through Plaid, read-only, to answer questions and build widgets, including account names, types and last four digits, up to 24 months of transactions, and balances and credit limits. It cannot move, manage or invest money | You sign in to your bank through Plaid and choose which accounts to share, and can link up to 16 banks. You can unlink a bank, turn the Plaid connector off or set it to ask before each read, and disconnect Claude at my.plaid.com. Claude asks before linking or unlinking a bank in a chat | unknown | In beta on Pro, Max and Ultra plans in the US only, on Claude web, desktop, iOS and Android. Not on Free, Team or Enterprise plans. Rolling out gradually | 2026-11-18 |
| [Gemini with Google Wallet](gemini-google-wallet.md) | Google | Answer money questions from Google Wallet data and from bank, card, loan and investment accounts linked to Wallet through Plaid, such as spending charts, forgotten subscriptions, budgets, and rewards and offers on cards and passes. Read-only, it cannot move, manage or invest money. From 2026-11-23, Search AI Mode can also opt in to connect Wallet and read spending and card-benefit tips, still without moving, managing or investing money | You choose whether to connect Wallet to Gemini and can turn the connection on or off at any time. You can unlink financial accounts in Google Wallet settings and manage Plaid connections in Plaid Portal. For Search AI Mode, you opt in to connect Wallet to Personal Intelligence | unknown | Rolling out from 2026-11-13 to Gemini app users in the US who are 18 or over, with a personal Google Account, in English, on the Gemini mobile and web apps. Google says it is being made available gradually. From 2026-11-23, users can opt in to connect Google Wallet to Personal Intelligence in Search AI Mode; the countries for that rollout are unknown | 2026-11-27 |
| [Tasks in Gemini](gemini-tasks.md) | Google | Shop and check out using Google Pay, with digital tokens on supported Mastercard and Visa cards. American Express is coming soon. Receipts and tracking land in Google Wallet | You can set a hard spending cap. Gemini is designed to ask for confirmation or pre-approval before clicking Buy. For a routine action you already trust, you can set that to Always allow. You can adjust task settings, disconnect apps, or delete chat history | unknown | Tasks in Gemini is rolling out free of charge in the US, Japan, Korea, Canada, Australia and India. A set of advanced features is starting in the US. The countries where checkout with Google Pay is available, beyond the US, are unknown | 2026-11-27 |
| [Grok Bot](grok-bot.md) | xAI | Through its Finance integration, answer questions about balances, spending, subscriptions and investments from bank, card and investment accounts linked through Plaid, read-only. Separately, pay at checkout with Stripe Link or X Money, with an approval step for each purchase | You choose whether to link accounts and can unlink them anytime. A financial connection is read-only. A Link purchase shows the amount to Allow or Deny, and every X Money action that moves money needs its own approval. After a bank or brokerage connector returns data, the Bot asks before sharing it anywhere else | Yes | The Finance integration was announced on 2026-09-26 and needs Grok Bot 0.49 or newer. Plans and regions for it are unknown | 2026-11-22 |
| [Instinct](instinct.md) | Instinct | Read balances and transactions from accounts connected through Plaid, read-only, alongside connections such as email and calendar, to spot patterns and flag what needs attention. Stripe says Link's agent wallet helps power its payments | You authenticate your accounts through Plaid when Instinct prompts you, and Plaid says Instinct asks for approval before taking next steps such as drafting a dispute | unknown | Plaid's post of 2026-11-18 says US consumers can connect accounts, with thousands of US users. CNBC describes Instinct as invitation-only | 2026-11-22 |
| [JPMorgan Smart Cash](jpmorgan-smart-cash.md) | JPMorgan Chase | Predict a user's cash flow and move funds to maximize yield, as the bank's CFO described it (news report) | unknown | unknown | A targeted pilot that began in the weeks before 2026-10-13 (news report) | 2026-11-14 |
| [Meta Muse](meta-muse.md) | Meta | Give personalized money guidance from accounts you connect through Plaid, such as balances, transactions, investment holdings and mortgage information. Separately, with your approval each time, buy online using Link by Stripe or a card saved in its Secure Credential Store. From 2026-11-24, shop Walmart through the Walmart Agent Gateway, shop Gopuff once you approve the order, and shop JD Sports in the UK | You choose whether to connect accounts, and you can manage Plaid-powered connections in Plaid Portal. Muse always asks for your approval before completing a purchase, and you can disconnect a Connector at any time in Settings. On Walmart, you set an Agent Profile spending limit and approve purchases | unknown | Launched 2026-09-08 with Plaid-powered account connections in its finance features. From 2026-11-24 it can shop Walmart through the Walmart Agent Gateway, and JD Sports says Muse launched in the UK that day for people aged 18 or over | 2026-11-27 |
| [Nous](nous.md) | Nous (Nous for your House Limited, England) | Track household bills and subscriptions, switch energy, broadband, mobile and car insurance providers, cancel subscriptions, and handle other household admin. It cannot move or transfer money | Choose a savings mode (Manual, Balanced or Freedom) for how much Nous decides on its own, and set and change its permissions at any time | unknown | Live in the UK for one address per household, with a free tier and a paid Premium tier | 2026-11-15 |
| [OpenAI dots](openai-dots.md) | OpenAI | Work as an always-on agent on its own cloud computer, using plugins to connect to apps. A dot can buy with a card you saved on a merchant's website, with your approval, which may be given in advance when it specifically covers the purchase | Dots start with built-in rules for which actions need approval each time, which can be approved in advance and which need none. Custom Rules let you allow, require approval for, or block specific actions, and auto-review checks actions that could affect your accounts. Sensitive tasks such as changing a password stay with you, and you can pause a dot at any time | unknown | Announced 2026-09-29 and rolling out to Pro users aged 18 and over outside the EEA, Switzerland and the UK, and to Business Premium users in supported regions. Enterprise, Edu and Healthcare workspaces get it by default from 2026-11-18 unless an admin opts out | 2026-11-27 |
| [Perplexity Personal CFO](perplexity-personal-cfo.md) | Perplexity | According to Plaid, answer questions about spending, subscriptions and balances from accounts connected through Plaid, and build tools such as a budget tracker, net worth view or debt payoff plan. Plaid says access is read-only | According to Plaid, you choose which accounts to share and access is read-only. In the EU, Plaid provides the connection as a regulated account information service through Plaid B.V. | unknown | According to Plaid, US users can connect accounts through Plaid, and Pro and Max users get Perplexity Computer features, from 2026-04-09. Plaid says people in 17 European countries can use Personal CFO from 2026-11-12 | 2026-11-18 |
| [Plaid MCP servers](plaid.md) | Plaid | Developer work only: production diagnostics and analytics for a Plaid customer's team, and a local sandbox MCP for building. No access to end users' accounts | The Dashboard MCP needs a Plaid OAuth token, and the team must be approved for Production access | Yes | The Dashboard MCP is under active development. Plaid says breaking changes may occur and support is limited | 2026-11-18 |
| [Starling Assistant](starling-assistant.md) | Starling Bank | Set up a payment from a voice or text prompt such as "Pay the plumber £200", for the customer to approve. The assistant also analyses direct debits and subscriptions, builds personalised budgets and creates Spaces | The customer authorises each payment with a screen tap | unknown | Announced 2026-11-13 and rolling out to all retail customers by the end of 2026, so not yet available to everyone. Small business customers will soon get a similar feature for paying invoices, with no date given | 2026-11-18 |
| [X Money](x-money.md) | X Payments LLC, with Cross River Bank holding the deposit accounts | Through the Grok Bot plugin and X Money's hosted MCP server, view the balance and transaction history, use the X Money card for purchases, and send or request money with users on X. X Money decides which of these actions each account gets | Connect with a code or QR code approved with a passkey in the X Money app, and revoke at X > Money > Settings > Connections. Every action that moves money needs its own Approve or Cancel, X Money refuses calls that were not approved, agents have separate limits, and higher-risk transfers stay in the X app | Yes | Rolling out in the US since 2026-07-27, first to Premium and Premium+ subscribers. X's pages now say it is available to select users who are 18 or older and live in the 50 states or DC. Interest is not available in New York | 2026-11-18 |

<!-- /records -->

</details>

## How should an agent choose a way to pay?

Affirm and Consumer Reports published a draft Payment Choice Framework: a set of written instructions that helps an AI assistant recommend how to pay for a purchase. It asks the assistant to check terms, compare costs on the same assumptions, consider what could go wrong, rule out poor fits, and explain the recommendation. The best suggestion might be to finance, pay in full, choose another provider, wait, or not buy.[^cr-01] They tested it against Consumer Reports' [Consumer Finance AI Standard](../glossary.md#consumer-finance-ai-standard).[^cr-01]

The [GitHub repository](https://github.com/consumer-reports-innovation-lab/payment-choice-framework) describes the draft as "for review only. Not for real world use."[^cr-02] The case study says the framework is not a financial adviser or a finished product, cannot access accounts or make purchases on its own, and that further testing is needed before use in real-world consumer experiences.[^cr-01]

Testing used 30 payment-advice tasks, with and without the framework, across four model configurations. Each model attempted the 30 tasks three times per condition, producing 720 conversations. Pass rates were higher with the framework. Averaged across the four models, the pass rate was 48.6% without it and 71.8% with it, an increase of 23.2 percentage points. The case study says these results do not establish improved consumer outcomes or readiness for consumer use.[^cr-01]

## How it fits together

- **The agent.** A personal agent, such as Muse, reads account data you choose to share.[^pb-01]
- **The connection.** A [data aggregator](../glossary.md#data-aggregator), such as Plaid, links the agent to your bank with your permission.[^pb-01] This is a form of [open banking](../glossary.md#open-banking). [How a Plaid connection works](plaid.md#how-does-a-plaid-connection-work) walks through the steps.
- **The bank.** Banks decide what outside agents can do. News reports say most allow read-only access at best, while some build their own AI tools.[^bl-01][^bl-02]

Some of these agents also pay. Stripe's [Link wallet for agents](../payments/link-wallet-for-agents.md) is used by Muse, Grok Bot and Instinct, Claude Duet pays with a one-time card from a wallet like it, and OpenAI's dots can pay merchants through [ChatGPT Wallet](../payments/chatgpt-wallet.md).[^sp-01][^cl-03][^oa-01] Copilot, Alexa+ and Apple's assistants have no page, because no primary source is cited for them yet.

## Related pages

- [Robinhood Agentic Credit Card](../payments/robinhood-agentic-credit-card.md): a card your agent can spend with, with limits you set.
- [Merchants and outside agents](../payments/merchants-and-outside-agents.md): merchants whose terms forbid AI agents.
- [Mandates and data access](../rails/mandates-and-data-access.md): the US data-rights rule (often called 1033) in the background.
- [Payments](../payments/README.md): how agents pay.

Not investment advice.

## Sources

[^pb-01]: [Plaid powers Meta's new AI agent, Muse - Plaid](../sources/pb-01.md). Plaid, official, retrieved 2026-11-12.
[^wm-01]: [Walmart’s Black Friday Deals Continue. Meta’s Muse Can Now Shop Them, Too.](../sources/wm-01.md). Walmart, official, retrieved 2026-11-25.
[^jd-01]: [JD partners with Meta as it launches Muse in UK](../sources/jd-01.md). JD Sports Fashion plc, official, retrieved 2026-11-25.
[^gb-01]: [Grok Bot on X: "Grok Bot now connects to your finances" (with follow-up post)](../sources/gb-01.md). Grok Bot (@bot on X), official, retrieved 2026-11-18.
[^gb-05]: [Grok Bot changelog](../sources/gb-05.md). xAI, official, retrieved 2026-11-18.
[^xm-01]: [X Money plugin README (cursor/plugins, third_party/x-money)](../sources/xm-01.md). cursor/plugins (GitHub), official, retrieved 2026-11-18.
[^cl-01]: [Use Personal Finance in Claude (Claude Help Center)](../sources/cl-01.md). Anthropic, official, retrieved 2026-11-18.
[^cl-03]: [Claude Duet safety, privacy and security](../sources/cl-03.md). Anthropic, official, retrieved 2026-11-18.
[^cl-04]: [Introducing Claude Duet](../sources/cl-04.md). Anthropic, official, retrieved 2026-11-18.
[^oa-05]: [Finances in ChatGPT (OpenAI Help Center)](../sources/oa-05.md). OpenAI, official, retrieved 2026-11-18.
[^oa-07]: [Dots privacy, security, and safety FAQs (OpenAI Help Center)](../sources/oa-07.md). OpenAI, official, retrieved 2026-11-18.
[^oa-08]: [Introducing dots (OpenAI)](../sources/oa-08.md). OpenAI, official, retrieved 2026-11-18.
[^pb-09]: [Instinct gets the full financial picture with Plaid](../sources/pb-09.md). Plaid, official, retrieved 2026-11-18.
[^pb-12]: [Plaid and Perplexity expand integration to power personalized financial insights](../sources/pb-12.md). Plaid, official, retrieved 2026-11-18.
[^pb-13]: [Perplexity brings Personal CFO to Europe with Plaid](../sources/pb-13.md). Plaid, official, retrieved 2026-11-18.
[^ns-01]: [Frequently asked questions - Nous](../sources/ns-01.md). Nous, official, retrieved 2026-11-15.
[^gg-01]: [Connect Google Wallet to Gemini for personal finance insights](../sources/gg-01.md). Google, official, retrieved 2026-11-18.
[^gg-03]: [A more tailored Google Search that’s uniquely yours](../sources/gg-03.md). Google, official, retrieved 2026-11-25.
[^gg-04]: [Put Gemini to work for you](../sources/gg-04.md). Google, official, retrieved 2026-11-27.
[^st-01]: ['Talk to transact': Starling customers can use their voice to send money](../sources/st-01.md). Starling Bank, official, retrieved 2026-11-18.
[^pb-02]: [Resources - MCP Server - Plaid Docs](../sources/pb-02.md). Plaid Docs, official, retrieved 2026-11-12.
[^bl-01]: [JPMorgan blocks outside AI agents like Muse, Instinct from account access](../sources/bl-01.md). CNBC, third-party, retrieved 2026-11-12.
[^bl-02]: [Scoop: Unvetted AI agents are accessing U.S. bank accounts](../sources/bl-02.md). Axios, third-party, retrieved 2026-11-12.
[^bl-08]: [Five Major Banks Are Blocking AI Agents From Logging Into Customer Accounts](../sources/bl-08.md). Yahoo Finance, third-party, retrieved 2026-11-12.
[^ci-01]: [Citi Online User Agreement (Section H: Use of Third-party AI Agents)](../sources/ci-01.md). Citi, official, retrieved 2026-11-20.
[^jp-02]: [Digital Services Agreement (J.P. Morgan Chase)](../sources/jp-02.md). JPMorgan Chase, official, retrieved 2026-11-20.
[^sp-01]: [Stripe helps Meta Muse shop with Link](../sources/sp-01.md). Stripe, official, retrieved 2026-11-18.
[^oa-01]: [Introducing ChatGPT Wallet](../sources/oa-01.md). OpenAI, official, retrieved 2026-11-15.
[^cr-01]: [A Consumer-First Standard for AI Payments (Affirm and Consumer Reports case study)](../sources/cr-01.md). Affirm and Consumer Reports, official, retrieved 2026-11-23.
[^cr-02]: [GitHub - consumer-reports-innovation-lab/payment-choice-framework](../sources/cr-02.md). Consumer Reports Innovation Lab (GitHub), with Affirm, official, retrieved 2026-11-23.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20personal-money%2FREADME.md&body=Page%3A%20personal-money%2FREADME.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
