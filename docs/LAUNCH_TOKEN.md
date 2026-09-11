# Launch a Token

Official launchpad: https://www.ponsfamily.com/launchpad

## Launch Checklist

1. Open the official PONS launchpad.
2. Connect an EVM wallet configured for Robinhood Chain.
3. Confirm the active network and current wallet address.
4. Upload a token image accepted by the live form.
5. Enter the full token name.
6. Enter the ticker without relying on the `$` prefix as part of the onchain symbol.
7. Add the optional description and social links.
8. Verify the creator fee wallet.
9. Review any optional creator initial buy.
10. Review the launch fee and every transaction parameter.
11. Sign only after confirming the destination contract and network.
12. Record the deployed token contract and pool addresses.

Do not document guessed character limits, image dimensions, upload sizes, or contract parameters. Treat current form validation and official documentation as authoritative.

## Fictional Example Launch

```text
Name:        The Ponsi
Ticker:      PONSI
Display:     $PONSI
Description: The Ponsi, paired with NVDA.
Image:       A token image accepted by the PONS launch form
Socials:     Optional
Creator:     Connected wallet or another carefully verified EVM address
Initial buy: Optional and reviewed before signing
```

### Pairing Clarification

The phrase **“paired with NVDA”** is branding or narrative context for this fictional example. It does not mean the token is backed by NVIDIA stock, redeemable for NVDA shares, affiliated with NVIDIA, or technically paired with an NVDA asset.

According to the current PONS documentation, PONS launch tokens trade in their own pools against **WETH**. The actual pool for `$PONSI` would therefore be `$PONSI/WETH`, not `$PONSI/NVDA`.

## Token Identity

Names and tickers are not unique identifiers. After launch, users should verify **The Ponsi** by its deployed token contract address rather than relying only on the name or `$PONSI` ticker.

This example is fictional. It is not a deployed token, investment recommendation, promise of profit, or statement of affiliation with PONS, Robinhood, Uniswap, or NVIDIA.
