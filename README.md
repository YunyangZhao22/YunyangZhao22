# Hi, I'm Yunyang Zhao

Quantitative research portfolio — commodity futures factor engineering and market state identification.

[Portfolio site](https://yunyangzhao22.github.io) · [GitHub](https://github.com/YunyangZhao22)

---

## Projects

### [Commodity Momentum Foundry](https://github.com/YunyangZhao22/Commodity-Momentum-Foundry)

A 85-factor momentum library for Chinese commodity futures (F01–F85), with specifications, benchmark mapping and a full single-factor case study.

- **Factor specs** — Chinese/English names, math symbols and formulas, organised as time-series / cross-sectional / strategy-level
- **Benchmark study** — correspondence mapping against WorldQuant 101 and GTJA 191 alphas on a four-level scale (A homologous → D futures-specific); ~30% of factors use futures-only inputs (open interest, term structure, warehouse receipts, cross-market linkage)
- **Case study: F34 (TRIX)** — 81 contracts, 1-day forward-return framework; long-short Sharpe 0.70 / 0.69 at N150 / N200 with −14% max drawdown and 1.2% daily turnover; cross-sectional IC is positive while time-series IC is negative — two orthogonal dimensions, not a contradiction
- **Also included** — reference handbook (notation, data structure, MAD standardisation) and four literature reviews (LLM factor mining, CTA factor systems, cross-sectional commodity strategies, technical pattern recognition)

### [Market Regime Recognition](https://github.com/YunyangZhao22/Market-Regime-Recognition)

A six-state regime identification system for domestic commodity futures, built as **nowcast rather than forecast**: direction is largely unpredictable (signal half-life ≈ 12h), while volatility and regime are identifiable.

- **Core signal** — `signal = sign(R) × min(E/eff, 1)`, direction × trend-efficiency saturation, compressed into [−1, +1]; Hull MA smoothing
- **Five timeframes** — 15min / 30min / 60min / 2h / 4h with separately calibrated `(win, eff)` pairs, converging on 60min as the single primary signal
- **Probabilistic framework** — five-dimensional features → hard anomaly gate (gap / volatility burst / limit-lock / liquidity) → generative posterior over six states → HMM forward filtering with grey-zone detection
- **Interactive visualisation** — [live demo](https://yunyangzhao22.github.io/market-regime-daily.html): K-line with regime colour bands and state statistics (red = long, green = short, following domestic futures convention)

---

## Method stack

Python (pandas, numpy, scipy, pyarrow) · factor engineering · cross-sectional backtesting (IC, quantile groups, long-short, cost sensitivity, train/val/test split) · MAD robust standardisation · HMM and probabilistic state modelling · ECharts interactive visualisation

---

## Notes

Research documentation only. Backtests use continuously-concatenated main contracts and are intended for factor comparison and direction judgement, not for position-level replication. Nothing here constitutes investment advice.
