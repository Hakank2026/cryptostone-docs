# 35 STONX 销毁结构

在 CryptoStone 中，STONX 不只是支付手段，而是参与数字宝石挖矿的挖矿资源。正如现实矿山中设备和能源会被使用，并且设备会随着时间磨损一样，投入 CryptoStone 挖矿池的 STONX 在挖矿过程中也具有一定的数字折旧结构。

开发者认为，STONX 的销毁结构并不是为了保证代币价格上涨，而是为了表达数字宝石挖矿所需的资源消耗与稀缺性结构。

CryptoStone 的基础 STONX 销毁结构主要发生在两种情况下。

| 销毁类型 | 发生时点 | 目的 |
| -------- | -------- | ---- |
| Claim Burn | claim Gem NFT 时 | 表达挖矿成本与稀缺性 |
| Maturity Burn | lock-up 到期后 unstake 时 | 表达挖矿资源折旧 |

以上两项是 CryptoStone 的基础销毁结构。随着生态扩展，STONX 销毁机制可以增加。例如，Marketplace 手续费的一部分销毁、Arena 或其他游戏模块的 entry fee/settlement 销毁、Gem Refinement 执行费用销毁等，都可以成为额外销毁路径。这些扩展销毁应在不破坏核心挖矿规则的范围内，通过独立合约和公开规则定义。

claim Gem NFT 时发生的销毁量 (B\_{claim,j}) 按以下公式计算。

$$
B_{claim,j} = \beta \times S_j
$$

其中，(\beta) 是 Base Claim Burn，(S\_j) 是对应宝石的 Scarcity Multiplier。

Claim Burn 并不是所有矿池都固定为 2 STONX。基础值为 2 STONX，但实际销毁量会根据各宝石矿池的 Scarcity Multiplier 而变化。例如，某个矿池处于 2x 区间时，claim 时销毁 4 STONX；处于 4x 区间时，销毁 8 STONX。因此，Claim Burn 是反映各矿池挖矿进度与难度的动态销毁成本。

初始基准值如下。

| Scarcity Multiplier | Claim Burn |
| ------------------- | ---------- |
| 1x | 2 STONX |
| 2x | 4 STONX |
| 4x | 8 STONX |
| 8x | 16 STONX |
| 16x | 32 STONX |
| 32x | 64 STONX |

Base Claim Burn 是表达挖矿成本的最小消费结构，并不是为了快速压缩总供应量。被销毁的 STONX 不会支付给运营方或基金会，而是永久从流通量中移除。通过这一结构，STONX 不只是被存入的资产，而是在 CryptoStone 生态中实际被使用和消耗的数字挖矿资源。
