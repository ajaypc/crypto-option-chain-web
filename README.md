# Crypto Option Chain

Live near-the-money option chains for **BTC, ETH and SOL** — mark price, bid/ask,
implied volatility, delta and open interest.

A single static page, no build and no server. It fetches directly from the
exchanges in the browser on load and every 5 seconds (the asset you're viewing):

- **BTC, ETH** — [Delta Exchange](https://docs.delta.exchange/) `/v2/tickers` (greeks included)
- **SOL** — [Deribit](https://docs.deribit.com/) USDC linear options `book_summary`

The "expected move" figure is the at-the-money straddle (call mark + put mark)
divided by spot — the market's priced-in ± move by that expiry.

**Not investment advice.**

Deployed with GitHub Pages: <https://ajaypc.github.io/crypto-option-chain-web/>
