# Bitcoin Real Token (BRT)

## Overview

Bitcoin Real Token (BRT) is a collateral-backed BRC-20 asset bridged onto the Bitcoin mainnet with transparent mint, transfer, and redemption flows backed by verifiable BTC reserves.

## Supply

- **Maximum supply:** 21,000,000 BRT
- **Circulating supply (initial mint):** 5,000,000 BRT
- **Collateralization:** 1.05 BTC reserve ratio per 1,000 BRT issued, held in a 3-of-5 multisig managed by the Bitcoin Real Token Reserve Council.

Supply expansions require on-chain governance approval and attestation of additional collateral deposits before mint requests are processed. Excess collateral cannot be withdrawn without a corresponding burn of outstanding BRT.

## Minting Flow

1. Reserve operators deposit BTC into the custodial multisig wallet (`bc1qn7k3z6l4dq9z70m36v5y5vhwjttep7g3l6rv4c`).
2. A proof-of-reserve transaction and Merkle proof are generated and published to the `proofs` directory of the GitHub repository.
3. Once collateral exceeds the required threshold, a mint inscription is submitted on Bitcoin specifying the BRC-20 ticker `brt`.
4. Newly minted BRT is distributed to participants according to the governance-approved allocation schedule.

## Transfers

BRT inherits standard BRC-20 transfer semantics:

- Transfers are performed through ordinal inscriptions referencing the `brt` ticker.
- All transfers settle on-chain and are visible through BRC-20 explorers such as UniSat.

## Collateral Monitoring

- Real-time dashboard: <https://bitcoinrealtoken.org/proof-of-reserves>
- GitHub proofs: <https://github.com/bitcoinrealtoken/proof-of-reserves>
- Open telemetry feed: `wss://stream.bitcoinrealtoken.org/reserves`

Reserve attestations are issued weekly and whenever collateral balances change materially. Independent auditors can verify balances by monitoring the multisig address and reconciling with the published proofs.

## Redemption

1. Holders submit a redemption request through the official portal.
2. BRT tokens are burned via a `brt` burn inscription.
3. BTC is released from the multisig after multi-party approval, minus redemption fees covering network costs.

## Governance & Contact

- Governance forum: <https://forum.bitcoinrealtoken.org>
- Emergency contact: `security@bitcoinrealtoken.org`

For integration assistance, open an issue at <https://github.com/bitcoinrealtoken/integrations>.
