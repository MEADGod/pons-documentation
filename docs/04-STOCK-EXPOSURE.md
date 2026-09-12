# 4. Stock Exposure and “Long Apple 1x”

Source for custom pairs: https://docs.ponsfamily.com/v2

## Documented possibility

PONS v2 permits quote assets explicitly approved by the protocol. The docs give tokenised stocks as an example: buyers spend the stock token, sellers receive it, graduation is measured in it, the v4 pool is paired against it and creator fees are paid in it. There is no silent conversion to ETH.

This makes stock-linked pairing a real documented category, not merely branding. It does NOT establish that an Apple instrument is currently approved. This folder does not invent an AAPL contract, issuer, venue or approval result.

## Three different positions

1. **Direct stock holding:** shares held through a brokerage, with rights determined by the account and jurisdiction.
2. **Unleveraged Apple-linked token holding:** a token intended to represent Apple exposure, subject to issuer terms, backing, redemption, custody, eligibility and tracking risk.
3. **Apple Table paired with that token:** a separate launch token priced in the Apple-linked quote asset. Its own relative price can rise or fall independently.

These are not interchangeable products. Buying Apple Table is not automatically buying a share, and pairing does not create enforceable one-for-one redemption.

## Meaning of 1x

For this example, “1x” means the desired absence of borrowing or leverage in a stock-exposure strategy. It is an objective, not an implemented PONS order parameter. The reviewed PONS docs do not specify a stock margin account, leverage selector, guaranteed delta, stock oracle peg or rebalancing engine that makes a memecoin track AAPL at exactly 1x.

If the requirement is exact unleveraged stock tracking rather than a stock-linked meme-token market, the product needs separately verified instrument terms and execution infrastructure. Documenting a pair cannot supply that missing mechanism.

## Valuation

Indicative Apple Table price in USD = Apple Table price in quote-token units × quote-token price in USD.

Both components move. The quote token may itself deviate from the underlying stock, especially around closed stock-market hours, liquidity interruptions or issuer restrictions. Transaction fees, creator taxes, opening tax and price impact further affect realized returns.

## Product wording

Suitable: “Apple Table — proposed Apple-linked custom pair; unleveraged stock-exposure theme.”

Only use “Long Apple 1x” with a nearby explanation that it is the proposed objective, not guaranteed Apple Table performance. Do not claim stock backing, NVIDIA/Apple affiliation, guaranteed redemption or leverage functionality without evidence.
