# 37 Development structure choice

CryptoStone EVM-compatible smart contract network से launch कर सकता है। यह users, wallets, explorers और marketplaces के साथ compatibility देता है।

Deployment status reference:

| Component | Status | Note |
| --- | --- | --- |
| STONX Token | Testnet / preparing | mining resource और liquidity unit |
| Gem NFT | Testnet / preparing | digital gemstone identity |
| Garnet Pool | Testnet focus | initial public testing |
| Other Pools | Preparing | closed until protocol validation |
| Randomness Standard | user entropy + multi-block entropy + prevrandao | upgraded baseline |
| Mainnet Status | Preparing | security review के बाद |

Architecture components:

* STONX Token
* CryptoStone Gem NFT
* Mining Pool Template
* Pool Factory
* Marketplace
* Refinery
* Arena
* Metadata API और watcher

Long-term में CryptoStone Appchain या independent mainnet पर विकसित हो सकता है, लेकिन यह तभी उचित है जब users, liquidity, validators और developer ecosystem पर्याप्त हों।