# 5. Example Launch — Apple Table

**Fictional configuration. No token or stock position has been launched.**

- Name: **Apple Table**
- Proposed symbol: `ATABLE`, displayed as `$ATABLE`
- Theme: **Long Apple 1x**
- Description: “Apple Table — an Apple-themed community token with a proposed approved Apple-linked quote asset. Long Apple 1x is the exposure objective, not a promise that this token tracks AAPL.”
- Quote asset: an approved Apple-linked ERC-20, if verified and available
- Quote address: not configured
- Creator wallet: not configured
- Initial buy: none requested
- Creator tax: illustrative zero, subject to final review
- Buybacks: illustrative disabled, subject to final review

## How the example would work

First identify the exact eligible Apple-linked asset, including issuer, decimals, transfer restrictions and terms. Verify the asset on the intended network and check the v2 factory approval and economics. If no suitable approved asset exists, stop; do not replace it with an arbitrary token called AAPL or silently switch to ETH.

The creator then selects that asset at launch. Buyers must hold it and approve the appropriate curve or router. During the curve phase, their purchase spends that quote token in exchange for Apple Table. A sell returns quote tokens, not necessarily ETH, dollars or brokerage shares.

At graduation, the locked v4 pool contains Apple Table and the same quote asset. Changing to another pairing asset later is not a creator option. Creator fees accrue and become claimable in the quote asset, while vested buyback distributions, if enabled, are Apple Table tokens.

## What the launch does not do

It does not open a Robinhood brokerage position, borrow capital, buy Apple shares on behalf of holders, guarantee a stock peg or give share voting rights. Any such rights would require a separate verified instrument and contractual structure.

## Launch readiness

The example JSON deliberately contains null addresses and `readyToLaunch: false`. It is a planning record, not contract calldata. The user's requested “Long Apple 1x” concept is represented explicitly without manufacturing a live capability.
