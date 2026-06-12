# 41\_生态扩展模块与\_Gem\_Refinement

CryptoStone 的核心协议由 STONE、12 个宝石挖矿池、Proof of Mining 以及 Gem NFT 构成。不过，CryptoStone 生态并不局限于核心挖矿结构。未来可以通过添加独立智能合约，或与现有合约联动的扩展模块，发展出多种应用功能。这些扩展功能可以包括 Marketplace、Ranking System、Collection Quest、Gem Refinement 等。

Gem Refinement，即宝石精炼，是这些生态扩展模块之一。它是一种可选的后挖矿实用结构，使已挖掘的 Gem NFT 能够再次被使用。Gem Refinement 并不是无限追加发行 NFT 的结构，而是一种供应压缩机制：将两个拥有相同 `stoneType` 的 Gem NFT 结合，生成一个相同 `stoneType` 的 Refined Gem NFT。

```
2 个 Gem NFT
+ 少量 STONE 使用或销毁
→ Parent Gem NFTs Burned
→ 1 个 Refined Gem NFT Minted
```

每执行一次精炼，两个父级 Gem NFT 会被销毁或以不可恢复方式处理，只生成一个新的 Refined Gem NFT。因此，整体流通 NFT 数量会减少 1 个。

```
2 Gem NFTs Burned → 1 Refined Gem NFT Minted
Net Circulating NFT Supply = -1
```

初期 Gem Refinement 最好只允许同种宝石精炼。例如，2 个 Diamond Gem NFT 可以精炼为 1 个 Refined Diamond Gem NFT，2 个 Ruby Gem NFT 可以精炼为 1 个 Refined Ruby Gem NFT。不同宝石之间的精炼会使各宝石供应量、稀缺性、减半和挖矿难度结构变得复杂，因此在初期模型中排除更为合适。

## 项目原则

| 项目         | 原则                                  |
| ---------- | ----------------------------------- |
| 所需材料       | 2 个相同 `stoneType` 的 Gem NFT         |
| 追加费用       | 少量 STONE 使用或销毁                      |
| 父级 NFT 处理  | 2 个父级 Gem NFT 被销毁或不可恢复处理            |
| 结果物        | 1 个相同 `stoneType` 的 Refined Gem NFT |
| 世代信息       | 记录为 Gen1 或 Refined Generation       |
| 供应效果       | 整体流通 NFT 数量减少                       |
| 发行权限       | 限定于 Refining Contract               |
| Admin Mint | 无                                   |
| 随机性        | 使用可验证随机结构                           |

Refined Gem NFT 的基准等级可以根据两个父级 Gem NFT 中较高的等级进行计算。

$$
T_{base} = \max(T_1, T_2)
$$

其中，T1、T2 是两个父级 Gem NFT 的等级，Tbase 是用于确定精炼结果的基准等级。

等级体系可以简化如下。

| Tier Level | Tier      |
| ---------- | --------- |
| 1          | Common    |
| 2          | Rare      |
| 3          | Epic      |
| 4          | Legendary |

精炼结果中，出现与基准等级相同等级的概率应最高。一阶降级概率设置得非常低，即使发生升级，最多也限制在 1 至 2 个等级。同时，等级越低，其升级可能性可以相对更高；等级越高，升级可能性越低，从而保护高等级 Gem NFT 的稀缺性。

使用 0 至 9,999 的随机值 U 的 BPS 方式基本阈值示例如下。

$$
U \in [0, 9,999]
$$

10,000 BPS = 100%

| Base Tier | Tier -1 | Tier Same | Tier +1 | Tier +2 |
| --------- | ------- | --------- | ------- | ------- |
| Common    | 无       | 68.0%     | 27.0%   | 5.0%    |
| Rare      | 1.0%    | 76.0%     | 20.0%   | 3.0%    |
| Epic      | 1.5%    | 88.5%     | 10.0%   | 无       |
| Legendary | 2.0%    | 98.0%     | 无       | 无       |

在上述结构中，Common 与 Rare 通过精炼获得升级的可能性相对较高，但从 Epic 开始升级概率会明显降低。Legendary 被视为精炼模型中的最高等级，不允许继续升级。该结构在维持精炼期待感的同时，防止高等级 NFT 被过度生成。

当两个父级 Gem NFT 之间的等级差较大时，升级概率可以进一步调整。等级差 G 定义如下。

$$
G = |T_1 - T_2|
$$

| Tier Gap G | Upgrade Modifier 处理原则 |
| ---------- | --------------------- |
| 0          | 100% 同等级精炼，适用基础概率     |
| 1          | 70% 相邻等级精炼，部分降低升级概率   |
| 2          | 35% 较大等级差，大幅降低升级概率    |
| 3 以上       | 限制 初期模型中可限制精炼         |

升级概率可以按如下方式调整。

$$
Adjusted\ Upgrade\ Probability = Base\ Upgrade\ Probability \times Upgrade\ Modifier
$$

因调整而减少的升级概率，会被加入维持同等级的概率中。通过这种方式，可以限制用户反复将一个高等级 Gem NFT 与低等级 Gem NFT 结合来尝试生成更高等级结果的行为。

Refining Contract 会执行所有权验证、相同宝石验证、等级差验证、STONE 使用或销毁、父级 NFT 销毁、随机值请求以及 Refined Gem NFT 发行请求。Refined Gem NFT 不得由运营方任意发行，只能在 Refining Contract 验证预设条件后生成。

Gem Refinement 并不会替代 CryptoStone 的基础挖矿结构。它是为了在挖矿之后扩展 Gem NFT 的实用性、收藏性和交易需求而设计的可选模块。未来，CryptoStone 可以通过 Gem Refinement 以及其他扩展模块，逐步扩展数字宝石生态。
