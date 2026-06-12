# 38\_协议固定原则

为了使 CryptoStone 具备类似比特币的去中心化资产性，部署之后核心规则不得被任意更改。

| 固定项目                     | 说明                              |
| ------------------------ | ------------------------------- |
| STONE 总发行量               | 1,200,000,000 STONE             |
| STONE 流通结构               | 100% 公开流通                       |
| 各宝石 Max Supply           | 各宝石 NFT 最大发行量                   |
| 各宝石 Base Mining Interval | 基础挖矿周期                          |
| Target Pool Power        | 初始基准值 40,000,000 Power          |
| Base Mining Unit         | 100,000 STONE                   |
| Weight 概率表               | 重量生成概率                          |
| Color 概率表                | 颜色等级生成概率                        |
| Clarity 概率表              | 净度等级生成概率                        |
| Cut 概率表                  | 切工等级生成概率                        |
| Scarcity Multiplier      | 基于减半的难度倍率                       |
| Claim Burn               | 公式 claim 时销毁公式                  |
| Mining Power             | 公式 基于质押的挖矿算力公式                  |
| PoM                      | 公式 Proof of Mining 累积及 claim 条件 |
| Lock Multiplier          | 按锁仓期限计算的挖矿倍率                    |
| Maturity Burn            | 公式 锁仓结束时折旧销毁公式                  |

初始设置完成后，协议应被 finalize。此后，运营方不得任意增加发行量、更改稀有度概率，或手动为特定用户发行 NFT。

CryptoStone 的核心合约在部署后应公开验证源码，代币发行量、NFT 供应量、概率表、挖矿公式、PoM 阈值计算结构在 finalize 之后不得更改。

如果 finalize 之前存在必要的有限管理功能，则该功能清单、目的、移除时间和控制方式必须明确公开。

finalize 之后，与核心发行量、概率表、发行权限、PoM 计算方式相关的管理员权限应被移除或禁用。

去中心化并不是因为部署在区块链上就自动完成。去中心化形成于运营方无法更改的规则、任何人都能验证的代码，以及任何人都能参与的结构。
