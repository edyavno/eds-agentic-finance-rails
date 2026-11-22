# Log

Append-only record of ingests, queries filed back, lint passes and reviews. Newest at the bottom. Never edit or delete earlier entries; lint fails if the committed log is not a prefix of the current one.

Format: `## [YYYY-MM-DD] operation | subject`, then a few bullet points.

## [2026-11-12] ingest | source batch 1
- 103 source cards written to sources/ (summary, fingerprint, short verified quotes; no full copies).

## [2026-11-12] draft | launch broker pages
- Drafted providers/ pages for Robinhood, Coinbase, Webull, Interactive Brokers and Alpaca from batch 1. All page_status: draft.
- Alpaca endpoint updated from "unknown" to https://api.alpaca.markets/mcp based on Alpaca's agentic repo (al-03).

## [2026-11-12] lint | first pass
- Generated files rebuilt; lint run by the publisher. Results are reported to the maintainer, not stored here.

## [2026-11-12] draft | feedback discovery
- Documented the site address and the GET /feedback then POST JSON recipe in AGENTS.md, README.md, llms.txt and index.md.

## [2026-11-12] process | drop per-page review status
- Removed the per-page draft/reviewed/verified step. page_status is now current, stale or archived. last_verified and stale checks stay.

## [2026-11-13] edit | front-page wording
- Headline is now "Connect AI agents to money, safely". Subhead covers how brokers, banks and payment networks let AI agents trade, pay and manage money, and who approves what, starting with five brokers. Mirrored in README.md, index.md and llms.txt.
- Removed the leftover "Draft. Not yet reviewed." callout from the five launch provider pages. The sourcing sentence stays.

## [2026-11-13] ingest | advisor tools, Schwab RIABiz, Coinbase feedback docs
- Retrieved and ingested source cards bl-11, an-01, an-02, ni-01, ni-02, nv-01, wf-01, ws-01, bd-01 and cb-09 (summaries, fingerprints, short verified quotes; no full copies).
- Added the advisors/ section (README plus pages for Claude for Financial Advisors, Nitrogen and Wells Fargo AI Teammate). Front-page tab, schema type `advisor`, generated index, directory and llms.txt updated.
- Updated overview.md with the RIABiz Schwab report (retail / thinkorswim; RIAs not included). Noted that the article's Key Points box is labeled AI generated and that the Anthropic headline framing is opinion.
- Updated providers/coinbase.md with the official `coinbase_feedback_submit` tool from Coinbase MCP docs. Official docs do not document an HTTP path named `/feedback`.

## [2026-11-14] ingest | ERC-8004 on the Agent identity rail
- Retrieved and ingested official source card id-07 from https://eips.ethereum.org/EIPS/eip-8004 (summary, fingerprint, short verified quotes; no full copy).
- Added an ERC-8004 (Trustless Agents) row to rails/agent-identity.md, with status Draft as stated on the official page, and a short note under "Why it matters for finance" that the ERC says payments are orthogonal and gives x402 feedback examples.
- Eco registration figures were not added; the cited Dune dashboard was not opened and confirmed.

## [2026-11-14] ingest | remaining prepared source cards
- Folded previously uncited batch cards into existing pages with footnotes: blockers (bl-07, bl-09, bl-10), Coinbase docs index (cb-06), FINRA (id-05, id-06), PrimeXBT watchlist (np-02), prior-art directories as leads only (pa-01 through pa-10), Muse coverage (pb-03), Stripe MCP (pm-09), Public (pu-01, pu-03, pu-04, pu-07, pu-08, pu-09), Robinhood (rh-05, rh-06, rh-08, rh-11, rh-12), tastytrade (tt-02, tt-04), and Webull (wb-01, wb-04, wb-08).
- Prior-art cards are cited only in gaps.md as leads, not as evidence for provider fields. The pa-01 referral/affiliate links were not reused.
- Front-page coming-soon tabs were not changed.

## [2026-11-14] site | front page search and plain English
- Added a short, dated answer under the front-page headline, taken from the comparison and provider pages. The Coinbase approval line matches the comparison page (portfolios picked at sign-in, which can include the main account).
- Replaced the three coming-soon tabs with a line linking existing rails pages. Brokers and Advisor agents stay as tabs. Payments and personal money agents were not flipped to live.
- Front table now uses plain-English labels; endpoint URLs stay on provider and Build pages.
- Search setup: page summaries as meta descriptions, branded titles, one SITE_URL for canonicals (preview default; production build fails if unset), home og:url is /, sitemap drops /claude, /tags/ and /log, JSON-LD WebSite and Organization on home and Dataset on the directory, visible "No affiliate links" line. Preview stays noindex.
- Added the plain-English writing-style rule to AGENTS.md (style section and lint checklist) and the README. Other wiki pages were not rewritten in this round.

