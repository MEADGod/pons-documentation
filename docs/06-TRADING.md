# 6. Quotes, Trading and Routing

Source: https://docs.ponsfamily.com/v2

## Curve pricing

Use `getReserves()` for pricing. The returned quote reserve includes the phantom quote and excludes fees awaiting distribution. `realQuoteReserve()` represents actual collected quote, not the pricing reserve. Raw reserve ratios need correct token decimals before display.

Buy fees are removed from quote input before curve pricing; sell fees are deducted from the resulting quote output. The two directions are not symmetric. Include `feeBps()`, `creatorTaxBps()` and, for buys, `currentSnipeTaxBps(recipient)`.

The docs describe an opening buy tax starting at 99% and decaying over five seconds. It applies by recipient, not simply transaction sender; creator-related exemptions are established at creation. Do not substitute the v1 two-block restrictions or ignore tax in opening quotes.

## Order review

Show the precise token and quote addresses, trade direction, input asset, amount, expected output, minimum acceptable rate, fees, opening tax, recipient and venue. Use integer amounts and explicit decimals; do not use binary floating point for transaction amounts.

A clamped final buy may return fewer tokens and refund input. The documented minimum-output semantics protect an accepted rate during this clamp, not necessarily the full originally requested quantity. Integrators must reproduce the contract's integer rounding rather than adapting a generic AMM quote casually.

## Phase-aware execution

Before a curve buy, verify remaining sellable tokens. Before a sell, also verify readiness to graduate. Once phase 2 is reached, use a v4-aware route rather than the closed curve. During phase 1, explain the pending transition instead of pretending an executable venue exists.

For ERC-20 quote buys, approve the exact intended spender; native value is not the purchase input. Approvals and trades are separate permission boundaries. Native gas may still be needed even when buying with an Apple-linked token.

## Result reconciliation

Use receipts and actual CurveBuy, CurveSell and refund events. Label pending, reverted and confirmed operations distinctly. A network timeout is uncertain, not automatically failed; check transaction state before resubmitting. Reorganizations and stale index data require reconciliation with canonical chain state.
