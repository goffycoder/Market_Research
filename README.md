# Global Flow Engine

An information-churning engine for global macro, cross-asset, and cross-border flow analysis.

## Why This Repo Exists

This project is not just a data downloader. It is a decision engine for an individual investor to answer:

- What regime are global markets in right now?
- Is liquidity expanding or tightening?
- Who is the marginal buyer/seller by country and asset class?
- Which flows are mechanical vs policy-driven vs sentiment-driven?
- What is the likely risk direction over days, weeks, and months?

> Core idea: we cannot directly observe the full "world money flow."  
> We approximate it through a layered proxy system:
> balance sheets, rates differentials, sovereign supply, funding stress,
> cross-border holdings, derivatives positioning, commodity flows,
> policy communication, and narrative velocity.

## What This Engine Should Do

At maturity, this repo should:

1. Ingest official macro, rates, policy, and market data across major regions.
2. Track money/risk flows across bonds, FX, equities, credit, commodities, and funding.
3. Detect regime shifts (disinflation, reflation, QT stress, sovereign stress, risk-on/off, dollar shortage, commodity shock).
4. Merge slow + fast + event data into interpretable market-direction scores.
5. Output both machine features and human-readable narratives.

## First Principle: Balance Sheets + Marginal Buyers

Markets move when the marginal buyer/seller changes.

Examples:

- Fed reserve drain + heavy Treasury issuance raises funding importance.
- Japan capital repatriation can move U.S. rates and USD/JPY without new U.S. data.
- China slowdown can reprice EM FX and cyclicals through commodity demand.
- Oil shock from war can reprice inflation expectations, rates, and consumption risk together.

### Key actor buckets

- Central banks
- Sovereign treasuries / debt offices
- Reserve managers
- Commercial banks
- Shadow funding markets
- Real-money managers
- Leveraged macro / CTA participants
- Corporates
- Households
- Commodity exporters/importers
- Geopolitical state actors

## Factor Map (12 Buckets)

If a factor is missing from this map, the engine will miss the story.

| # | Factor Bucket | What To Track | Why It Matters |
|---|---|---|---|
| 1 | Global Liquidity & Money | Central bank balance sheets, reserves, policy rates, QE/QT pace, broad money, credit creation, cross-currency funding, repo/collateral stress | Liquidity is the fuel for asset prices |
| 2 | Inflation & Expectations | CPI/core/supercore/trimmed, PPI pipelines, wage growth, breakevens, inflation swaps, commodity passthrough | Inflation drives rate path; rate path drives discount rates |
| 3 | Growth & Demand | GDP nowcasts, PMIs, production, retail sales, housing, credit impulse, payrolls, trade | Growth drives earnings, defaults, fiscal pressure |
| 4 | Sovereign Rates & Supply | Front-end/long-end yields, curve shape, term premium, auctions, issuance, deficits, cash balances, foreign holdings | Sovereign markets are the global pricing spine |
| 5 | FX & Cross-Border Flows | Major FX, REER, reserves, intervention, BoP, IIP, TIC, carry, hedging basis | FX is the transmission channel for global pricing |
| 6 | Credit, Banking & Funding Stress | IG/HY spreads, CDS, bank equity, interbank rates, FRA/OIS proxies, repo specialness, swap spreads | Funding stress forces cross-asset deleveraging |
| 7 | Equity Internals | Breadth, sector rotation, earnings revisions, dispersion, concentration, small-vs-large, cyclical-vs-defensive | Index level alone can hide fragility |
| 8 | Commodities & Real-Economy Pressure | Oil/products/gas/coal, base metals, gold/silver, agriculture, freight, inventories | Commodities are inflation + growth + geopolitics in one channel |
| 9 | Positioning, Leverage & Derivatives | CFTC COT, skew, dealer gamma proxies, open interest, vol term structure, CTA proxies | Positioning amplifies price moves |
| 10 | Policy & Political Risk | CB statements/speeches/minutes, fiscal actions, sanctions, tariffs, elections, war, route threats | Policy can override normal macro relationships |
| 11 | Narrative, Sentiment & Attention | Official transcripts, calendar density, trusted-news velocity, topic clustering, account-network shifts, social attention spikes | Speed of consensus formation moves markets |
| 12 | Alternative/High-Frequency Signals | Mobility, ports, electricity demand, search trends, shipping/satellite proxies, card-spend | Useful for nowcasting before official data catch up |

