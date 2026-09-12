# 7. Fees, Creator Payouts and Buybacks

Source: https://docs.ponsfamily.com/v2

## Fee layers

Separate the standard trading fee, optional creator tax, temporary opening buy tax and transaction gas. The standard fee is divided among protocol, creator and an optional buyback allocation. Creator tax goes to the creator. Read the actual per-launch policy rather than importing v1's fee splits.

The graduated v4 core pool is documented as having zero pool fee because the PONS hook charges the trading fee. Zero in the pool fee field therefore does not mean fee-free trading.

## Accrual is not a wallet payout

Before graduation, fees accrue on the curve; after graduation, on the hook. They reach fee escrow only after a sweep. A zero escrow balance can coexist with unswept earnings. Keep unswept, credited, claimed and vested balances separate in reporting.

A native launch uses the native balance ledger. A custom pair uses a per-token ledger. For an Apple-linked pair, creators receive that quote asset, not silently converted ETH. Post-graduation launch-token fees may require bounded conversion before payout; conversions can be deferred when pricing is unacceptable.

## Withdrawals

Documented escrow reads include `balanceOf(recipient)` and `balanceOfToken(recipient, token)`; withdrawals use `claim()` and `claimToken(token)`. Resolve the correct escrow for the token's stack. Do not display an aggregate balance across assets as if it were denominated in a single currency.

## Buybacks

In v2, optional buybacks buy the launch token and vest it over five years. They are not the v1 PONS burn mechanism. The vesting start is weighted as later purchases arrive. Released tokens are split between beneficiaries according to the protocol, not paid as immediate quote-asset fees.

Internal conversion and buyback operations have operator restrictions and price-impact bounds. A creator call is not guaranteed to complete a sweep requiring those internal swaps. Skipped conversions and buybacks should be shown as deferred or rerouted states, never as completed purchases.
