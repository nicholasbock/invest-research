# invest-research

A personal, non-commercial investment-research tool. It collects publicly available
information about publicly traded securities and organizes it for offline analysis to
help an individual investor track emerging themes, sentiment, and discussion trends.

This repository describes the project at a high level. The tool surfaces and ranks
information for a human to review for investment decisions.

## What it does

- Reads public posts and comments from a small, fixed allowlist of investment-related
  subreddits and stores them in a local database for later analysis.
- Combines that with other public sources (financial news headlines, public SEC/EDGAR
  filings) to summarize what is being discussed about a given security.
- Produces local, private research notes and summaries for the project owner only.

## How it uses the Reddit Data API

- **Read-only.** OAuth client-credentials flow with `read_only = True`. The app never
  posts, comments, votes, messages, edits, or modifies anything on Reddit.
- **Low volume.** Polls on an hourly cadence and stays within the free non-commercial
  rate limit (≤100 queries/minute per OAuth client). Requests are budget-capped per run.
- **Bounded scope.** Polls only a fixed allowlist of public subreddits (no broad,
  universe-wide search). Examples: r/investing, r/ValueInvesting, r/ETFs, etc.
- **Identified client.** Sends a descriptive, contactable `User-Agent` on every request.

## Compliance and data handling

- **Non-commercial / personal use only.** The project is not a product or service, is not
  monetized, and serves a single individual.
- **No redistribution.** Reddit content is used only for the owner's private analysis. It is
  **never** resold, published, shared, or redistributed in any form.
- **Public data only.** No attempt is made to access private, deleted, or restricted content,
  and no authentication beyond standard read-only OAuth is used.
- Operates in accordance with Reddit's [Data API Terms](https://www.redditinc.com/policies/data-api-terms),
  [Developer Terms](https://www.redditinc.com/policies/developer-terms), and the Responsible
  Builder Policy.

## Status

Personal project, single maintainer. Not affiliated with or endorsed by Reddit.