## [2026-11-14] edit | plain-English pass
- Rewrote overview.md (especially Public, tastytrade, Schwab, and PrimeXBT), and the Coinbase, Robinhood, Webull, Interactive Brokers, and Alpaca provider pages, following the AGENTS.md style rule. Light pass on rails/local-mcp-and-cli.md and rails/mandates-and-data-access.md.
- Facts, numbers, links, and footnote citations were kept. No new facts were added.


## [2026-11-14] edit | glossary and trim pass
- Added glossary.md with short, general definitions of recurring terms, and linked it from the overview, index, llms.txt, and the front page.
- Trimmed overview, the five launch-broker provider pages, rails/local-mcp-and-cli.md, rails/mandates-and-data-access.md, and the front-page short answer so first-use terms link to the glossary. Facts, numbers, links, and footnotes were kept.
- Added an AGENTS.md style rule: define terms in glossary.md and link them on first use, instead of writing long inline explanations.

## [2026-11-14] edit | Payments and Personal money agents sections
- Added payments/ (README plus visa-intelligent-commerce, mastercard-agent-pay, agentic-commerce-protocol, stripe, paypal, x402, ap2, robinhood-agentic-credit-card) and personal-money/ (README plus meta-muse, plaid, jpmorgan-smart-cash, banks-and-outside-agents). Built only from existing source cards pm-01 to pm-15, rh-09, rh-10, cb-01, pb-01 to pb-05, bl-01, bl-02 and bl-08. No new cards; prior-art cards were not used as evidence.
- New schema/program.schema.json for program records (operator, agent_can, user_controls, mcp_server, endpoint, availability, field_sources). Page types payment and personal-money added to page.schema.json. Generated data/programs.json and directory tables.
- Marked unknown where no source confirms a value: Mastercard MCP, endpoint and availability; Visa production MCP address; ACP and x402 user controls and MCP; AP2 MCP; Muse MCP and endpoint; JPMorgan Smart Cash controls, MCP and endpoint. JPMorgan Smart Cash rests on one news report (single-source warning).
- Glossary: agentic commerce, data aggregator, open banking, payment token, stablecoin, virtual card.
- Front-page Payments and Personal money agents tabs flipped live on the maintainer's instruction of 2026-11-14; "What we cover" overview added.

