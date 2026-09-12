# 3. Launch Guide

Source: https://docs.ponsfamily.com/v2

## Before filling the form

Confirm Robinhood Chain, the current v2 factory, the connected wallet and whether `canLaunch(wallet)` permits creation. The documentation currently describes a restricted rollout. Having ETH for gas does not imply permission to launch.

Choose a name and symbol, an accepted image, description and optional social links. No guessed upload limits are prescribed here. Verify the fee recipient carefully; a direct factory launch can default a zero recipient to its caller, but the launch-and-buy router requires an explicit recipient.

## Select economics

Read enabled configs using `launchConfigCount()` and `getLaunchConfig(id)`. A config contains supply, curve fee, phantom quote, graduation threshold and pool parameters. For a custom asset also check `approvedPairTokens(asset)` and `pairTokenEconomics(asset)`. Nonzero economics and approval are required; neither the symbol nor an image proves eligibility.

Use the asset's decimals. An Apple-linked token is not automatically 18 decimals, redeemable for one share, or available to this wallet. Verify its issuer and legal terms separately.

## Pin the reviewed terms

Read `previewLaunchEconomics(configId, pairToken)` immediately before creating and pass the resulting `expectedEconomics`. If terms change, the transaction should revert rather than silently accept different economics. Re-read and seek a fresh review; do not bypass the pin.

Read `launchFee()` rather than copying v1's launch fee. Confirm creator tax against `maxCreatorTaxBps()`. Supply a fresh salt for deterministic deployment, and record the predicted and actual addresses when relevant.

## Optional initial buy

The documented launch-and-buy router creates and buys atomically. For a native quote, fee and purchase value travel as native value. For an ERC-20 quote, approve the router for the intended quote amount and send only the native launch fee. Review the spender, allowance, token recipient, minimum-output protection and exemption list.

## Completion record

Record chain, factory, launch config, quote token, token address, curve address, transaction receipt, actual initial purchase and refunded amount. A submitted hash is not proof of a successful launch. Do not retry a timed-out submission until receipt and chain state have been checked.
