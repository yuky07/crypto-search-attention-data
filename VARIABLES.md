# Variables and construction

## Calendar and units

`week_start` is the Sunday beginning the search and market week. Daily inputs use UTC dates. Current market weeks contain seven daily observations and seven finite daily returns. Partial boundary weeks were excluded from market-variable construction. Volume is summed rather than averaged. Raw base volume is measured in BTC for Bitcoin and ETH for Ethereum; quote volume is measured in USDT. Natural logarithms use unscaled source units, not billions. Percentage returns and initiation pressure use different definitions even though both are reported on a 100-based scale.

## Trading variables

- Daily return: 100 × ln(close / previous daily close). The first available daily observation has no daily return because its previous closing price is not included. The blank is intentional.
- Weekly return: sum of the seven daily percentage log returns, equivalent to 100 × ln(current Saturday close / previous Saturday close).
- Within-week volatility: sample standard deviation of the seven daily percentage log returns, using denominator 6. This is not annualized volatility.
- Trading activity: ln(sum of daily USDT quote trading volume).
- Alternative activity: ln(sum of daily base volume), or ln(sum of daily trade counts).
- Signed initiation pressure: 100 × (2 × weekly taker-buy base volume / weekly total base volume − 1).
- Alternative initiation pressure: the same expression using quote-asset volumes instead of base quantities.

Positive pressure means buyer-initiated volume exceeds seller-initiated volume. It does not identify retail or institutional investors, net purchases by a population, or capital inflows. Trade counts represent exchange-reported trades, not blockchain transactions or counts of investors.

## Search attention

Google indices measure relative search interest. Each linked asset history is separately normalized to a maximum of 100, so levels do not measure comparable absolute search counts across assets.

- `attention_change`: current Google index minus its previous-week value, in index points.
- `abnormal_attention4`: ln(current Google index / arithmetic mean of the preceding four weekly index values).
- Suffix `lag1` or `lag2`: value one or two calendar weeks earlier.
- Prefix `next_week_`: value in the immediately following Sunday–Saturday week.

The stored attention measures are unstandardized. In descriptive regression models both current and lagged attention use the mean and sample standard deviation of the current measure within the same asset and estimation sample. In forecast models scaling must be recalculated from each expanding training sample. Full-sample moments must not be used to standardize past forecasts.

## Market states

For a Sunday search week beginning t, the four-week return is 100 × ln(BTC close at t−1 day / BTC close at t−29 days). Bull = 1 if this return is positive; otherwise Bull = 0. The shared BTC state is applied to both assets. There are 199 bull weeks and 154 bear weeks. The twelve-week sensitivity version uses t−85 days in the denominator and has 203 bull and 150 bear weeks. Neither uses prices from the current search week.

The four-week rule adapts Hsieh, Huang and Liu (2025), who use a value-weighted cryptocurrency market index. Our implementation uses Bitcoin instead and is not an exact replication of their market index or state-transition design.

## Cross-exchange calendar

`binance_weekday_volume.csv` contains Monday–Friday volume summed within the Sunday-labelled week, its natural log, two lags and the following week's log volume. These observations differ from the Sunday–Saturday main outcome. Merge with the main data for attention and common return/volatility controls. The corresponding Bitstamp inputs are not included.
