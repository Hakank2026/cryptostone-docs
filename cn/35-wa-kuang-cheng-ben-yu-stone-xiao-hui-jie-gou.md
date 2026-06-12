# 35\_挖矿成本与\_STONE\_销毁结构

在 CryptoStone 中，STONE 并不仅仅是支付工具，而是参与数字宝石挖矿所需的挖矿资源。正如现实矿山中使用挖矿设备和能源，且设备会随着时间折旧一样，在 CryptoStone 中，投入挖矿池的 STONE 也会在挖矿过程中具有一定的数字折旧结构。

本文作者认为，STONE 的销毁结构并不是为了保证代币价格上涨，而是为了表达数字宝石挖矿所需的资源消耗和稀缺性结构。

CryptoStone 中的 STONE 销毁主要可能发生在两种情况下。

| 销毁类型          | 发生时间            | 目的         |
| ------------- | --------------- | ---------- |
| Claim Burn    | claim Gem NFT 时 | 表达挖矿成本与稀缺性 |
| Maturity Burn | 锁仓结束后 unstake 时 | 表达挖矿资源折旧   |

claim Gem NFT 时发生的销毁量 (B\_{claim, j}) 通过以下公式计算。

$$
B_{claim,j} = \beta \times S_j
$$

其中，(\beta) 是 Base Claim Burn，(S\_j) 是该宝石的 Scarcity Multiplier。

初始基准值设定如下。

\[ \beta = 20 \text{ STONE} ]

| Scarcity Multiplier | Claim Burn |
| ------------------- | ---------- |
| 1x                  | 20 STONE   |
| 2x                  | 40 STONE   |
| 4x                  | 80 STONE   |
| 8x                  | 160 STONE  |
| 16x                 | 320 STONE  |
| 32x                 | 640 STONE  |

Base Claim Burn 是表达挖矿成本的最低消耗结构，并不是为了快速减少整体供应量而设计的机制。被销毁的 STONE 不会支付给运营方或基金会，而是永久从流通量中移除。通过这一机制，STONE 不仅仅是被存入的资产，而是在 CryptoStone 生态中实际被使用并消耗的数字挖矿资源。
