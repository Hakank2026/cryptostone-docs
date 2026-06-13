# 46 Conclusion

CryptoStone is a protocol that implements the concept of digital gemstones on smart contracts.

It defines STONX as a mining resource and Gem NFT as the mined result, connecting the two through Proof of Mining, or PoM. Users deposit STONX into mining pools, accumulate Mining Power and PoM over time, and claim Gem NFTs once the required threshold is reached.

## Core Structure

| Item | Structure |
| ---- | --------- |
| Mining Resource | STONX |
| Initial Supply | 1,200,000,000 STONX |
| Mining Result | CryptoStone Gem NFT |
| Stone Types | 12 birthstone-based pools |
| Attribute Generation | Weight, Color, Clarity, Cut, Rarity |
| Metadata | HTTPS metadata API + watcher finalization + IPFS media |
| Rarity Standard | Rarity Score + Probability Rarity Index |

## Protocol Execution Structure

| Stage | Description |
| ----- | ----------- |
| Participation | Enter a mining pool from 1,000 STONX |
| Mining Power | Calculated from staked amount, lock-up period, and pool parameters |
| PoM | Mining work value accumulated over time |
| Claim | Gem NFT claim after reaching the required PoM threshold |
| Claim Burn | 2 STONX x Scarcity Multiplier |
| Maturity Burn | Depreciation burn based on lock-up period |
| Randomness | User entropy, recent multi-block entropy, `prevrandao`, claim state, and contract-specific values |
| Finalization | Core attributes fixed at claim; media updated later by watcher |
| Open Verification | Source code, audit reports, LP handling records, and probability tables |

CryptoStone's purpose is not to connect NFTs to real gemstone ownership. It is to reinterpret the structure of gemstones as a digital-native asset model: mining difficulty, scarcity, individual attributes, and collectible value.

This whitepaper does not claim that CryptoStone is a great discovery or a fundamentally new invention. It is a change of perspective and a new attempt. If gemstone attributes, scarcity, and collectibility are accepted by the market as a meaningful value system, CryptoStone may develop into a new category of digital gemstones.

CryptoStone should continue to evolve with transparent contracts, verifiable randomness, public supply data, secure metadata structure, and user-facing tools that make the system easier to understand and verify.
