# 38\_protocol\_finalization\_principles

For CryptoStone to aim for decentralized asset characteristics similar to Bitcoin, its core rules must not be arbitrarily changed after deployment.

| Fixed Item                    | Description                                      |
| ----------------------------- | ------------------------------------------------ |
| Total STONX supply            | 1,200,000,000 STONX                              |
| STONX circulation structure   | Open Market Allocation                          |
| Max Supply by STONX           | Maximum NFT issuance quantity by each STONX      |
| Base Mining Interval by STONX | Basic mining interval                            |
| Target Pool Power             | Initial reference value of 40,000,000 Power      |
| Base Mining Unit              | 1,000 STONX                                      |
| Weight probability table      | Weight generation probability                    |
| Color probability table       | Color grade generation probability               |
| Clarity probability table     | Clarity grade generation probability             |
| Cut probability table         | Cut grade generation probability                 |
| Scarcity Multiplier           | Halving-based difficulty multiplier              |
| Claim Burn formula            | Burn formula at claim                            |
| Mining Power formula          | Staking-based Mining Power formula               |
| PoM formula                   | Proof of Mining accumulation and claim condition |
| Lock Multiplier               | Mining multiplier by lock-up period              |
| Maturity Burn formula         | Depreciation burn formula at lock-up maturity    |

Once initial settings are completed, the protocol should be finalized. After this, the operator must not be able to arbitrarily increase supply, change rarity probabilities, or manually issue NFTs to specific users.

The core contracts of CryptoStone should have source code publicly verified after deployment, and token supply, NFT supply, probability tables, mining formulas, and PoM threshold calculation structures must not be changeable after finalization.

If limited administrative functions are necessary before finalization, the list, purpose, removal timing, and control method of those functions must be clearly disclosed. After finalization, administrative authority related to core issuance quantity, probability tables, issuance rights, and PoM calculation method should be removed or disabled.

Decentralization is not completed simply because something is deployed on a blockchain. Decentralization is formed through rules that the operator cannot change, code that anyone can verify, and structures in which anyone can participate.
