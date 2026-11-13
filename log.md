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
