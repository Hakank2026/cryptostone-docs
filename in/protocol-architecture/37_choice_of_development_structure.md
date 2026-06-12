# 37\_choice\_of\_development\_structure

CryptoStone adopts the following structure:

* STONE Token
* CryptoStone Gem NFT
* 12 Mining Pool Contracts
* Pool Factory

This structure is designed to implement a digital gemstone protocol that is not dependent on a specific chain. Initially, an EVM-compatible smart contract network is used as the Launch Network.

| Choice                | Reason                                                      |
| --------------------- | ----------------------------------------------------------- |
| STONE Token           | Provides a single mining resource and liquidity structure.  |
| CryptoStone Gem NFT   | Expresses the uniqueness and attributes of each gemstone.   |
| 12 Mining Pools       | Implements independent mine structures by stone.            |
| Pool Factory          | Deploys pools using the same verified template.             |
| Unified NFT Contract  | Concentrates collection identity and transaction data.      |
| Verifiable Randomness | Enables attribute generation without operator manipulation. |
| Finalize Mechanism    | Prevents changes to core rules.                             |

First, the roles of STONE and Gem NFT are separated. STONE is the token for Mining Power, and Gem NFT is the mining result.

Second, the uniqueness of gemstones is protected. Each Gem NFT has a tokenId and attribute combination, and attributes cannot be changed after issuance.

Third, independence by stone is maintained. Each mining pool has independent supply, mining interval, and halving, making it suitable for digitally expressing the concept of individual real-world mines.

Fourth, the NFT collection is maintained as one collection. This concentrates the CryptoStone brand and market data, and allows integrated management of trading and rarity rankings.

Fifth, future scalability is high. CryptoStone can start on an EVM-compatible Launch Network and expand into an independent Appchain or CryptoStone Mainnet in the long term.

Sixth, dependence on centralization is reduced. Mining and issuance are executed by contracts, not by servers, and anyone can verify the conditions.
