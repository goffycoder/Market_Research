# Global Flow Engine

An information-churning engine for global macro, cross-asset, and cross-border flow analysis.

The goal of this repository is not just to download data. It is to build a system that helps an individual investor answer:

- What is the current global market regime?
- Where is liquidity expanding or tightening?
- Which countries, sectors, and asset classes are acting as the marginal price-setters?
- Which flows are mechanical, which are policy-driven, and which are sentiment-driven?
- What is the likely direction of global risk appetite across the next few days, weeks, and months?

This repo starts from one core idea:

You cannot observe the full world flow of money directly. You can only approximate it through a layered map of:

- balance sheets,
- interest-rate differentials,
- sovereign issuance and reserve behavior,
- banking and funding stress,
- cross-border portfolio data,
- derivatives positioning,
- commodities and energy flows,
- official policy communication,
- and real-time narrative shifts.

That means the engine should be built as a proxy system, not as a fantasy "perfect ledger."

## What This Repo Should Eventually Do

At maturity, this project should:

1. Ingest official macro, rates, policy, and market data from the most important jurisdictions.
2. Track money and risk flows across bonds, FX, equities, credit, commodities, and funding markets.
3. Detect regime shifts such as disinflation, reflation, QT stress, sovereign stress, risk-on, risk-off, dollar shortage, and commodity shock.
4. Combine slow data, fast data, and event data into an interpretable market-direction score.
5. Generate both machine-readable features and human-readable narratives.

## First Principle: Model The World As Balance Sheets And Marginal Buyers

Markets move when the marginal buyer or seller changes.

Examples:

- If the Fed is shrinking reserves while Treasury issuance is rising, funding conditions matter more.
- If Japan repatriates capital, U.S. rates and USD/JPY can move even if U.S. data are unchanged.
- If China is weak and commodities roll over, EM FX and cyclicals can reprice globally.
- If oil spikes because of war, inflation expectations, bond yields, and consumer demand expectations all change together.

So this engine should be built around these actor buckets:

- Central banks
- Sovereign treasuries and debt offices
- Reserve managers
- Commercial banks
- Shadow banking / funding markets
- Real-money asset managers
- Leveraged funds / CTAs / macro funds
- Corporates
- Households
- Commodity exporters and importers
- Systemically important geopolitical actors

## Factor Map: What Actually Drives Global Markets

This is the heart of the repo. If a factor is not mapped here, the engine will miss the real story.

### 1. Global Liquidity And Money

Track:

- Central bank balance sheets
- Reserve balances
- Policy rates
- QE / QT pace
- Bank reserves and excess reserves
- Broad money and credit creation
- Cross-currency funding conditions
- Repo and collateral stress
- Dollar liquidity proxies

Why it matters:

- Liquidity is the fuel for asset prices.
- Tightening liquidity can hurt equities, credit, EM, and speculative assets even when growth data still look fine.
- Expanding liquidity can support risk assets even with mediocre fundamentals.

### 2. Inflation And Inflation Expectations

Track:

- CPI, core CPI, supercore, trimmed measures
- PPI and input-cost pipelines
- Wage growth
- Breakevens
- Inflation swaps
- Commodity passthrough
- Shipping and logistics costs
- Energy and food shocks

Why it matters:

- Inflation changes the rate path.
- The rate path changes discount rates.
- Discount rates reprice nearly everything.

### 3. Growth And Demand

Track:

- GDP nowcasts
- PMIs / business surveys
- Industrial production
- Retail sales
- Consumption proxies
- Housing activity
- Credit impulse
- Payrolls / unemployment / vacancies
- Trade volumes and export orders

Why it matters:

- Growth determines earnings power, default risk, fiscal stress, and political stability.

### 4. Sovereign Rates And Debt Supply

Track:

- Front-end and long-end government bond yields
- Curve shape
- Term premium proxies
- Auction calendars
- Debt issuance
- Fiscal deficits
- Treasury cash balances
- Foreign official holdings
- Domestic bank absorption of sovereign debt

Why it matters:

- Sovereign bond markets are the pricing spine of the whole system.
- They set discount rates, funding costs, and reserve-asset competition.

### 5. FX And Cross-Border Capital Flows

Track:

- Major FX pairs
- Real effective exchange rates
- Reserve data
- FX intervention
- Balance of payments
- International investment position
- TIC and cross-border holdings
- Carry spreads
- Hedging costs and basis

Why it matters:

- FX is the transmission channel between domestic policy and global asset pricing.
- Many crises are funding crises wearing an FX mask.

### 6. Credit, Banking, And Funding Stress

Track:

- Investment-grade and HY spreads
- CDS indices
- Bank equity relative performance
- Interbank funding rates
- FRA/OIS or equivalent spread proxies
- Repo specialness
- Swap spreads
- Commercial paper stress
- Bank lending surveys

Why it matters:

- Credit stress often leads equity stress.
- Funding stress can force deleveraging across otherwise unrelated assets.

### 7. Equity Market Internals

Track:

- Index levels
- Breadth
- Sector rotation
- Earnings revisions
- Forward EPS
- Dispersion
- Market cap concentration
- Small-cap vs large-cap
- Cyclicals vs defensives

