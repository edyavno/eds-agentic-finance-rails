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

