---
type: personal-money
title: Banks and outside agents
summary: What news reports say about big US banks blocking or limiting outside AI agents, including Chase's block on agents shopping with a card number, the read-only middle ground, and the US data-rights rule in the background.
page_status: current
last_verified: '2026-11-23'
---

# Banks and outside agents

Most of what is known here comes from news reports, not from the banks. Each line says which.

## The short version

- Several big US banks block outside AI agents that log in with a customer's password.[^bl-01][^bl-02][^bl-08]
- Most allow, or are moving toward, read-only access through approved data connections.[^bl-02] See [open banking](../glossary.md#open-banking).
- JPMorgan Chase also blocks agents that shop with a card number a customer gives them, according to a Wall Street Journal report.[^bl-12][^bl-13] See [shopping with a card](#what-about-shopping-with-a-card).
- Some banks are building their own AI tools, such as [JPMorgan Smart Cash](jpmorgan-smart-cash.md)[^bl-01] and, in the UK, [Starling Assistant](starling-assistant.md).[^st-01]
- Citi and JPMorgan Chase now say in their own user agreements that if you give an outside AI agent your login, they treat the agent's actions as yours.[^ci-01][^jp-02] See [the Citi and Chase terms](#what-do-the-citi-and-chase-user-agreements-say).

## Bank by bank (news reports)

- **JPMorgan Chase.** Its CEO said it will not allow outside agents into customer accounts. A spokeswoman confirmed the bank blocks external AI agents from acting for retail customers, and said it supports customer-authorized data sharing through open banking providers. CNBC says agents can see some data, such as balances, read-only through Plaid or another connector, but cannot send money or pay a bill. There is no timeline for more access.[^bl-01] The Wall Street Journal later reported that Chase also blocks agents when consumers give the bots their card information, according to people familiar with the matter. See [shopping with a card](#what-about-shopping-with-a-card).[^bl-12]
- **Morgan Stanley.** Has begun blocking third-party agents from its platforms, according to people familiar with the decision. A spokesperson said the bank had not seen "rogue AI agents accessing our platforms."[^bl-02]
- **Citi.** Says it does not let third-party AI agents log into customer accounts or transact directly, but allows some read-only access through approved open-banking providers, as reported by Yahoo Finance.[^bl-08]
- **Bank of America and Wells Fargo.** Named among the banks limiting third-party agent access. The cited reports give no bank-specific detail.[^bl-02][^bl-08]
- **Schwab.** Covered on the [overview](../overview.md), because it blocks some agents while running its own MCP pilot.

## What do the Citi and Chase user agreements say?

These two come from the banks' own terms, not from news reports. Both say an outside AI agent you give your login to acts with your authority.

**Citi.** Its Online User Agreement says it was last updated November 2026 to add a new Section H on third-party AI agents. The exact day is unknown.[^ci-01]

- Section H cautions customers against using any third-party AI agent to access their accounts or use digital services through Citi Online or Citi Mobile.[^ci-01]
- If a customer gives their Online Credentials to a third-party AI agent, or otherwise lets it access their accounts, Citi says it will consider any access and actions taken by the agent as authorized by the customer.[^ci-01]
- Citi says the same applies if those credentials are further shared, leaked or otherwise distributed to other persons or AI agents.[^ci-01]
- Citi says it has no responsibility to investigate the authority or validity of such actions, even if they conflict with the customer's instructions to the agent. It says the customer is responsible for errors from the agent's incorrect interpretation or execution, and for unintended actions or actions beyond the authority given.[^ci-01]
- Citi says that by letting an agent access their accounts the customer authorizes Citi to disclose their information, including sensitive personal information, to the agent, and that the Citi Privacy Notice does not apply to the agent.[^ci-01]
- The terms say they do not apply to AI agents, tools or features that Citi itself provides.[^ci-01]

**JPMorgan Chase.** Its Digital Services Agreement is marked "Last updated: November 2026". The exact day is unknown.[^jp-02]

- A notice says that, effective 2026-10-27, third parties, including External AI, automated tools or data aggregators, are prohibited from using the customer's Login Credentials to access Chase's digital platforms or the customer's accounts or services.[^jp-02]
- Chase says it permits third-party applications and tools, including External AI, to access customer account data through approved application programming interfaces (APIs) with the customer's authorization.[^jp-02]
- Chase tells customers who have shared Login Credentials with any third party to change them.[^jp-02]
- If a customer permits, directs or facilitates a third party, including External AI, to access their accounts, Chase says the customer is deemed to expressly authorize that third party to transact in the account and the actions it initiates. Chase says it will treat that party's actions or instructions as evidence of the customer's authorization.[^jp-02]
- Chase says the customer is responsible for resulting errors, including unintended actions, transactions the customer did not intend and actions that exceed the authority given.[^jp-02]
- The agreement says that, subject to applicable law, the customer assumes the entire risk for the fraudulent, unauthorized or otherwise improper use of their login credentials.[^jp-02]
- The wiki read an excerpt of the agreement, not the whole document.[^jp-02]

## What do reports and a regulator say about other banks' new terms?

- TechCrunch reported on 2026-11-18 that Citi had changed its terms of service that week.[^tc-01]
- TechCrunch says JPMorgan and Bank of America "announced similar policies last month", and that PNC changed its terms on the day of the article.[^tc-01]
- TechCrunch says Citizens emailed its customers that week, warning that they are on the hook for anything their AI assistant does, according to an email TechCrunch saw.[^tc-01]
- These are TechCrunch's accounts. The wiki has not seen Bank of America's, Citizens' or PNC's own wording, so those details are unknown, and PNC's wording is unknown.[^tc-01]
- The Monetary Authority of Singapore said on 2026-11-19 that it would not advise giving personal agents login credentials to financial accounts, as there is insufficient assurance of safety.[^ma-01] See [Mandates and data access](../rails/mandates-and-data-access.md#what-have-a-regulator-and-two-banks-said-about-agent-authority).
- In a 16 November 2026 speech, Federal Reserve Governor Michael S. Barr said major banks now report finding AI agents attempting to take actions in retail customer accounts, without the bank being able to verify authenticity, consent, and alignment with customer instructions. He called for strict authentication, explicit consent verification for specific actions, and technical controls limiting agent capabilities.[^fr-01]

## Why banks say they are worried

- Banks are finding unvetted agents inside customer accounts. These usually log in with the customer's permission and password, which most banks' rules forbid. Some agents appear to act on their own, beyond the user's instructions.[^bl-02]
- Many banks cannot tell whether account activity is directed by the user.[^bl-02]
- Reuters could not independently verify the specific incidents, according to Yahoo Finance.[^bl-08]

## The middle ground

Reading data is one thing, and moving money is another. Banks already allow read-only connections for budgeting apps.[^bl-02] Yahoo Finance says a standard way to give agents scoped, limited power to transact does not exist yet.[^bl-08] For a card-based approach with limits, see the [Robinhood Agentic Credit Card](../payments/robinhood-agentic-credit-card.md).

Banks are also getting tools to tell agents apart. On 2026-11-16 Plaid launched [Agent Detection](../glossary.md#agent-detection), which lets a bank see whether a session is a person or an AI agent and which AI provider the agent is linked to, so it can decide how to handle each one.[^pb-06]

## What is the JPMorgan and Plaid data agreement?

On 2025-09-16 JPMorganChase and Plaid announced a renewed data access agreement that continues to let their shared customers use products that rely on their bank data. The press release says the agreement includes a pricing structure and sets out commitments on safe, secure and consistent access, and that it would not affect Plaid's current customer agreements and pricing. The release does not give the price.[^jp-01] The price is unknown. Plaid is the [data aggregator](../glossary.md#data-aggregator) behind several personal agents: see [Plaid](plaid.md#which-assistants-connect-through-plaid).

## What about shopping with a card?

On 2026-11-13 the Wall Street Journal reported, citing people familiar with the matter, that JPMorgan Chase has been blocking agents when consumers give the bots their card information. The same report says Chase has been slow to allow other solutions that rival banks are trying, and has been at odds with the Visa and Mastercard [agentic tokens](../glossary.md#agentic-token) that Stripe's Link uses.[^bl-12] PYMNTS summarized the report the same way.[^bl-13]

- **Other banks.** The report says cards from Bank of America, Capital One and Citigroup are being used by agents when consumers enable them.[^bl-12][^bl-13]
- **Link and Chase cards.** The report says Stripe's mechanism can be used for Chase cards and other issuers. For those, Stripe's wallet uses a one-time [virtual card](../glossary.md#virtual-card) for the purchase amount, then charges the shopper's own card.[^bl-12] See [Link wallet for agents](../payments/link-wallet-for-agents.md#does-link-work-with-chase-cards).
- **ChatGPT Wallet and Chase.** OpenAI's help page says that to add a Chase card to [ChatGPT Wallet](../payments/chatgpt-wallet.md#how-do-i-add-a-chase-card), you must be the primary cardholder and approve the connection in the Chase mobile app.[^oa-02] The report above is about agents given a card number, and it does not mention Wallet. No cited source says how the two relate.

## The data-rights rule (background)

Rules are background here, not a focus. The CFPB's personal financial data rights rule (Section 1033) went through a reconsideration notice in August 2025.[^pb-05] A November 2026 POLITICO report says bank lobbyists see the rule, then at the White House budget office, as a possible way to regulate AI agents.[^pb-04] More on [Mandates and data access](../rails/mandates-and-data-access.md).

## Unknown

Primary statements from most of these banks, and the price in the JPMorgan and Plaid agreement. Whether Chase's card block applies to agents that use ChatGPT Wallet is also unknown. The exact days on which Citi's and Chase's terms changed are unknown, and so are Bank of America's, Citizens' and PNC's own wording. This is listed on [gaps](../gaps.md).

All pages: [Personal money agents](README.md).

## Sources

[^bl-01]: [JPMorgan blocks outside AI agents like Muse, Instinct from account access](../sources/bl-01.md). CNBC, third-party, retrieved 2026-11-12.
[^bl-02]: [Scoop: Unvetted AI agents are accessing U.S. bank accounts](../sources/bl-02.md). Axios, third-party, retrieved 2026-11-12.
[^bl-08]: [Five Major Banks Are Blocking AI Agents From Logging Into Customer Accounts](../sources/bl-08.md). Yahoo Finance, third-party, retrieved 2026-11-12.
[^bl-12]: [AI bots are using credit cards. Banks are racing to keep up. (The Wall Street Journal, via Mint)](../sources/bl-12.md). The Wall Street Journal (syndicated on Mint), third-party, retrieved 2026-11-19.
[^bl-13]: [JPMorgan Stops AI Agents From Using Customer Credit Cards (PYMNTS)](../sources/bl-13.md). PYMNTS, third-party, retrieved 2026-11-19.
[^st-01]: ['Talk to transact': Starling customers can use their voice to send money](../sources/st-01.md). Starling Bank, official, retrieved 2026-11-18.
[^ci-01]: [Citi Online User Agreement (Section H: Use of Third-party AI Agents)](../sources/ci-01.md). Citi, official, retrieved 2026-11-20.
[^jp-02]: [Digital Services Agreement (J.P. Morgan Chase)](../sources/jp-02.md). JPMorgan Chase, official, retrieved 2026-11-20.
[^tc-01]: [More banks say customers using AI agents are on their own — even if they get hacked (TechCrunch)](../sources/tc-01.md). TechCrunch, third-party, retrieved 2026-11-20.
[^ma-01]: [Keynote address by the Managing Director of the Monetary Authority of Singapore at the Singapore FinTech Festival 2026](../sources/ma-01.md). Monetary Authority of Singapore, official, retrieved 2026-11-20.
[^fr-01]: [Speech by Governor Barr: Some Potential Financial Stability Implications of Artificial Intelligence](../sources/fr-01.md). Board of Governors of the Federal Reserve System, official, retrieved 2026-11-23.
[^pb-06]: [Introducing Agent Detection: building trust in the age of agentic finance](../sources/pb-06.md). Plaid, official, retrieved 2026-11-18.
[^jp-01]: [JPMorganChase and Plaid announce an extension to their data access agreement](../sources/jp-01.md). JPMorganChase, official, retrieved 2026-11-18.
[^oa-02]: [Making purchases with ChatGPT Wallet](../sources/oa-02.md). OpenAI Help Center, official, retrieved 2026-11-19.
[^pb-05]: [Federal Register](../sources/pb-05.md). Federal Register, official, retrieved 2026-11-12.
[^pb-04]: [AI agents scramble banks' fight with fintechs](../sources/pb-04.md). POLITICO, third-party, retrieved 2026-11-12.

---

<!-- footer: generated by afr footer; do not edit -->
[Suggest a correction](https://github.com/edyavno/eds-agentic-finance-rails/issues/new?title=Correction%3A%20personal-money%2Fbanks-and-outside-agents.md&body=Page%3A%20personal-money%2Fbanks-and-outside-agents.md%0A%0AWhat%20is%20wrong%3A%0A%0AWhat%20is%20right%3A%0A%0ASource%20link%20%28official%20page%20preferred%29%3A%0A) (opens a GitHub issue)