Why it matters:

- Index price alone can lie.
- Breadth and leadership show whether a move is healthy or fragile.

### 8. Commodities And Real-Economy Pressure

Track:

- Crude oil, products, gas, coal
- Copper, iron ore, steel
- Gold, silver
- Agricultural commodities
- Freight and shipping
- Inventory levels
- Physical bottlenecks

Why it matters:

- Commodities are inflation drivers, geopolitical shock sensors, and growth barometers at the same time.

### 9. Positioning, Leverage, And Derivatives

Track:

- CFTC COT data
- Options skew
- Dealer gamma proxies
- Futures open interest
- Volatility term structure
- CTA trend exposure proxies
- Basis trades where observable

Why it matters:

- Price moves are often amplified by positioning, not fundamentals alone.

### 10. Policy And Political Risk

Track:

- Central bank statements
- Speeches
- minutes
- fiscal announcements
- sanctions
- tariffs
- elections
- war escalation
- energy-route threats
- industrial policy

Why it matters:

- Politics changes the rules of the pricing system.
- Geopolitics can override normal macro relationships.

### 11. Narrative, Sentiment, And Attention

Track:

- Official speeches and transcripts
- Major economic calendars
- trusted-news velocity
- topic clustering
- account-network activity
- social-media attention spikes
- sentiment divergence vs price

Why it matters:

- Markets move on both facts and the speed at which facts become common knowledge.

### 12. Alternative And High-Frequency Signals

Track:

- mobility
- port throughput
- electricity demand
- search trends
- satellite / shipping proxies
- card-spend proxies
- logistics trackers

Why it matters:

- These are useful for nowcasting before official releases catch up.

## Regional Coverage: What To Track By Geography

### United States

Priority:

- Fed
- Treasury
- FRED / ALFRED
- BLS
- BEA
- EIA
- SEC EDGAR
- CFTC
- Treasury auction and borrowing data
- NY Fed funding indicators

Why:

- The U.S. still anchors global discount rates, dollar funding, equity leadership, and reserve-asset pricing.

### Euro Area

Priority:

- ECB
- Eurostat
- sovereign spreads
- TARGET balances
- bank stress
- industrial demand
- energy exposure

Why:

- Europe is highly sensitive to global trade, energy shocks, and banking transmission.

### United Kingdom

Priority:

- BoE
- gilt market
- inflation and wage prints
- pension / LDI stress signals
- GBP funding and rates

Why:

- The U.K. is a major rates, FX, and financial-services node with outsized signaling value.

### Japan

Priority:

- BOJ
- MoF
- JGBs
- FX intervention risk
- foreign reserve behavior
- domestic investor allocation

Why:

- Japan is critical for global bond markets, yen funding, and reserve behavior.

### China

Priority:

- PBOC
- SAFE
- NBS
- credit growth
- property stress
- industrial demand
- export machine
- yuan fixing behavior
- commodity demand

Why:

- China is the world's manufacturing and commodity-demand hinge.
- China weakness or stimulus changes the whole global cycle.

### India

Priority:

- RBI
- government bond market
- inflation
- growth
- capital flows
- FX reserve management
- domestic liquidity

Why:

- India matters more every year for EM flows, energy demand, and domestic demand growth.

### Rest Of World / EM

Priority:

- commodity exporters
- Taiwan / Korea semiconductor cycle
- Gulf oil states
- Brazil / LatAm rates and FX
- frontier dollar stress

Why:

- EM often reveals liquidity cracks before DM investors notice them.

## Should This Repo Capture Twitter / X Feeds?

Yes, but only as a secondary layer.

X is useful for:

- real-time headlines,
- policy leaks,
- local-language reaction,
- official account monitoring,
- journalist and regulator watchlists,
- and measuring narrative velocity.

X is bad as a primary truth source because:

- it is noisy,
- access is gated by pricing tiers,
- relevance is unstable,
- engagement is easy to manipulate,
- and macro-quality signal is sparse compared with official releases.

Recommended rule:

- official data and official policy communication should set the base view,
- trusted news should confirm event reality,
- X should help detect narrative acceleration and market attention,
- but X should not override official data on its own.

Capture approach for X:

1. Build watchlists:
   - central banks
   - finance ministries
   - debt offices
   - regulators
   - exchange accounts
   - trusted journalists
   - policy analysts
2. Use the official X API for:
   - recent search,
   - full-archive search where available,
   - and filtered stream if your tier supports it.
3. Store:
   - post id,
   - author id,
   - timestamp,
   - language,
   - entities,
   - referenced posts,
   - public metrics,
   - topic tags,
   - embeddings / classifier outputs
4. Compute:
   - attention velocity,
   - topic frequency,
   - sentiment,
   - stance,
   - conflict,
   - surprise,
   - narrative divergence vs price
5. Keep ToS in mind:
   - design storage and redistribution carefully,
   - and prefer storing ids, metadata, features, and summaries over uncontrolled redistribution of full raw content.

## Official And High-Signal Data Sources

