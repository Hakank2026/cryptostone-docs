# 37\_开发结构的选择

CryptoStone 采用以下结构：

* STONE Token
* CryptoStone Gem NFT
* 12 个 Mining Pool Contract
* Pool Factory

该结构是为了实现一个不依赖特定链的数字宝石协议而设计的。初期将使用 EVM 兼容智能合约网络作为 Launch Network。

## 选择理由

1. STONE Token 提供单一挖矿资源和流动性结构。
2. CryptoStone Gem NFT 表达每颗宝石的唯一性与属性。
3. 12 Mining Pools 实现按宝石区分的独立矿山结构。
4. Pool Factory 通过同一验证模板部署矿池。
5. Unified NFT Contract 集中一个集合身份与交易数据。
6. Verifiable Randomness 实现无运营方操纵的属性生成。
7. Finalize Mechanism 防止核心规则变更。

第一，分离 STONE 与 Gem NFT 的角色。STONE 是用于 Mining Power 的代币，Gem NFT 是挖矿结果物。

第二，保护宝石的唯一性。每个 Gem NFT 拥有 tokenId 和属性组合，并且发行后属性不可更改。

第三，保持各宝石的独立性。每个挖矿池拥有独立供应量、挖矿周期和减半结构，因此适合以数字方式表达现实中的独立矿山概念。

第四，NFT 集合保持统一。这使 CryptoStone 的品牌和市场数据集中于一个集合，并能够统一管理交易和稀有度排名。

第五，具备较高的未来扩展性。CryptoStone 可以从 EVM 兼容 Launch Network 开始，长期可扩展为独立 Appchain 或 CryptoStone Mainnet。

第六，降低对中心化的依赖。挖矿与发行由合约执行，而不是由服务器执行，任何人都可以验证条件。
