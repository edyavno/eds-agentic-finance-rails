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
