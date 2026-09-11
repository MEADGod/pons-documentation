# PONS Lightweight Documentation

A compact, unofficial reference for launching and understanding tokens on **pons**.

Official documentation: https://docs.ponsfamily.com/

Launchpad: https://www.ponsfamily.com/launchpad

Robinhood Chain explorer: https://robinhoodchain.blockscout.com/

> Reviewed against the public PONS documentation on 11 September 2026. Live interfaces, fees, thresholds, contracts, and protocol behavior can change. Verify current values in the official documentation and wallet transaction before signing.

## At a Glance

PONS is an interface for launching and trading user-created tokens on Robinhood Chain. PONS does not hold user funds; each launch and trade is submitted as a transaction for the connected wallet to approve.

Current documentation states that:

- tokens launch on Robinhood Chain;
- the network chain ID is `4663`;
- launches use Uniswap V3 pools;
- each token trades against WETH;
- the fixed token supply is one billion tokens;
- the pool fee is 1%;
- the launch fee is 0.0005 ETH;
- pool liquidity is locked automatically;
- the default graduation threshold is 4.2 ETH of paired WETH;
- there is no bonding curve and no later migration; and
- trading continues in the same pool after graduation.

## Folder Contents

```text
pons-light-docs/
├── README.md
├── docs/
│   ├── INTEGRATION.md
│   ├── LAUNCH_TOKEN.md
│   ├── PROTOCOL.md
│   └── RISKS.md
├── examples/
│   └── ponsi-launch.example.json
└── SOURCES.md
```

## Example Token

The example included in this folder is fictional:

- **Name:** The Ponsi
- **Ticker:** `$PONSI`
- **Description:** The Ponsi, paired with NVDA.

“Paired with NVDA” is a narrative reference only. According to the PONS documentation, the actual onchain pool pair is **WETH**, not NVDA stock or an NVDA-linked asset.

See [`docs/LAUNCH_TOKEN.md`](docs/LAUNCH_TOKEN.md) for the full example.

## Important Safety Notes

Tokens launched through PONS are user-created and experimental. Graduation is a threshold event, not a quality signal. Locked liquidity does not guarantee price stability, market depth, future liquidity, or an exit.

Always verify:

- the network;
- token contract address;
- creator and fee recipient;
- pool address;
- holder concentration;
- transaction parameters;
- price impact and slippage; and
- wallet transaction preview.

Never share a private key or seed phrase.