## Regional Coverage (Priority Lens)

| Region | Priority Inputs | Why It Is Systemic |
|---|---|---|
| United States | Fed, Treasury, FRED/ALFRED, BLS, BEA, EIA, SEC, CFTC, auction/borrowing data, NY Fed funding indicators | Anchor of global discount rates, dollar funding, and reserve pricing |
| Euro Area | ECB, Eurostat, sovereign spreads, TARGET balances, bank stress, industrial and energy sensitivity | High exposure to trade/energy/banking transmission |
| United Kingdom | BoE, gilt market, inflation/wage prints, pension/LDI stress, GBP funding | Financial-system signaling node with outsized global impact |
| Japan | BOJ, MoF, JGB market, FX intervention risk, reserve behavior, domestic allocation | Key for global rates, yen funding, reserve dynamics |
| China | PBOC, SAFE, NBS, credit/property cycle, industrial demand, exports, yuan fixing, commodity demand | Manufacturing and commodity-demand hinge of global cycle |
| India | RBI, gov bond market, inflation/growth, capital flows, FX reserves, liquidity | Fast-growing EM flow and demand center |
| Rest of World / EM | Commodity exporters, Taiwan/Korea semi cycle, Gulf oil states, Brazil/LatAm rates+FX, frontier dollar stress | Early warning channel for global liquidity cracks |

## Should We Capture Twitter / X?

Yes, but only as a secondary layer.

### Use X for

- Real-time headlines and narrative acceleration
- Official-account monitoring
- Journalist/regulator watchlists
- Local-language reaction context

### Do not use X as primary truth

- High noise and manipulation risk
- Tier-gated access
- Relevance instability
- Lower signal quality than official releases

### Rule of precedence

1. Official data + policy communication set baseline view.
2. Trusted news confirms event reality.
3. X enriches attention/speed signals.
4. X never overrides official data by itself.

### Capture pipeline for X

1. Build watchlists (CBs, ministries, debt offices, regulators, exchanges, journalists, analysts).
2. Use official X API (recent search, full archive where available, filtered stream by tier).
3. Store metadata/features (id, author, timestamp, language, entities, references, metrics, topics, embeddings/classifier outputs).
4. Compute downstream features (attention velocity, topic frequency, sentiment/stance/conflict/surprise, narrative-price divergence).
5. Respect ToS (prefer ids/metadata/features/summaries over uncontrolled raw redistribution).

## Source Strategy: Official First

Use official and stable sources first; layer social/vendor feeds later.

### Core official APIs and feeds

