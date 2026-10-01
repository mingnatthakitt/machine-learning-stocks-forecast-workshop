# Where the workshop data comes from

According to the organiser's `prepare_data.py` script, the source is **Yahoo Finance**,
retrieved through the Python **yfinance** library using `auto_adjust=True`.
The original retrieval date was not recorded, so we cannot give a verified download
timestamp for this snapshot.

This repository distributes a **frozen CSV**. Everyone should use this supplied file
rather than download a fresh copy: market-provider revisions can change the inputs
and make teams' experiments harder to compare.

| Item | Supplied snapshot |
|---|---|
| File | `data/workshop_participant.csv` |
| Instruments | AAPL, MSFT, NVDA, SPY, TSLA |
| First / last date | 2014-01-02 / 2024-12-31 |
| Rows | 13,840 |
| Columns | Date, Ticker, Open, High, Low, Close, Volume |
| Price treatment | Adjusted OHLC prices; script requests split/dividend adjustment, drops incomplete OHLCV rows and rounds prices to two decimal places |
| Validation split | Training 2014–2022; practice/validation 2023–2024 |

`Open`, `High`, `Low` and `Close` are daily prices; `Volume` counts shares traded.
One row is one instrument on one trading day. The notebook computes next-day return
from the following day's close, within the same instrument.

SHA-256 of the supplied CSV:
```text
3231d9280e869080c6c7dcac42b6a4758226d223b79cb382176013604582b488
```

No participant needs `yfinance`, a Yahoo account, or a separate market-data download.
No private competition-year or holdout files are included. This source attribution
is not a separate license for the market data; applicable provider terms still apply.

Source references: [yfinance download documentation](https://ranaroussi.github.io/yfinance/reference/api/yfinance.download.html),
[Yahoo terms](https://legal.yahoo.com/us/en/yahoo/terms/otos/index.html).
