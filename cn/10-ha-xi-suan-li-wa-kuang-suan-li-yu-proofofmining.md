# 10\_哈希算力\_挖矿算力与\_Proof\_of\_Mining

在比特币中，矿工通过哈希算力获得生成区块的概率。哈希算力越高，发现区块的可能性越高，但哈希算力无法任意改变比特币整体的发行规则或难度结构。也就是说，哈希算力并不是改变网络规则的权限，而是在既定规则中获得更多挖矿机会的计算资源。

CryptoStone 将这一概念抽象为适用于数字宝石挖矿的结构。在 CryptoStone 中，对应哈希算力的概念是 Mining Power，而 Mining Power 随时间累积形成的工作量就是 Proof of Mining，即 PoM。

| Bitcoin                     | CryptoStone              |
| --------------------------- | ------------------------ |
| Hash Power                  | Mining Power             |
| Proof of Work               | Proof of Mining，PoM      |
| ASIC / Mining Equipment     | Staked STONX             |
| Block Reward                | Gem NFT                  |
| Network Difficulty          | Pool Difficulty          |
| Halving Scarcity Multiplier |                          |
| BTC Issuance                | Gem NFT Minting          |
| Miner                       | STONX Staker / Gem Miner |

PoM 并不是可以单独转移或交易的代币。PoM 是合约根据用户的挖矿参与和时间流逝所记录的链上工作量指标。同时，PoM 也不是网络共识算法。CryptoStone 中的 PoM 是协议内部数值，用于判断用户是否已在特定宝石池中达到 claim Gem NFT 的条件。

当用户 i 在特定宝石池 j 中质押的 STONX 数量为 s<sub>i,j</sub>，锁仓期限对应的倍率为 L<sub>i</sub> 时，用户的挖矿算力 P<sub>i,j</sub> 定义如下：

$$
P_{i,j} = s_{i,j} \times L_i
$$

用户的 PoM 值会随着时间按如下方式累积：

$$
PoM_{i,j}(t + \Delta t) = PoM_{i,j}(t) + P_{i,j} \times \Delta t
$$

其中，PoM<sub>i,j</sub>(t) 表示用户 i 在宝石池 j 中截至时间 t 所累积的 Proof of Mining 值。

PoM 按宝石池独立累积。例如，在 Diamond Pool 中累积的 PoM 只能用于 claim Diamond NFT，不能转换为 Ruby Pool 或 Sapphire Pool 的 PoM。该结构保护了各宝石池的独立性、稀缺性和挖矿难度。

挖矿算力更高的用户可以更快达到所需 PoM 阈值，但不能任意提高获得稀有宝石的概率，也不能选择特定等级的宝石。
