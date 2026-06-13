# 15 STONX 分配结构

在 CryptoStone 中，STONX 是参与数字宝石挖矿的单一挖矿资源。开发者认为，STONX 的分配结构不应通过向特定内部人预先授予权利的方式形成，而应遵循任何人都可以在透明规则下访问的公开市场型结构。

因此，STONX 被设计为没有团队分配、创始人储备或隐藏内部人分配的市场公开型分配模型。总供应量分配给 DEX 流动性、直接销售、战略生态伙伴以及上市与流动性准备。

| 项目 | 结构 |
| ---- | ---- |
| Total Supply | 1,200,000,000 STONX |
| Team Allocation | 无 |
| Founder Reserve | 无 |
| Hidden Insider Allocation | 无 |
| Additional Mint | 无 |
| Primary Utility | 参与 Gem NFT 挖矿池 |
| Mechanism | 获取 STONX -> 质押 -> 生成 Mining Power -> 累积 PoM -> claim Gem NFT |
| Supply Trust | 发行量、矿池结构、概率表、claim 条件可通过合约和公开数据验证 |

## 15.1 Allocation

| Allocation | Ratio | TGE Unlock | Lock / Vesting | 理由 |
| ---------- | ----: | ---------- | -------------- | ---- |
| DEX Liquidity Reserve | 50% | 仅在初始流动性需要的范围内分阶段投入 | LP 长期锁定或销毁，剩余部分在流动性扩展时分阶段使用 | 最大化任何人都可进入的链上入口 |
| Direct Sale Pool | 20% | 在销售合约限制内公开销售 | 未售出部分保留在池中并分阶段供应 | 提供直接获取挖矿参与所需 STONX 的路径 |
| Strategic / VC Allocation | 10% | 0% 或有限初始解锁 | 6 个月 cliff + 24 个月线性 vesting | 用于交易所、基础设施和战略生态伙伴 |
| Listing / Liquidity Reserve | 20% | 仅在上市准备和做市需要范围内使用 | 公开钱包管理、限制用途、分阶段执行 | 支持中心化交易所流动性、活动和市场稳定 |

DEX Liquidity Reserve 占比最高，是因为 STONX 的核心入口应当是公开市场。Direct Sale Pool 帮助新用户无需经过复杂交易路径即可获得参与挖矿所需的 STONX。Strategic / VC Allocation 仅限生态扩展伙伴使用，并通过长期 vesting 减少短期抛压。Listing / Liquidity Reserve 是用于上市、做市、活动和市场稳定准备的目的型储备。

用户可以通过公开市场或直接销售路径获得 STONX，并将其投入自己选择的宝石挖矿池。随后，用户基于质押的 STONX 生成 Mining Power，并随着时间累积 Proof of Mining，即 PoM。当累积 PoM 达到对应矿池所需阈值时，用户即可 claim Gem NFT。

在这一结构中，DEX 与 Direct Sale 是进入 STONX 的公开入口，挖矿池则是 STONX 的实际使用场景。也就是说，STONX 的目的不是单纯持有或投机流通，而是作为参与数字宝石挖矿的协议资源发挥作用。

为了让公开型分配结构获得信任，初始流动性供应方式、LP 处理方式、合约权限、不可追加发行、主要储备钱包都应被明确公开。初始 LP 代币最好以长期锁定或销毁方式公开处理。这有助于降低对流动性撤回的担忧，并增强对 STONX 公开市场访问模型的信任。

CryptoStone 的信任并不来自特定主体的特权分配，而是来自固定总供应量、无团队分配、不可变更的挖矿规则、可验证的 PoM 结构以及链上透明性。
