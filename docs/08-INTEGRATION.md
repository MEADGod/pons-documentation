# 8. Integration Requirements

Source: https://docs.ponsfamily.com/v2

## Read surface

| Workload | Documented contract read | Purpose |
| --- | --- | --- |
| Launch permission | `canLaunch(address)` | Current wallet eligibility |
| Config discovery | `launchConfigCount`, `getLaunchConfig` | Enabled launch terms |
| Pair eligibility | `approvedPairTokens`, `pairTokenEconomics` | Approved asset and units |
| Economics pin | `previewLaunchEconomics` | Protect reviewed creation terms |
| Routing | `getLaunchedToken` | Curve, pair and phase |
| Quote inputs | `getReserves`, fee/tax reads | Current curve pricing |
| Trade availability | `sellableTokens`, `readyToGraduate` | Avoid closed-side quotes |
| Revenue | Curve/hook balances plus escrow | Unswept and claimable amounts |

## Write surface

Creation uses `launchToken`, optionally the launch-and-buy router. Curve transactions use `buy` and `sell`. Graduation completion uses `createGraduatedPool`. Fee claims use the appropriate escrow. This document lists source-verified method names, not a complete audited ABI or executable transaction builder.

## Discovery rules

Resolve per-launch token and curve from its factory. Never use a symbol lookup as proof of stock-token identity. Never hardcode an Apple address without provenance. The source lists current v2 singleton addresses, but this pack intentionally links to them instead of presenting unverified addresses as execution defaults.

Check chain ID 4663, deployed bytecode, factory provenance, current config and asset eligibility before any transaction. These chain checks were not performed for Apple Table because no quote-token or wallet address has been supplied.

## Events and state

Index TokenLaunched, CurveBuy, CurveSell, CurveBuyRefunded, CurveCompleted, LaunchSwept, PoolGraduated and AutoGraduationFailed. For revenue include native and ERC-20 escrow events; native-only indexing misses custom-pair payouts. Record block number, block hash, transaction hash and log index for deduplication and reorg handling.

Use persisted checkpoints and bounded log ranges. Do not assume an RPC or frontend snapshot guarantees complete historical coverage. Derive current venue from contract state and reconcile it with indexed events.

## v4 pool identity

Reconstruct the pool key from sorted currencies, pool fee, tick spacing and the correct stack's hook. Native ETH is represented by the zero address; ERC-20 custom pairs are actual token addresses. A v3 pool address model cannot simply be reused for v4 pool IDs.

## Error handling

Surface PairTokenNotApproved, PairTokenDecimalsMismatch, LaunchEconomicsMismatch, NotWhitelisted, SlippageExceeded, CurveGraduated and native-value mismatch errors with actionable explanations. Re-read changed terms and require renewed review rather than loosening protections automatically.
