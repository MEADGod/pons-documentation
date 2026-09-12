# 9. Risks and Release Checklist

## Stock-linked asset risks

Verify the issuer, backing model, redemption rights, custody, transfer restrictions, eligible jurisdictions, trading hours and corporate-action handling of any Apple-linked quote token. An AAPL symbol is insufficient. Stock-token approval by PONS is not a guarantee of the asset or its issuer.

Apple Table adds independent launch-token demand and liquidity risk. An unleveraged theme can still lose all its value. The quote token may diverge from AAPL, and Apple Table may diverge from the quote token. Neither pairing nor locked liquidity promises an exit at a reference price.

## Protocol and rollout risks

The reviewed v2 docs explicitly say audits have not closed and public launches are restricted. Three listed teams are SB Security, Dingbats and Pashov Audit Group. Their listing is not a completed audit report. Recheck reports and launch permissions before release.

Contract bugs, stale frontends, failed graduation, restrictive quote assets and transaction irreversibility remain possible. The website's degraded-performance notice reinforces the need to verify chain state rather than relying exclusively on cached UI values.

## Required evidence before calling Apple Table live

- Exact approved Apple-linked token contract and issuer terms.
- Successful chain/network and bytecode checks.
- Creator wallet permitted by `canLaunch`.
- Enabled config and verified quote economics.
- Fresh economics pin and launch fee.
- Reviewed creator tax, buyback setting and recipients.
- Valid minimum-output protection and intended allowances.
- Confirmed creation receipt and canonical token/curve identities.
- Actual trade events before reporting purchases or proceeds.
- Clear public language distinguishing quote exposure from guaranteed AAPL tracking.

Until those checks are complete, retain the example's blocked status. No funds should be requested to “activate” this documentation. No private key, seed or account credential belongs in this pack.
