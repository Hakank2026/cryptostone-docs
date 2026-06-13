# 46 结论

CryptoStone 是一个在智能合约上实现数字宝石概念的协议。

CryptoStone 将 STONX 定义为挖矿资源，将 Gem NFT 定义为挖矿结果，并通过 Proof of Mining，即 PoM，将二者连接起来。用户将 STONX 投入挖矿池，随着时间累积 Mining Power 与 PoM，并在达到所需阈值后 claim Gem NFT。

## 核心结构

| 项目 | 结构 |
| ---- | ---- |
| Mining Resource | STONX |
| Initial Supply | 1,200,000,000 STONX |
| Mining Result | CryptoStone Gem NFT |
| Stone Types | 12 个基于诞生石的矿池 |
| Attribute Generation | Weight, Color, Clarity, Cut, Rarity |
| Metadata | HTTPS metadata API + watcher finalization + IPFS media |
| Rarity Standard | Rarity Score + Probability Rarity Index |

## 协议执行结构

| 阶段 | 说明 |
| ---- | ---- |
| Participation | 从 1,000 STONX 起参与挖矿池 |
| Mining Power | 根据质押数量、锁仓期限与矿池参数计算 |
| PoM | 随时间累积的挖矿工作量 |
| Claim | 达到所需 PoM 阈值后 claim Gem NFT |
| Claim Burn | 2 STONX x Scarcity Multiplier |
| Maturity Burn | 根据锁仓期限产生折旧销毁 |
| Randomness | 用户熵、近期多区块熵、`prevrandao`、claim 状态、合约固有值 |
| Finalization | 核心属性在 claim 时确定，媒体由 watcher 后续更新 |
| Open Verification | 源代码、审计报告、LP 处理记录、概率表验证 |

CryptoStone 的目的并不是把 NFT 与现实宝石所有权连接起来，而是将挖矿难度、稀缺性、个体属性和收藏价值这一宝石结构，重新解释为数字原生资产模型。

本白皮书并不主张 CryptoStone 是伟大的发现或完全全新的发明。它是一种视角转换，也是一种新的尝试。不过，如果宝石属性、稀缺性和收藏性能够被市场认可为有意义的价值体系，CryptoStone 可能发展为“数字宝石”这一新类别。

CryptoStone 应继续通过透明合约、可验证随机性、公开供应数据、安全元数据结构，以及让用户更容易理解和验证的工具来发展。
