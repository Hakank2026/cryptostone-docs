# 30 属性生成与随机性

宝石属性并不是由运营方手动输入的。在挖矿时，挖矿合约会基于随机值确定 Weight、Color、Clarity 与 Cut。

关键在于，随机生成方式必须可验证。如果运营方能够任意生成高等级 NFT，CryptoStone 的去中心化与稀缺性就会受到破坏。

CryptoStone 通过组合用户提供的熵、近期多区块熵、Ethereum `prevrandao`、Claim 状态值以及合约固有值，降低对单一随机要素的依赖。

其结构可以表示为:

$$
S = H(userEntropy, user, positionId, claimNonce, prevrandao, chainId, contract)
$$

$$
B_i = blockhash(blockNumber - 1 - (H(S,i) \bmod 30)) \quad \text{for } i \in \{0..4\}
$$

$$
R = H(userEntropy, B_0, B_1, B_2, B_3, B_4, prevrandao, claimState, contractState)
$$

该模型不依赖单一区块值或单一用户值。它混合用户熵、多个近期区块引用、Ethereum 共识熵以及 claim 相关状态，以降低可预测性和运营方依赖。

CryptoStone 的随机生成方式遵循以下原则。

| 原则 | 说明 |
| ---- | ---- |
| 不可预测性 | 运营方与用户都不应提前知道结果 |
| 不可选择结果 | 运营方不得选择有利结果或拒绝不利结果 |
| 防止重试 | 随机请求后，在结果确定前用户不得取消或重试 |
| No Admin Reroll | 运营方不得重抽或替换特定结果 |
| 公开验证 | 结果生成过程必须链上或公开可验证 |
| 固定概率表 | 属性概率表必须在部署前公开，并在 finalization 后不可更改 |
| 发行后不可变 | 发行后的属性不得被更改 |

随机结果被请求后，用户不得因为结果不利而取消或重试 claim。运营方也不得向特定用户分配有利结果，或选择会产生特定属性组合的 seed。这是确保稀有宝石由可验证随机结构产生，而不是由运营方裁量产生的核心条件。

发行后，Gem NFT 的核心属性必须被冻结。Weight、Color、Clarity、Cut、stoneType、minedAt、minedFromPool 等核心元数据不得被运营方更改。
