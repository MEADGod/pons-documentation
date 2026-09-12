# 2. PONS v2 Lifecycle

Source: https://docs.ponsfamily.com/v2

## Create

The creator supplies metadata, a fee recipient, optional creator tax and buyback preference, a launch config and a quote asset. Supply is minted to the curve rather than handed to the creator as a preallocated holding. An optional initial purchase is a purchase, not a free allocation.

## Curve trading

Users buy with the quote asset and sell the launch token for that asset. Pricing depends on reserves, including a phantom quote reserve used for pricing rather than withdrawable funds. Large orders move the curve and cannot be valued solely from a marginal spot price.

## Graduation

The curve stops at its reserved allocation. The purchase that completes it normally triggers graduation automatically. An oversized final purchase can be partially filled and unspent input refunded. Read actual event amounts rather than assuming the requested size was filled.

## Routing phases

- `0 NotGraduated`: curve phase; also check whether buys or sells have closed.
- `1 Swept`: reserves swept, pool not yet created. Do not show it as actively trading on either venue.
- `2 PoolCreated`: trade through Uniswap v4.
- `3 Rescued`: exceptional recovery path; display it explicitly.

`readyToGraduate()` closes sells even if a simple graduated flag still reads false. `sellableTokens()` determines whether curve inventory remains. Phase alone is not enough to offer a valid curve quote.

## Completion and recovery

`createGraduatedPool(token)` is documented as permissionless and retryable when the launch is waiting to be seeded. This is not permission to retry an uncertain trade submission: first resolve its transaction state.

The docs describe a protocol recovery path after seven full days stuck between graduation steps. It is not an instant holder redemption mechanism. Locked graduated liquidity and mistaken transfers directly to contracts are not recoverable through an ordinary withdrawal.

## Migration is a separate feature

The v2 migration section concerns outside tokens with failing markets moving to replacement tokens. It involves deposit epochs, conversion, claims and rescue deadlines. Do not confuse that workflow with automatic graduation of an ordinary new v2 launch.
