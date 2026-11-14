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

