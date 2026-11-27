# Sources and provenance

## Google Trends

Data source: Google Trends, https://trends.google.com/ . Topics: Bitcoin (Cryptocurrency), topic ID `/m/05p0rr`; Ethereum (Software), topic ID `/m/0108bn2x`. Settings documented for the study: Worldwide, All Categories, Web Search.

Bitcoin topic URL: https://trends.google.com/explore?q=%2Fm%2F05p0rr&date=all&geo=Worldwide

Ethereum topic URL: https://trends.google.com/explore?q=%2Fm%2F0108bn2x&date=all&geo=Worldwide

The frozen input exports were obtained in November 2026. Each asset uses 25 overlapping annual and July-start bridge windows. In chronological window order, each new window is rescaled using the median ratio of positive raw values in the overlap with its preceding window, multiplied by the preceding linking factor. Observations outside complete window weeks are excluded. Annual-window observations take priority over July-start windows for duplicate weeks. Each linked asset history is then normalized to maximum 100. This produces 669 consecutive Sunday-start weeks per asset. Retained export CSVs contain the values originally supplied; the ledger records the asset mapping and window metadata.

## Binance

Public historical repository: https://data.binance.vision/

Definitions and archive structure: https://github.com/binance/binance-public-data

Pairs: BTCUSDT and ETHUSDT, spot market, daily klines. Main inputs cover 1 January 2020–31 October 2026. Extra BTC daily closes cover October–December 2019 for market-state prehistory. The metadata archive ledger lists URLs and hashes. The daily public CSV retains the date, OHLC prices, volumes, trade counts and taker-buy volumes needed for this study. Original timestamp fields and the unused kline field were omitted. Daily returns and Sunday week labels were added locally.

## Uncertainty sources not redistributed in this public folder

VIX: CBOE via FRED, series VIXCLS, https://fred.stlouisfed.org/series/VIXCLS . The frozen download used in the study was dated 16 November 2026. FRED flags the observations as copyrighted. Obtain permitted access directly from the source.

Cryptocurrency uncertainty: Lucey, B. M., Vigne, S. A., Yarovaya, L., & Wang, Y. (2022). The cryptocurrency uncertainty index. Finance Research Letters, 45, 102147. https://doi.org/10.1016/j.frl.2021.102147

Provider data page: https://brianmlucey.com/2021/03/16/cryptocurrency-uncertainty-index-dataset/ . The page permits free use with citation. An explicit redistribution licence for the supplied updated weekly file was not established. The frozen file used here ends in December 2024; later downloads may contain a different vintage.

## Market-state reference

Hsieh, C.-H., Huang, P.-H., & Liu, H.-C. (2025). State transitions and momentum effect in cryptocurrency market. Finance Research Letters, 86, 108356. https://doi.org/10.1016/j.frl.2025.108356

## Restricted cross-exchange source

Bitstamp observations were obtained through LSEG Datastream under institutional access. No vendor observation-level data, workbook or mixed cross-exchange output is included. Author subscription access does not itself establish public redistribution rights.
