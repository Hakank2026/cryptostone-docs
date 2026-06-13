# 05\_数字宝石资产的基本概念

CryptoStone 由一个 STONX Token、12 个宝石挖矿池以及一个 Gem NFT 合约构成。

| 构成要素                     | 作用                     |
| ------------------------ | ---------------------- |
| STONX Token              | 参与数字矿山所需的单一挖矿资源        |
| 12 Gemstone Mining Pools | 用于挖掘各诞生石的独立数字矿山        |
| CryptoStone Gem NFT      | 表达已挖掘数字宝石的唯一 NFT 资产    |
| Mining Pool Contract     | 管理质押、挖矿算力、难度和 claim 条件 |
| Gem NFT Contract         | 管理宝石 NFT 的属性、发行量和所有权   |

STONX 并不是宝石本身。STONX 是参与数字矿山所需的挖矿算力来源。用户通过将 STONX 质押到自己选择的宝石挖矿池中获得 Mining Power，并随着时间推移累积 PoM。

挖矿结果物是 CryptoStone Gem NFT。Gem NFT 由一个统一的 NFT 合约发行，每个 NFT 都以链上属性的形式保存其所属宝石种类、重量和等级等信息。

将现实宝石挖矿结构抽象化后，可以表示如下。

| 现实宝石挖矿  | CryptoStone                       |
| ------- | --------------------------------- |
| 矿山      | Gemstone Mining Pool              |
| 挖矿设备与能源 | STONX Token                       |
| 挖矿工作量   | Proof of Mining，PoM               |
| 挖矿结果物   | Gem NFT                           |
| 矿山难度    | Pool Difficulty                   |
| 储量减少    | Scarcity Multiplier               |
| 宝石鉴定    | On-chain Attribute & Rarity Score |
