# PONS v2 — Launches, Custom Pairs & Apple Table

An expanded, unofficial documentation pack based on the official PONS v1 and v2 documentation, reviewed on 12 September 2026. This is documentation, not an executable launchpad or trading bot.

## Start here

- [Version boundaries](docs/01-VERSIONS.md)
- [Protocol lifecycle](docs/02-LIFECYCLE.md)
- [Launch guide](docs/03-LAUNCH.md)
- [Stock exposure and the meaning of 1x](docs/04-STOCK-EXPOSURE.md)
- [Apple Table worked example](docs/05-APPLE-TABLE.md)
- [Trading, quotes and routing](docs/06-TRADING.md)
- [Fees, payouts and vesting](docs/07-FEES.md)
- [Integration requirements](docs/08-INTEGRATION.md)
- [Risks and release checklist](docs/09-RISKS.md)
- [Sources and verification boundaries](SOURCES.md)

## What changed from the earlier pack

The earlier pack summarized v1: WETH-only Uniswap v3 pools from launch. **PONS v2 supports approved custom quote assets, including the documented possibility of tokenised-stock pairs.** A v2 launch starts on a bonding curve and graduates into Uniswap v4. These are different protocol versions, not interchangeable descriptions.

## Featured example

**Apple Table** — illustrative ticker **$ATABLE** — a proposed launch paired against an approved Apple-linked stock token, if available. The ticker is an editorial suggestion, not supplied by the user or reserved onchain.

The requested phrase **“Long Apple 1x”** describes a proposed unleveraged stock-exposure objective. It is NOT a verified PONS leverage setting, a promise of stock-price tracking, or a claim that holding Apple Table is identical to holding AAPL.

A stock-token quote asset can provide an Apple-related component of exposure, but Apple Table has its own price against that quote asset. Its dollar performance depends on both. No Apple quote-token address, issuer, approval, redemption rights, or live availability has been verified for this example.

## Current documented rollout caveats

The v2 page says public launches are closed and creation is limited to whitelisted accounts; check `canLaunch(address)`. It also says all three security engagements are still in progress and to treat v2 as unaudited until reports are published. The site displayed a degraded-performance notice. These are documentation observations, not independently verified chain state.

Nothing in this folder launches a token, spends funds, or opens a stock position.
