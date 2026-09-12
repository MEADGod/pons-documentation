# 1. Version Boundaries

Source: https://docs.ponsfamily.com/ and https://docs.ponsfamily.com/v2

## v1: existing pool launches

The v1 documentation describes a fixed supply of one billion tokens, a Uniswap v3 pool paired with WETH from creation, a 1% pool fee and a 0.0005 ETH launch fee. Its default graduation threshold is 4.2 ETH and graduation does not migrate that pool. The first-two-block buy restrictions belong to this version.

## v2: curve to pool

In v2, the full minted supply begins on a launch-specific bonding curve. Part is available for public trading, while a reserved allocation is held for graduation. Completing the curve creates a permanently locked Uniswap v4 pool. Approved ERC-20 quote assets can replace native ETH across the entire lifecycle.

Do not copy the v1 fee, threshold, reserve settings, ABI, factory, or launch protections into a v2 integration. Read the selected v2 config and quote-asset economics at creation time. Existing config IDs remain stable, but their settings may be edited or disabled for new launches.

## Per-token provenance

A token belongs to the stack that deployed it. Replacing the active factory does not move older tokens to a new hook or escrow. Resolve the launch's factory and its associated contracts; a wrong escrow can return zero without proving the creator earned nothing.

## Language to avoid

Do not describe all PONS tokens as WETH-only, all PONS launches as bonding curves, or all graduation events as no-migration milestones. Qualify each statement by protocol version. Do not describe a stock-themed v1 token as technically paired against a stock merely because its description mentions one.
