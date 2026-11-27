# Cryptocurrency Trading Activity and the Predictive Limits of Search Attention

## About this deposit

This data-only collection supports a study of Google search attention, cryptocurrency trading volume, signed trade initiation and next-week forecasting. It contains CSV datasets and Markdown documentation. It does not contain analysis code, notebooks or software environments, and is not a complete executable replication package.

The main sample contains 353 weekly observations for each of Bitcoin (BTC) and Ethereum (ETH), or 706 asset-week rows. Search-week dates run from 19 January 2020 to 18 October 2026. Weeks start on Sunday and end on Saturday in UTC. The final current week ends on 24 October 2026; the final next-week outcome ends on 31 October 2026.

## Files to start with

| File | Description |
|---|---|
| `data/weekly_analysis_data.csv` | Final estimation sample, including current, lagged and next-week variables and alternative measures |
| `data/google_trends_weekly.csv` | Linked Google Trends indices, 669 weeks per asset, 5 January 2014–25 October 2026 |
| `data/binance_daily_data.csv` | Binance BTCUSDT and ETHUSDT spot observations, 2,496 daily rows per asset, 1 January 2020–31 October 2026 |
| `data/weekly_market_source_data.csv` | Complete market weeks, including lag-construction and next-week target observations |
| `data/market_states.csv` | Shared Bitcoin-based four-week states and twelve-week sensitivity states, one row per search week |
| `data/bitcoin_daily_close_with_2019_history.csv` | BTC daily close history from October 2019 needed to reconstruct both state horizons |
| `data/binance_weekday_volume.csv` | Binance Monday–Friday volume inputs for the exchange comparison; no Bitstamp observations |
| `sources/google_exports/` | The 50 original input exports actually used, renamed by asset and window dates |
| `metadata/data_dictionary.csv` | Definitions, units and construction of CSV variables |
| `metadata/attention_scaling_full_sample.csv` | Full-sample means and sample standard deviations for descriptive model scaling |
| `metadata/google_export_ledger.csv` | Google source-file mapping, window dates, extraction labels and linking diagnostics |
| `metadata/binance_source_archives.csv` | Original archive URLs and recorded SHA-256 hashes |
| `metadata/file_inventory.csv` | File sizes, row counts and hashes |
| `metadata/validation_checks.csv` | Checks performed while assembling this deposit |

## Variable construction and matching

See [VARIABLES.md](VARIABLES.md) for definitions and [SOURCES.md](SOURCES.md) for source details. Use `asset` and `week_start` as the main analysis keys. The market-state file has one row per week and applies to both assets. The data dictionary records full column names; the manuscript may use mathematical notation instead.

Attention changes in the main CSV are unstandardized index-point changes. For the full-sample models, both current and lagged attention use the current-attention mean and sample standard deviation for the relevant asset. The scaling file is not appropriate for historical forecast origins: expanding-window forecasts must estimate scaling from their training data alone.

The linked Google history uses historical downloads. Forecast evaluation with these vintages is retrospective and does not recreate data actually available at every past forecast date. Future outcomes in the CSV are targets, not information available at the forecast origin.

## Coverage and exclusions

This public folder contains no VIX or UCRY index values and no Datastream/Bitstamp observations. VIX and cryptocurrency uncertainty require separate acquisition or redistribution clearance; see [RESTRICTED_DATA.md](RESTRICTED_DATA.md). Their absence means this public folder alone does not reproduce the uncertainty models or the Bitstamp comparison.

The data are third-party observations and author-constructed transformations, not public-domain data. Read [RIGHTS_AND_ATTRIBUTION.md](RIGHTS_AND_ATTRIBUTION.md). No blanket CC0 or MIT licence is applied to the mixed data collection. Binance-derived data retain their provider's noncommercial, attribution and share-alike conditions; Google attribution and applicable terms also remain relevant.

## Publication and citation

Prepared on 17 November 2026. No GitHub repository or DOI has yet been assigned to this package. Once deposited, cite the repository's versioned release and, if created, its Zenodo DOI. A data availability statement is supplied in [DATA_AVAILABILITY.md](DATA_AVAILABILITY.md).