## [2026-11-15] edit | front page reorganization and wiki navigation pass
- Front page cut to a short version of the README (hero, What we cover, Start here, For AI agents, footer). The "No affiliate links / not investment advice" line moved from the hero to the footer.
- Moved, not removed: the Trading short answer and its broker list now open directory.md (generated, with footnotes from the comparisons rows: rh-01, rh-04, cb-03, cb-07, wb-07, wb-03, ib-01, ib-07, ib-06, al-05, al-03, al-01, plus each provider's first status source). Front-page stats and "What changed" moved to a generated changelog/README.md. The approval-model cards are on approval-models/README.md, now linked from the directory and rails/README.md.
- Generated record tables (what an agent can do, what you control, official MCP, last verified) added to payments/README.md and personal-money/README.md between records markers.
- Glossary: approval model, human in the loop, rails. README style section now matches the AGENTS.md glossary rule. AGENTS.md lists the new generated files.
- No last_verified dates were bumped; no facts or source cards changed.

## [2026-11-15] edit | approved organization pass: Trading page, FAQ, answer-first openings
- directory.md renamed to "Trading" in titles, nav and link text; the /directory URL is unchanged. It now covers brokers only. The payments, personal-money and advisor tables were removed from it; their operator and availability columns moved into the generated records tables on payments/README.md and personal-money/README.md, so no field was lost. Advisor summaries, last_verified and page status remain on advisors/README.md and each advisor page.
- New faq.md (six Q&As). Every answer is footnoted from cards already cited on existing pages (al-01, al-02, al-03, al-05, cb-01, cb-03, cb-07, ib-01, ib-06, ib-07, rh-01, rh-04, rh-09, wb-02, wb-03, wb-07, pm-01, pm-05, pm-06, pm-08, bl-01, bl-02, bl-08, an-02, ni-01, wf-01). Unknowns kept as unknown (paper options for Robinhood, Coinbase and IBKR; Webull Cloud MCP sandbox; Wells Fargo AI Teammate trading). last_verified set to 2026-11-12, the earliest underlying check.
- Answer-first openings added to rails/agent-identity.md, rails/agent-payments.md, rails/mandates-and-data-access.md, build/human-in-the-loop.md and the three advisors pages, using footnotes already defined on each page. last_verified not bumped.
- "Starting with five brokers." dropped from the README lede. README, overview.md and the generated index and llms.txt link the FAQ.
- No facts or source cards changed.
- Public copy: dropped the phrase "No affiliate links." and its variants from the README, payments/README.md, personal-money/README.md, gaps.md, changelog/2026-11-14.md and the front-page footer, on the maintainer's request of 2026-11-15. The footer now reads "Not investment advice." The no-affiliate-links rule for contributors in AGENTS.md and the lint check are unchanged.

## [2026-11-15] edit | AGENTS.md is now a reader's guide
- AGENTS.md now covers reading only: where to start (llms.txt, index.md, data/*.json), how source cards and footnotes work, citing the page and the card, saying "unknown", checking page_status and last_verified, and how to send corrections or /feedback notes.
- Removed an internal maintenance file. The analyses section page, README, gaps.md, index.md and llms.txt descriptions updated to match.
- No facts, footnotes, source cards or last_verified dates changed.

## [2026-11-15] edit | feedback instructions for agents
- AGENTS.md gained a "Giving feedback" section (#giving-feedback) with the fields, limits and replies of /feedback, and a line that the endpoint records the sender's IP address with each note. README and llms.txt now point there with one line.
- No facts, footnotes, source cards or last_verified dates changed.

## [2026-11-15] edit | agent notes pointer kept to agent files
- The pointer for agent notes now appears only in llms.txt, llms-full.txt and the AGENTS.md reader's guide. README, index.md, the front page and the site footer no longer mention it. README's "Corrections and feedback" heading is now "Corrections".
- No facts, footnotes, source cards or last_verified dates changed.

## [2026-11-15] edit | public wording pass
- AGENTS.md and README.md now give the site address https://agenticfinancerails.com.
- Changelog entries, gaps.md and three source cards (pa-01, pa-08, np-02) lost process notes; source card Notes now read "This card is a pointer, not a copy. Archive link: unknown."
- This log stays in the repo but is no longer published on the site. index.md no longer links it.
- No facts, footnotes or last_verified dates changed.

## [2026-11-15] edit | log wording
- Reworded four earlier entries in this log so they no longer mention private notes, an old site address or an internal file name. A one-time, recorded exception to the append-only rule covered this change.
- No facts, footnotes, source cards or last_verified dates changed.

## [2026-11-15] release | public launch
- The site is now public at https://agenticfinancerails.com. www.agenticfinancerails.com, edsagenticfinancerails.com, edsagenticfinancerails.wiki and edsagenticfinancerails.xyz redirect there.
- No facts, footnotes, source cards or last_verified dates changed.

## [2026-11-15] edit | overview wording for Public
- overview.md now introduces Public as "Not yet profiled here" instead of roadmap wording.
- No facts, footnotes, source cards or last_verified dates changed.

## [2026-11-15] edit | provider history wording
- The 2026-11-12 history line on the robinhood, coinbase, webull, interactive-brokers and alpaca pages now reads "First version of this page."
- No facts, footnotes, source cards or last_verified dates changed.

## [2026-11-15] edit | source-set wording
- Provider pages: "not yet in the source batch" now reads "not yet reviewed here", and the callout's "no source in the current batch" now reads "no source we cite".
- rails/README.md, gaps.md, rails/remote-mcp-oauth.md, rails/agent-identity.md and approval-models/ai-partition.md now say "our sources" instead of the batch. The 2026-11-12 changelog no longer names the batch.
- No facts, footnotes, source cards or last_verified dates changed.

## [2026-11-15] edit | headline
- The headline is now "How AI agents connect to money". Updated in README.md, the generated index and llms.txt, the front page, the document title and the share-card text.
- No facts, footnotes, source cards or last_verified dates changed.

## [2026-11-15] ingest | ChatGPT Wallet, Rain Agent Vaults, AgentBank, Nous, merchant agent rules
- Retrieved and ingested source cards oa-01 to oa-04 (OpenAI), eb-01 (eBay), ua-01 and ua-02 (United Airlines), rn-01 and rn-02 (Rain), ag-01 to ag-03 (AgentBank) and ns-01 to ns-03 (Nous). All official; summaries, fingerprints, short verified quotes; no full copies.
- New pages: payments/chatgpt-wallet.md, payments/rain-agent-vaults.md, payments/agentbank.md, payments/merchants-and-outside-agents.md, personal-money/nous.md.
- Edited: payments/README.md, payments/mastercard-agent-pay.md, payments/visa-intelligent-commerce.md, personal-money/README.md, rails/agent-identity.md, faq.md, gaps.md, glossary.md (network token, Web Bot Auth), changelog/2026-11-15.md. No existing facts or footnotes removed.
- Unknown: Nous's own FCA status (no official source opened confirms it), whether ChatGPT Wallet runs on Visa Intelligent Commerce or Mastercard Agent Pay, MCP servers for ChatGPT Wallet, Rain and Nous, and AgentBank availability.

## [2026-11-17] query | AP2 vs ACP vs x402 comparison
- New analysis: analyses/ap2-vs-acp-vs-x402.md (comparison table, criteria, method, one section per protocol, how to choose, FAQ). Cites existing cards only: pm-04, pm-07, pm-08, pm-12, pm-13, pm-14, pm-15, cb-01, ag-01. The ACP, AP2 and x402 pages were re-read on 2026-11-17 and still match the cards.
- Edited: analyses/README.md (lists the page), README.md (analyses row), rails/agent-payments.md and payments/README.md (links), glossary.md (A2A, facilitator, merchant of record), changelog/2026-11-17.md. No existing facts or footnotes removed.
- Unknown: fees for each protocol, what the person approves under ACP and x402, production AP2 support, and whether ACP is combined with AP2 or x402 in production.

## [2026-11-17] edit | headings, openings, descriptions, Updated label
- Provider pages: H2s are now questions (e.g. "Can an AI agent trade at Alpaca?", "What is still unknown about Alpaca?", "What changed on this page?"); each opens with a direct answer; the source-card/unknown callout moved to the end of the unknown section. Rails and approval-model pages: H2s reworded as questions.
- Openers rewritten on faq, comparisons/launch-brokers, advisors/README, build/connect-an-mcp-client and gaps; the generated Trading page drops its "This page answers..." line and the dateline under the short answer.
- Summaries (meta descriptions) brought to 120-160 characters on 15 pages. AGENTS.md now says last_verified is shown as "Updated". changelog/2026-11-17.md extended.
- No facts, footnotes, source cards or last_verified dates changed.

## [2026-11-18] ingest | Coinbase Agent Controls, Public order gate, Agentic Ready, Agent Pay flight, Agent Detection, Gemini, Starling, Wealth.com, Target and Booking.com terms
- Retrieved and ingested source cards cb-10 (Coinbase Agent Controls blog, reader fetch), pu-10 and pu-11 (Public MCP server v0.11.0 release and pull request 19), pm-16 (Visa Agentic Ready), pm-17 (Mastercard live flight purchase, reader fetch), pb-06 (Plaid Agent Detection), gg-01 and gg-02 (Google blog and Gemini Apps Help), pb-08 (Plaid post on Gemini and Wallet), st-01 (Starling), wc-01 (Wealth.com), tg-01 (Target Terms & Conditions) and bk-01 (Booking.com Customer terms). cb-09 was re-retrieved (same URL as the Coinbase MCP docs): new fingerprint and summary, original feedback facts kept. All official; summaries, fingerprints, short verified quotes; no full copies.
- New pages: personal-money/gemini-google-wallet.md, personal-money/starling-assistant.md, advisors/wealth-com.md, changelog/2026-11-18.md.
- Edited: providers/coinbase.md (limits and the Coinbase-enforced Agent Controls, ChatGPT plugin confirmation cards), comparisons/launch-brokers.md, approval-models/per-order-confirm.md and separate-account.md, overview.md, rails/local-mcp-and-cli.md and agent-identity.md, payments/visa-intelligent-commerce.md, stripe.md, paypal.md, mastercard-agent-pay.md and merchants-and-outside-agents.md, personal-money/README.md, plaid.md and banks-and-outside-agents.md, advisors/README.md, gaps.md, glossary.md (Agent Detection, Agentic Ready, Elicitation, Verifiable Intent). No existing facts or footnotes removed.
- Not ingested: the OpenAI commerce page change (no ACP mention), which Edward deferred to the next pass, and Wirex Navoka, which he declined.
- Unknown: whether Public's hosted server has the 0.11.0 order gate; whether Coinbase auto-stop cancels open orders and when product permissions ship; the airline, date and volume of the Mastercard flight purchase; the exact date of Wealth.com's November update; Starling payment limits.
- Notes: the Target terms page states "LAST UPDATED: September 10, 2026" and the Booking.com page states "Updated August 25, 2025", so both revision dates are recorded on their cards. Business Insider's list of agent bans was used as a pointer only and is not cited.

## [2026-11-18] edit | section pages for providers, sources and comparisons

- Added providers/README.md, sources/README.md and comparisons/README.md. The left-hand menu links each folder to its own page, and these three folders had none, so /providers, /sources and /comparisons returned 404. providers/ and sources/ carry a generated listing.
- Edited: overview.md and AGENTS.md (link the new pages), changelog/2026-11-18.md (one bullet).

## [2026-11-18] ingest | personal agents: Grok Bot, X Money, Claude Personal Finance and Duet, ChatGPT Finances, OpenAI dots, Instinct, Perplexity Personal CFO, Link wallet, Plaid connection steps
- Retrieved and ingested 43 source cards. Grok Bot: gb-01 (X posts), gb-02 (Finance plugin README), gb-03 (Vault), gb-04 (approvals), gb-05 (changelog). X Money: xm-01 (plugin README), xm-02 (Cross River release), xm-03 (overview), xm-04 (FAQ), xm-05 (licenses), xm-06 (CFPB prepaid agreements database), xm-07 (NY DFS bulletin, reader fetch), xm-08 (@XMoney launch post). Plaid: pb-09 (Instinct), pb-10 (Claude), pb-11 (ChatGPT), pb-12 and pb-13 (Perplexity), pb-14 to pb-19 (Link, OAuth, Data Transparency Messaging, products, Items, Transactions docs), pb-20 (Plaid Portal), pb-21 (consumer help, reader fetch), pb-22 (August 2026 product updates). Anthropic: cl-01 to cl-04. OpenAI: oa-05 to oa-09 (reader fetches). Meta: mm-01 and mm-02 (help pages, reader fetch), mm-03 (launch post). Stripe: sp-01 to sp-03. JPMorganChase: jp-01. Official unless the card says third-party (Cross River, CFPB and NY DFS are third-party for X Money). Summaries, fingerprints, short verified quotes; no full copies. For reader fetches of pages that would not load directly, the fingerprint covers the retained text (mm-01, mm-02, oa-08, pb-21 hold excerpts).
- New pages: personal-money/grok-bot.md, x-money.md, claude-personal-finance.md, claude-duet.md, chatgpt-finances.md, openai-dots.md, instinct.md, perplexity-personal-cfo.md; payments/link-wallet-for-agents.md.
- Edited: personal-money/README.md (a row for each new agent in the page list and, from page headers, the comparison table), meta-muse.md (how Muse pays, what you control), plaid.md (how a connection works, Plaid Portal, which assistants use Plaid, company-reported figures, MCP for Data Partners), banks-and-outside-agents.md and rails/mandates-and-data-access.md (JPMorgan and Plaid agreement; Data Transparency Messaging), payments/README.md, stripe.md and chatgpt-wallet.md (links), gaps.md (Muse item narrowed, four items added), glossary.md (Data Transparency Messaging, Item, Passkey, Plaid Link, Plaid Portal, Stored-value account), changelog/2026-11-18.md. No existing facts or footnotes removed; the line that said Instinct and dots had no pages was replaced.
- Not ingested: the CFPB 1033 / OIRA article (declined), Copilot, Alexa+ and Apple (no primary sources), and third-party explainers on X Money and Grok Bot (leads only; one unverified claim about Grok Bot linking X Money was deliberately not published).
- Unknown: whether OpenAI dots can read Finances data; whether Muse can pay from a bank account or pay bills; the price in the JPMorgan and Plaid agreement; Perplexity's own description of Personal CFO (its page could not be fetched, so Plaid is cited); the launch date of Claude Duet; X Money agent limits and whether agents other than Grok Bot can connect; which institutions each assistant supports.
- Notes: Meta's help pages and OpenAI's pages load only through a reader. The Grok Bot Finance plugin README carries a general caution that third-party connectors are not built or maintained by xAI, which the Grok Bot page repeats. The Grok Bot changelog (gb-05) is a running page, so its fingerprint will change as entries are added.

## [2026-11-18] remove | Advisor agents section

- Removed the Advisor agents section to keep the wiki focused on end-user agents: advisors/README.md and the four advisor pages, nine source cards (an-01, an-02, ni-01, ni-02, nv-01, wc-01, wf-01, ws-01, bd-01), the advisor type from the page schema, and the advisor links, entries and FAQ answer on README, index, llms.txt, overview, directory, faq and gaps. Older changelog and log entries stay, with their advisor links turned into plain text.
- /advisors, /advisors/ and the four advisor page addresses now redirect to /overview. Source card bl-11 (Schwab) stays. The Interactive Brokers line on advisor-managed accounts is unchanged.

## [2026-11-19] ingest | Chase block on agents shopping with a card number; Chase cards in ChatGPT Wallet
- Retrieved and ingested source cards bl-12 (Wall Street Journal report by AnnaMaria Andriotis, Ben Glickman and Gina Heeb, syndicated on Mint, reader fetch) and bl-13 (PYMNTS summary of the same report, reader fetch), both third-party. Re-read oa-02 (OpenAI Help Center, Making purchases with ChatGPT Wallet, reader fetch): the page now has a Chase section and a primary-cardholder rule, so the card's date, fingerprint, summary and quotes were updated. Its older quote on Chat, Work and Codex threads is kept; the availability quote now includes the primary-cardholder sentence.
- New pages: changelog/2026-11-19.md.
- Edited: personal-money/banks-and-outside-agents.md (Chase card block, other banks' cards, Link, ChatGPT Wallet and Chase side by side), payments/link-wallet-for-agents.md (Chase cards and merchant cost), payments/merchants-and-outside-agents.md (merchants on agent virtual cards), payments/chatgpt-wallet.md (steps to add a Chase card), glossary.md (Agentic token).
- Not ingested: the Kinexys and Hyundai Card agent-to-agent FX test (declined).
- Unknown: whether Chase's card block applies to agents that use ChatGPT Wallet; how much more the Link virtual card costs merchants; whether Visa or Mastercard have responded. The WSJ attributes the Chase block and the slow adoption of agentic tokens to people familiar with the matter, not to the bank.
- Notes: the PYMNTS article repeats the Journal's reporting and adds its own earlier coverage; only the points the Journal report carries were used.

## [2026-11-19] ingest | Coinbase docs: how to connect from each supported AI app
- Re-read source card cb-09 (Coinbase MCP docs, direct fetch): the card's date, fingerprint and summary were updated in place, and its existing text and quotes are kept. The page now lists ten supported apps with a setup tab for each, a Disconnect note, and limits on the CLI API key.
- Edited: providers/coinbase.md (new section on connecting from each app; revoke path and CLI key scope added to the guardrails table; changelog line), personal-money/grok-bot.md (how to add Coinbase in Grok Bot, account-wide connectors), glossary.md (Connector), changelog/2026-11-19.md.
- Unknown: plan, country and workspace availability for most of the ten apps; whether the Grok, Perplexity Computer, Claude Code and Codex CLI tabs show a portfolio approval screen is not stated in those tabs. Hermes and Supertake are named as the doc names them, with no description added.

## [2026-11-19] ingest | Public, Scalable Capital and Kraken provider pages; connecting from each AI app at Robinhood, Webull, Alpaca, Stripe and AgentBank
- Retrieved and ingested 17 new source cards, all official: pu-12 to pu-16 (Public connector guides for ChatGPT and Codex, Grok, Meta Muse and Perplexity; API guides index), sc-01 to sc-03 (Scalable Capital Help Center: connecting, what the assistant can do, order approval), kr-01 to kr-03 (Kraken MCP server docs, kraken-cli docs, kraken-cli GitHub repository), ag-04 to ag-08 (AgentBank docs: connect your agent, ChatGPT, Claude, account revocation, thresholds) and pm-18 (Stripe MCP docs, Markdown version, which carries the per-app setup tabs). Re-read and updated in place, keeping existing text and quotes: rh-01, rh-04, rh-06, rh-09, rh-10, pu-01, pu-02, pu-09, pm-09, ag-01, wb-01, wb-02, wb-03, wb-08, al-01, al-02, al-03, al-09. Only "None recorded yet." placeholder quotes were replaced.
- New pages: providers/public.md, providers/scalable-capital.md, providers/kraken.md.
- Edited: providers/robinhood.md, webull.md and alpaca.md (connecting from each app; Alpaca order types and local server defaults), payments/stripe.md (public preview, 14-day sessions, key deadline, Dashboard approval, revoking, connecting from each app), payments/agentbank.md (revoking, thresholds, connecting from each app), overview.md (Public now links its page; Scalable Capital and Kraken added), approval-models/per-order-confirm.md (Scalable Capital, Kraken) and separate-account.md (Public), providers/README.md (wording for brokers and exchanges beyond the five launch brokers), glossary.md (Agent skill, Dead man's switch), gaps.md (Alpaca order types closed; Public and Scalable Capital added to open items), changelog/2026-11-19.md. Publisher: the Trading page's short answer gained Public, Scalable Capital and Kraken lines and now says "providers here" rather than "launch brokers".
- Robinhood's Trade approvals article no longer says the setting is still rolling out; the earlier wording is kept as a dated statement rather than removed.
- Unknown: whether Public's hosted server confirms each order or enforces limits; Public and Scalable Capital order types for MCP orders; Scalable Capital paper trading, limits, per-assistant revoke and how its order confirmation reaches you; where Kraken's dead man's switch timer runs; AgentBank threshold amounts; Stripe Treasury caps and MCP country availability; Webull Cloud read-only mode and hard limits.
- Notes: Kraken's asset counts were left out because its CLI docs and GitHub README give different numbers (79 versus 170+ xStocks, 11 versus 12 forex pairs).

## [2026-11-19] ingest | Mastercard: developer MCP server, Agent Pay for Machines, Open Finance US
- Retrieved and ingested 6 new source cards, all official: pm-19 (Mastercard Developers Agent Toolkit page, Markdown version fingerprinted), pm-20 (Agent Toolkit SDK page and FAQ), pm-21 (GitHub README of Mastercard/developers-agent-toolkit), pm-22 (Mastercard press release of 2025-09-10, reader fetch), pm-23 (Mastercard Agent Pay for Machines page of 2026-10-20, reader fetch) and pm-24 (Open Finance US developer documentation home, Markdown version fingerprinted).
- Edited: payments/mastercard-agent-pay.md (new sections: does Mastercard have an MCP server, Agent Pay for Machines, Open Finance US; Unknown line reworded; mcp_server for Agent Pay left unknown), gaps.md (Mastercard MCP item answered for documentation only; Agent Pay for Machines and Open Finance US items added), rails/agent-payments.md (two table rows), payments/x402.md (Mastercard builds on x402), changelog/2026-11-19.md.
- Unknown: whether Agent Pay has an MCP server; Agent Pay for Machines price, countries, how to join Early Access and whether a public developer page exists; whether an AI agent can use Open Finance US on a consumer's behalf; what Agent Sign-Up and Insight Tokens (named in the 2025-09-10 release) involve.
- Notes: the toolkit tools are described as retrieving documentation and API details; no cited page uses the words "read-only", so the wiki does not either. Server and package version numbers were left out because they change.

## [2026-11-20] ingest | Citi and Chase terms, Singapore Know Your Agent, AgentCore payments, Lightspark, BNY and Microsoft, and six more
- Retrieved and ingested 23 new source cards: ma-01 (Monetary Authority of Singapore keynote), aw-01, aw-02 and aw-03 (AWS Marketplace agentic payments, AWS blog, AgentCore developer guide), ls-01 and ls-02 (Lightspark release and docs), an-01 and an-02 (Mastercard and Ant International), ax-01 (AXS), cb-11 and cb-12 (Coinbase Advisor page and Coinbase System Update), pm-25 and pm-26 (Visa Europe release and corrected global release), nt-01 (NETS), sd-01 and sd-02 (Sardine), rp-01 (Replit), tc-01 (TechCrunch on bank terms), ci-01 (Citi online user agreement), jp-02 (Chase Digital Services Agreement), bn-01 (BNY), mi-01 and mi-02 (Microsoft).
- Created: payments/agentcore-payments.md, payments/lightspark-agent-accounts.md, rails/institutional-markets.md, changelog/2026-11-20.md.
- Edited: glossary.md (six new entries), gaps.md, overview.md, payments/README.md, rails/README.md, personal-money/README.md, personal-money/banks-and-outside-agents.md, rails/agent-payments.md, rails/agent-identity.md, rails/mandates-and-data-access.md, payments/x402.md, payments/ap2.md, payments/mastercard-agent-pay.md, payments/visa-intelligent-commerce.md, payments/paypal.md, payments/stripe.md, payments/link-wallet-for-agents.md, payments/merchants-and-outside-agents.md, providers/coinbase.md, approval-models/draft-then-submit.md, approval-models/per-order-confirm.md.
- Visa's corrected release (pm-26, 2026-11-19) replaced the 2026-11-17 release (pm-16) as the citation on the PayPal, Stripe and overview pages. pm-16 stays cited on the Visa page.
- Unknown: the exact days Citi's and Chase's terms changed; Bank of America, Citizens and PNC wording; the Know Your Agent protocol text, date and participants; AgentCore payments Regions and pricing; Lightspark price, consumer countries and MCP address; the coffee purchase date, amount, merchant and country; whether Visa's European participants are in the global 140; AXS consumer launch date; BNY trade tenor, size, price and date.
- Notes: Mastercard says Agent Pay for Machines was introduced in June, while its product page is dated 2026-10-20; the wiki states both without reconciling them.

## [2026-11-21] edit | starter prompts and front-page Try a starter prompt
- Reorganized build/starter-prompts.md: retitled Starter prompts; research prompts then prompts for coding agents, with a jump link and session preambles; question-style headings; full https://agenticfinancerails.com URLs in every prompt. The four earlier coding prompts are kept as rewritten research or coding prompts. No facts or footnotes were removed.
- Front page "Start here" row: added Try a starter prompt, linking to /build/starter-prompts. Text prompt lines wrap; the stock copy button stays visible on touch. llms.txt "Start here" now lists the page. AGENTS.md and README link it. URL unchanged.
- Added changelog/2026-11-21.md.
- overview.md: What changed 'latest' link now points at changelog/2026-11-21.md.

## [2026-11-21] ingest | Coinbase's chart of which AI apps trade the most
- Retrieved and ingested 1 new source card: cb-13 (Coinbase's X post of 2026-11-21 with a 15-second video chart). Post text confirmed from X's public embed data; the video figures come from a viewer's description and were not checked against the video file.
- Edited: providers/coinbase.md (new table, shares by AI app for 11/09 - 11/15), personal-money/grok-bot.md (one cited line), glossary.md (LLM client, Notional volume), changelog/2026-11-21.md.
- Unknown: dollar totals; the year on the chart (2026 inferred from the post date); what "Custom CLI", "Muse" and "Other" cover; earlier weeks.

## [2026-11-21] edit | cb-13 cites Coinbase's official video
- Updated sources/cb-13.md so the chart title, footnote and shares cite the official 15-second video attached to Coinbase's X post. The post text is still confirmed from X's public embed data.
- Reformatted the Coinbase "Which AI apps trade the most" section and the matching Grok Bot line: a rank table of shares, with period, source and unknowns in a short table or note. No facts or footnotes were removed.

## [2026-11-21] edit | visual cheatsheets for approval models, payments, personal money, and x402
- Added cited cheatsheets: a two-axis approval-model spectrum on approval-models/README.md (linked from comparisons/launch-brokers.md); a payments control matrix on payments/README.md (15 programs, four named controls; Merchants topic excluded; "three kinds" typo corrected to four); a read / pay / move grid on personal-money/README.md (14 tools; Banks topic excluded); an x402 request-flow sequence on payments/x402.md (linked from analyses/ap2-vs-acp-vs-x402.md).
- Each cheatsheet is a sourced markdown table. The spectrum and x402 flow also have an inline SVG with title and desc (hidden below 800px so phones use the table). Unknown stays unknown. No facts or footnotes were removed. Front page unchanged.

## [2026-11-22] edit | cheatsheet diagrams for preview (tables folded under details)
- Redesigned the four cheatsheets as diagrams after Edward's preview note that some were just large tables. Payments is a 15×4 filled/hollow/diamond matrix. Personal money is a three-lane chip diagram (read only, pays with approval, moves money) plus an Other group, with connection marks. Approval spectrum and x402 were restyled, and Coinbase's optional dedicated portfolio is now a dashed card. Each diagram has a desktop SVG and a stacked mobile SVG (diagrams are no longer hidden below 800px). Sourced tables and footnotes are kept, inside a collapsed "Sources and full table" details block.
- Front page unchanged. No facts or footnotes were removed. Preview only; no production deploy and no push in this entry's scope.
## [2026-11-22] edit | approval spectrum: stack marks instead of crossing arrows
- Replaced the crossing arrows on the approval-models diagram with numbered stack marks in the gutters, so no connector runs across a card or label. Placements, facts, footnotes and the sourced table are unchanged. The other three cheatsheet diagrams were not edited. Preview only; no production deploy and no push in this entry's scope.

## [2026-11-22] edit | plain language instead of "YAML header" on public pages
- Reworded reader-facing "YAML header" on the payments, personal money, approval models and trading (directory) pages into plain language. Facts, footnotes and data links were kept. Repo docs, schemas and changelog history were left alone. Preview only; no production deploy and no push in this entry's scope.

## [2026-11-22] edit | payments records table folded after the controls diagram
- Moved "What can an agent do with each program?" on payments/README.md to sit after the controls diagram, and folded the seven-column record table into a closed "Full details for every program" details block. The heading, intro, data/programs.json link, facts and footnotes were kept. Preview only; no production deploy and no push in this entry's scope.
## [2026-11-22] ingest | Stripe chief economist's Link agent-spend figures
- Retrieved and ingested 1 new source card: sp-04, a 2026-11-20 X post and article by Ernie Tedeschi, Stripe's chief economist, on his personal account (not an official Stripe release). Post text confirmed from X's public embed data. The article text and the labeled figures on the two attached charts were read from the article and those charts.
- Edited: payments/link-wallet-for-agents.md (new "How much are agents spending?" table), personal-money/grok-bot.md, personal-money/instinct.md and personal-money/meta-muse.md (one cited line each, aggregate Link spend only), glossary.md (seven-day rolling average), changelog/2026-11-22.md. overview.md: What changed 'latest' link now points at changelog/2026-11-22.md.
- Unknown: dollar amounts and user counts; exact dates for the article's "last month" in which spend doubled. The charts date the category series through November 19, 2026, the retail inset as November 13–19, 2026, and the repeat-purchase chart as data through November 15, 2026 for customers whose first purchase was approved by October 15.
