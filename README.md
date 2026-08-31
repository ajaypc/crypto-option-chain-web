# Crypto Option Chain

Live near-the-money option chains for **BTC and ETH** — mark price, bid/ask,
implied volatility, delta and open interest.

A single static page, no build and no server. It fetches directly from the
exchanges in the browser on load and every 5 seconds (the asset you're viewing):

- [Delta Exchange](https://docs.delta.exchange/) `/v2/tickers` (greeks included)

The "expected move" figure is the at-the-money straddle (call mark + put mark)
divided by spot — the market's priced-in ± move by that expiry.

## Strangle builder

A panel above the chain sizes an OTM **call + put** strangle on the selected
expiry. Toggle **Long / Short**, pick the width by **delta** (10Δ / 16Δ / 25Δ), or set both strikes by hand.
It shows net debit/credit, breakevens, the move needed to profit vs. the ATM
expected move, max loss/profit, a delta-based P(expire between strikes), net
vega/theta, a payoff diagram, and highlights the two legs in the chain.

Below the payoff is a **30-minute history** of the two legs' combined price
(up to 48h) — the net credit you'd collect (short) or debit you'd pay (long),
from Delta's `/v2/history/candles`, with time-of-day marks on the x-axis. These
are last-trade prices, so illiquid strikes have gaps (carried forward), the
window shrinks to however far back both legs have actually traded, and a very
near expiry may have too few trades to plot. A collapsible **data-points table** under the chart lists every 30-min row (time in IST, each leg's price, net, 30-min change).

**Not investment advice.**

Deployed with GitHub Pages: <https://ajaypc.github.io/crypto-option-chain-web/>
