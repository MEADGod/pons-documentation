# Protocol Summary

## Launch Model

Creating a PONS launch deploys the token and its trading pool in a single transaction. The creator supplies the token name, symbol, image, description, social links, and creator fee wallet.

The liquidity pool is locked automatically. Every token trades against WETH in its own Uniswap V3 pool from launch. The documented model has no bonding curve and no later liquidity migration.

## Documented Launch Parameters

| Parameter | Current documented value |
| --- | --- |
| Network | Robinhood Chain |
| Chain ID | `4663` |
| DEX model | Uniswap V3 |
| Pair asset | WETH |
| Fixed supply | 1,000,000,000 tokens |
| Pool fee | 1% |
| Launch fee | 0.0005 ETH |
| Default graduation threshold | 4.2 ETH paired in the pool |
| Liquidity | Locked automatically |

These values are a dated summary, not permanent constants. Verify the current interface and contracts before use.

## Launch Protection

The official documentation describes buy protection during the first two blocks:

- on the launch block, only the creator's initial buy may execute;
- during the remainder of the protection window, each wallet may hold at most 5% of supply and buy at most 5.5% of supply;
- selling and wallet-to-wallet transfers are not restricted; and
- the limits end after the protection window closes.

## Graduation

A token graduates when the WETH paired in its locked pool reaches the configured threshold. The documented default is 4.2 ETH.

Graduation does not move liquidity to a new pool. Trading continues in the same pool. Graduation does not prove token quality and does not guarantee future liquidity, price appreciation, or an exit.

## Fees and Buybacks

Trading generates liquidity fees in both the launch token and WETH. The fee split is snapshotted when a token launches and does not change for that token.

The public documentation describes a current `70/30` split for active-factory launches and a legacy `90/10` split for older launches. Confirm the direction and exact split shown for the specific factory and token before making financial assumptions.

The documentation also describes protocol-funded PONS buybacks and burns. A burn reduces circulating supply but does not guarantee a higher token price.
