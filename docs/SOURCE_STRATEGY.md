# Source Strategy

This project should prefer:

1. Official APIs and official documents
2. Official RSS feeds and release calendars
3. High-quality machine-readable market data
4. Trusted news aggregation
5. Social / narrative feeds

## Tier 1: Official APIs

Use for macro, rates, reserves, fiscal, energy, filings, and policy baselines.

- FRED / ALFRED
- U.S. Treasury Fiscal Data
- IMF SDMX
- World Bank API
- ECB Data Portal API
- CFTC public data
- SEC EDGAR APIs
- EIA API
- BLS API

## Tier 2: Official Pages And Feeds

Use for speeches, minutes, calendars, and releases.

- central bank RSS feeds
- ministry press-release pages
- debt office calendars
- exchange notices
- regulator statements

## Tier 3: Hybrid Sources

These may be semi-structured and require custom collectors:

- XLSX release drops
- PDFs
- HTML tables
- media-room pages

This is likely where much of Japan, China, India, and some EM work will live.

## Tier 4: Narrative Sources

Use only after the core official layer is working.

- X / Twitter API
- GDELT
- major-news clustering
- watchlists

## Ingestion Policy

For each source, register:

- source id
- owner
- official / non-official flag
- access method
- cadence
- timezone
- revision behavior
- rate limit
- authentication requirement
- known failure modes

## Revision Policy

All macro systems should be revision-aware.

Store:

- first seen value
- latest value
- revision timestamp
- release timestamp
- effective period

That lets you backtest what was actually knowable at the time.