Use official and stable sources first. Add vendor or social data later.

### Core Official APIs And Feeds

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

### Additional Data You Will Likely Need Later

- Exchange calendars and market holiday calendars
- Earnings calendars and guidance databases
- Sovereign auction calendars
- Intraday market prices
- Options chains
- FX forwards / basis
- Cross-country ETF and fund-flow data
- Country-specific official sources that may require scraping instead of APIs

Inference:

Some country coverage, especially for China and parts of India / EM, may require a hybrid model:

- official APIs where available,
- structured scraping for official release pages,
- bulk spreadsheets,
- and manual QA around revisions and publication lags.

## Modeling World Flow Of Money: The Right Way To Think About It

Do not think of "money" as one number moving from one place to another.

Model it as interacting balance-sheet channels:

### Channel A. Policy Liquidity

- central bank assets,
- reserves,
- QT / QE,
- standing facilities,
- policy-rate path

### Channel B. Sovereign Supply

- net issuance,
- duration supply,
- auction absorption,
- foreign demand,
- bank balance-sheet capacity

### Channel C. Cross-Border Capital

- reserve accumulation,
- pension and insurer flows,
- household foreign buying,
- direct investment,
- portfolio rebalancing,
- repatriation stress

### Channel D. Banking And Funding

- repo,
- swaps,
- bank lending,
- collateral scarcity,
- dollar funding,
- maturity transformation

### Channel E. Commodity And Trade Settlement

- importer / exporter balances,
- terms of trade,
- energy bills,
- shipping disruptions,
- reserve drawdowns

### Channel F. Risk Appetite

- equity and credit demand,
- volatility selling or buying,
- leverage,
- CTA trend mechanics,
- defensive reallocation

The engine should estimate each channel separately, then combine them into a regime state.

## Project Architecture

This repo should follow a layered architecture.

### Layer 1. Bronze / Raw Ingestion

Store raw files exactly as collected:

- API responses
- CSVs
- XLSX files
- PDFs
- HTML
- RSS payloads
- social metadata

Why:

- reproducibility,
- auditability,
- and revision-aware research.

### Layer 2. Silver / Normalized Data

Normalize into consistent tables:

- releases
- time series
- event tables
- instrument metadata
- market prices
- policy documents
- speaker entities
- social posts

### Layer 3. Gold / Feature Store

Create reusable features:

- surprise scores
- z-scores
- rolling momentum
- rate-differential changes
- curve steepening / flattening
- liquidity impulse
- inflation impulse
- credit stress score
- policy hawkish / dovish score
- geopolitical escalation score
- narrative velocity score

### Layer 4. Model Layer

Run:

- regime classification
- market direction scoring
- cross-asset linkage analysis
- anomaly detection
- clustering
- factor decomposition

### Layer 5. Narrative Layer

Generate:

- morning brief
- weekly macro map
- risk dashboard
- country snapshots
- event-driven market notes

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

## What The Engine Should Score

The score should not be "bullish" or "bearish" in one vague number.

It should emit:

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

And then separate directional outputs by horizon:

- `risk_assets_1w`
- `risk_assets_1m`
- `duration_1w`
- `duration_1m`
- `usd_1w`
- `usd_1m`
- `oil_1w`
- `gold_1w`

## Suggested Build Order

### Phase 1. Build The Spine

Start with:

- U.S.
- Euro area
- Japan
- China
- India

and only the highest-signal factors:

- rates
- central banks
- sovereign supply
- FX
- inflation
- growth
- commodities
- official policy communication

### Phase 2. Add Positioning And Credit

Add:

- COT
- options vol
- credit spreads
- bank stress
- ETF and fund-flow proxies

### Phase 3. Add Narrative Intelligence

Add:

- RSS monitoring
- document parsing
- event extraction
- X watchlists
- trusted-news clustering

### Phase 4. Add Modeling

Add:

- regime labeling
- market-direction composites
- explainable scoring
- backtesting

## What Not To Do

- Do not start by scraping everything.
- Do not mix raw data and modeled data in the same tables.
- Do not rely on social sentiment as the main signal.
- Do not ignore revisions and release-time alignment.
- Do not build one giant "market score" with no decomposition.
- Do not treat all countries as equally important all the time.

## Existing Repo Artifacts

This repo already contains BOJ-specific research files and a dashboard:

- `boj_march30_to_apr03_analysis.md`
- `boj_advanced_dashboard.html`
- `boj_visual_dataset.csv`
- `boj_downloads/`

Those can serve as the first example of:

- raw-file capture,
- document interpretation,
- policy narrative extraction,
- and dashboard output.

## Immediate Next Steps

1. Define the source registry and event calendars.
2. Implement connectors for the official sources listed in `configs/source_registry.example.yaml`.
3. Normalize data into standard schemas.
4. Create the first version of the factor feature store.
5. Build a simple regime dashboard before any fancy ML.

## Long-Term Vision

The best version of this repo becomes:

- a macro data lake,
- a flow map,
- a policy watcher,
- a cross-asset risk engine,
- and a personal market research assistant.

That is ambitious, but it is the right ambition.