- [FRED / ALFRED API](https://fred.stlouisfed.org/docs/api/fred/overview.html)
- [FRED observations endpoint](https://fred.stlouisfed.org/docs/api/fred/series_observations.html)
- [U.S. Treasury Fiscal Data API](https://fiscaldata.treasury.gov/api-documentation/)
- [IMF Data APIs](https://data.imf.org/en/Resource-Pages/IMF-API)
- [IMF Data portal](https://www.imf.org/data)
- [World Bank Indicators API](https://datahelpdesk.worldbank.org/knowledgebase/articles/898581-api-basic-call-structures)
- [ECB Data Portal API overview](https://data.ecb.europa.eu/help/api)
- [ECB data endpoint syntax](https://data.ecb.europa.eu/help/api/data)
- [ECB RSS feeds](https://www.ecb.europa.eu/rss)
- [CFTC Commitments of Traders](https://www.cftc.gov/MarketReports/CommitmentsofTraders/index.htm)
- [SEC EDGAR APIs](https://www.sec.gov/edgar/sec-api-documentation)
- [EIA Open Data API](https://www.eia.gov/opendata/index.php/api)
- [BLS Public Data API](https://www.bls.gov/bls/api_features.htm)
- [X API docs](https://developer.x.com/en/docs/twitter-api)
- [X search overview](https://developer.x.com/en/docs/x-api/search-overview)
- [X filtered stream overview](https://developer.x.com/en/docs/twitter-api/filtered-stream-overview)
- [GDELT DOC 2.0 API](https://blog.gdeltproject.org/gdelt-doc-2-0-api-debuts/amp/)

### Additional data likely needed later

- Exchange and holiday calendars
- Earnings calendars and guidance databases
- Sovereign auction calendars
- Intraday market prices
- Options chains
- FX forwards / basis
- Cross-country ETF/fund-flow datasets
- Country-specific official pages requiring structured scraping

Inference:

Coverage for China and parts of India/EM likely needs a hybrid model:
official APIs + structured scraping + bulk files + revision-aware QA.

## Modeling World Money Flow (Practical Lens)

Do not model "money" as one scalar. Model interacting channels:

| Channel | Core Components |
|---|---|
| A. Policy Liquidity | Central bank assets, reserves, QE/QT, standing facilities, policy path |
| B. Sovereign Supply | Net issuance, duration supply, auction absorption, foreign demand, bank capacity |
| C. Cross-Border Capital | Reserve accumulation, pension/insurer flow, household foreign buying, FDI, portfolio rebalancing, repatriation |
| D. Banking & Funding | Repo, swaps, lending, collateral scarcity, dollar funding, maturity transformation |
| E. Commodity & Trade Settlement | Terms of trade, energy import bill, shipping disruption, reserve drawdown |
| F. Risk Appetite | Equity/credit demand, vol-selling/buying, leverage, CTA trend mechanics, defensive reallocation |

The engine should estimate each channel independently, then combine them into regime states.

## Project Architecture

| Layer | Purpose | Typical Outputs |
|---|---|---|
| Bronze (Raw) | Preserve source truth exactly as collected | API payloads, CSV/XLSX, PDF, HTML, RSS, social metadata |
| Silver (Normalized) | Standardize into consistent schemas | Releases, time series, event tables, instrument metadata, documents |
| Gold (Feature Store) | Create reusable analytical signals | Surprise/z-score/momentum, curve signals, liquidity and risk composites |
| Model Layer | Convert features to states/probabilities | Regime labels, direction scores, linkage and anomaly outputs |
| Narrative Layer | Explain machine output for humans | Morning brief, weekly macro map, risk dashboard, country notes |

## Repo Layout

```text
.
├── README.md
├── pyproject.toml
├── .gitignore
├── configs
│   └── source_registry.example.yaml
├── data
│   ├── raw
│   ├── normalized
│   ├── features
│   ├── models
│   └── snapshots
├── docs
│   ├── FACTOR_FRAMEWORK.md
│   └── SOURCE_STRATEGY.md
├── src
│   └── market_engine
│       ├── connectors
│       ├── features
│       ├── models
│       └── pipelines
└── boj_* existing research artifacts
```

## Engine Score Outputs

### Core regime scores

- `global_liquidity_score`
- `inflation_pressure_score`
- `growth_momentum_score`
- `policy_tightening_score`
- `credit_stress_score`
- `dollar_funding_score`
- `commodity_shock_score`
- `geopolitical_risk_score`
- `narrative_heat_score`
- `overall_risk_regime`

### Directional outputs by horizon

- `risk_assets_1w`, `risk_assets_1m`
- `duration_1w`, `duration_1m`
- `usd_1w`, `usd_1m`
- `oil_1w`
- `gold_1w`

## Suggested Build Order

| Phase | Focus | Deliverable |
|---|---|---|
| 1 | Build the spine (U.S., Euro area, Japan, China, India + top factors) | Stable ingestion + normalized baseline datasets |
| 2 | Add positioning and credit | Better stress/risk timing sensitivity |
| 3 | Add narrative intelligence | Event/narrative acceleration layer |
| 4 | Add modeling | Regime labeling, direction composites, explainable backtests |

## What Not To Do

- Do not start by scraping everything.
- Do not mix raw and modeled data in the same tables.
- Do not treat social sentiment as primary signal.
- Do not ignore revisions and release-time alignment.
- Do not collapse everything into one opaque score.
- Do not treat all countries as equally important at all times.

## Existing Repo Artifacts

These BOJ artifacts are the first end-to-end example:

- `boj_march30_to_apr03_analysis.md`
- `boj_advanced_dashboard.html`
- `boj_visual_dataset.csv`
- `boj_downloads/`

They already demonstrate raw capture, policy interpretation, and dashboard output.

## Immediate Next Steps

1. Finalize source registry and event calendars.
2. Implement connectors from `configs/source_registry.example.yaml`.
3. Normalize into standard schemas.
4. Build first feature-store version.
5. Launch a simple regime dashboard before advanced ML.

## Long-Term Vision

The mature system becomes:

- A macro data lake
- A world flow map
- A policy watcher
- A cross-asset risk engine
- A personal market research copilot

Ambitious, but exactly the right direction.
