# 37 Development Structure

CryptoStone adopts the following structure.

* STONX Token
* CryptoStone Gem NFT
* 12 Mining Pool Contracts
* Pool Factory

This structure is designed to implement a digital gemstone protocol that is not permanently dependent on a specific chain. In the initial phase, an EVM-compatible smart contract network is used as the Launch Network.

## Current Deployment Status

The following table summarizes the current testnet deployment status and protocol-document baseline. If mainnet deployment or contract upgrades occur, addresses and versions will be updated in separate public documentation.

| Item | Current Status | Notes |
| ---- | -------------- | ----- |
| Launch Network | Ethereum Sepolia | Testnet operation baseline |
| STONX Token | `0xBd10DA40Dec511c11100dd2927dDf8c53A5248Ed` | ERC-20 testnet deployment |
| GEMS NFT | `0x01CE9e3Ee0fb51B6b0cE1E5B3C72A5F981A50056` | V5.3 HTTPS metadata structure |
| Garnet Mining Pool | `0xd885D9865A1e7C9094EcD0982421bE9670Fabe16` | Current live pool |
| Other 11 Mining Pools | Preparing | Mainnet or sequential opening target |
| Refinery | `0xB7b55068163d6d8E4f8eD2e8B511e234520576DC` | Testnet refinement feature |
| Marketplace | `0x673d64550c718A3770064ee3cDdC8b20093D0913` | Testnet NFT trading feature |
| Metadata Model | HTTPS API + watcher finalization + IPFS media | Separates core attributes from media display layer |
| Randomness Standard | User entropy + multi-block entropy + `prevrandao` | New pool and upgrade baseline |
| Mainnet Status | Preparing | To proceed after security review, documentation alignment, and liquidity policy finalization |

## Rationale

| Choice | Reason |
| ------ | ------ |
| STONX Token | Provides a unified mining resource and liquidity structure |
| CryptoStone Gem NFT | Represents the uniqueness and attributes of each gemstone |
| 12 Mining Pools | Implements independent digital mines for each stone |
| Pool Factory | Deploys pools from the same verified template |
| Unified NFT Contract | Concentrates collection identity and trading data |
| Verifiable Randomness | Enables attribute generation without operator manipulation |
| Finalize Mechanism | Prevents changes to core rules |

First, STONX and Gem NFT roles are separated. STONX is the token for Mining Power, while Gem NFT is the mined result.

Second, gemstone uniqueness is protected. Each Gem NFT has a tokenId and attribute combination, and its attributes cannot be changed after minting.

Third, independence between stones is maintained. Each mining pool has its own supply, mining interval, and halving structure, making it suitable for representing real-world individual mines in digital form.

Fourth, the NFT collection remains unified. This concentrates CryptoStone's brand and market data, enabling unified management of trading and rarity ranking.

Fifth, the structure has strong future extensibility. CryptoStone can begin on an EVM-compatible Launch Network and may later expand into an independent Appchain or CryptoStone Mainnet.

Sixth, centralization dependency is reduced. Mining and minting are executed by contracts rather than a server, and anyone can verify the conditions.
