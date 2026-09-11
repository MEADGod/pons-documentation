# Integration Notes

## Network

- **Network:** Robinhood Chain
- **Chain ID:** `4663`
- **Native asset:** ETH
- **Launch-token quote asset:** WETH
- **Explorer:** https://robinhoodchain.blockscout.com/

Use the current official PONS documentation for the public RPC and deployed contract addresses. Do not copy addresses from an outdated snippet without verifying them against the active documentation.

## Onchain Source of Truth

The PONS documentation recommends reading directly from contracts and indexing events:

1. Index launch events from the active factory.
2. Register each emitted token and pool address.
3. Index pool swap events.
4. Read token metadata and canonical pool state from the token contract.
5. Poll the documented graduation state.
6. Backfill logs in bounded block ranges because wide public-RPC queries may time out.

There is no migration event in the documented launch model because trading continues in the original pool.

## Token State

The public docs describe launch tokens as self-describing onchain. Integrations can read values such as:

- name;
- symbol;
- decimals;
- total supply;
- logo;
- description;
- liquidity pool; and
- social links.

Never infer a token's legitimacy from metadata alone. Verify the token address, factory, pool, and relevant onchain events.

## Pricing

Every launch token trades against WETH. Calculate price using the pool's current state and token ordering. Quotes can change before execution, so integrations must account for slippage and price impact.

For current ABIs, factory addresses, locker addresses, router details, pricing formulas, and reference-token data, use:

https://docs.ponsfamily.com/
