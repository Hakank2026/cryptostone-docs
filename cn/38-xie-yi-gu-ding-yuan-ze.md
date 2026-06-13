# 38 协议固定原则

如果 CryptoStone 希望具备类似比特币的去中心化资产属性，部署后核心规则不得被任意更改。

| 固定项目 | 说明 |
| -------- | ---- |
| STONX 总发行量 | 1,200,000,000 STONX |
| STONX 分配结构 | DEX 50%、Direct Sale Pool 20%、Strategic / VC 10%、Listing / Liquidity Reserve 20% |
| 各宝石 Max Supply | 各宝石最大 NFT 发行量 |
| 各宝石 Base Mining Interval | 基础挖矿周期 |
| Target Pool Power | 初始基准值 40,000,000 Power |
| Base Mining Unit | 1,000 STONX |
| Weight 概率表 | 重量生成概率 |
| Color 概率表 | 颜色等级生成概率 |
| Clarity 概率表 | 净度等级生成概率 |
| Cut 概率表 | 切工等级生成概率 |
| Scarcity Multiplier | 基于减半的难度倍率 |
| Claim Burn 公式 | claim 时销毁公式 |
| Mining Power 公式 | 基于质押的 Mining Power 公式 |
| PoM 公式 | Proof of Mining 累积与 claim 条件 |
| Lock Multiplier | 按锁仓期限区分的 Mining 倍率 |
| Maturity Burn 公式 | 锁仓结束时的折旧销毁公式 |

初始设置完成后，协议应当 finalize。之后，运营方不得任意增加发行量、改变稀有度概率、或向特定用户手动发行 NFT。

CryptoStone 的核心合约在部署后应公开验证源代码，代币发行量、NFT 供应量、概率表、挖矿公式、PoM 阈值计算结构在 finalization 后不得更改。

如果在 finalization 前需要有限管理功能，则应明确公开这些功能的列表、目的、移除时间和控制方式。finalization 后，与核心发行量、概率表、发行权限、PoM 计算方式相关的管理员权限应被移除或禁用。

去中心化并不只是因为合约部署在区块链上就自动完成。去中心化来自运营方无法改变的规则、任何人都可验证的代码、以及任何人都可参与的结构。
