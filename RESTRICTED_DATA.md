# Excluded and separately acquired data

## Datastream / Bitstamp

The cross-exchange test uses Bitstamp BTC and ETH observations obtained through Datastream. Request the data through an institution with appropriate access. The public Binance weekday file supplies only the Binance side of the comparison. The author should retain Datastream instrument identifiers and extraction metadata in private research records; these identifiers were not available in the public inputs assembled here and are not invented in this deposit.

## VIX

Acquire daily close series VIXCLS from https://fred.stlouisfed.org/series/VIXCLS or an appropriately licensed CBOE source. The main analysis requires weeks from January 2020 through October 2026 and the preceding week's observations. Average available nonmissing daily closes within each Sunday–Saturday week; do not impute weekends or holidays. Use the previous week's mean for the contemporaneous models and the current search week's mean for next-week models. The study used a historical download dated 16 November 2026.

## Cryptocurrency uncertainty

Use separate weekly policy and price indices from Lucey et al. (2022), DOI https://doi.org/10.1016/j.frl.2021.102147 . A source page is https://brianmlucey.com/2021/03/16/cryptocurrency-uncertainty-index-dataset/ . The frozen supplied file contains 574 Monday–Sunday measurement periods and ends on 29 December 2024. Its Friday date labels are not period-end dates.

For a search week beginning on Sunday, the predictive model uses the uncertainty measurement period ending on that Sunday, and the contemporaneous model uses the period ending seven days earlier. Use no period that extends beyond the relevant model cutoff and do not carry stale values beyond the end of the file. This alignment yields 259 common weeks per asset, labelled 19 January 2020–29 December 2024. Measurement-period completion is verified; historical publication timestamps and real-time release availability are not established.

The full frozen uncertainty input values are kept in a separate researcher-only supplement. This public data folder alone cannot reproduce the uncertainty estimates. The supplement is not licensed for public redistribution by the author.
