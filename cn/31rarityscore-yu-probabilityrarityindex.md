# 31 Rarity Score 与 Probability Rarity Index

CryptoStone 使用两个指标来量化每颗宝石的稀有度。

| 指标 | 目的 |
| ---- | ---- |
| Rarity Score | 用户可直观理解的 0~100 分数 |
| Probability Rarity Index | 基于实际发生概率的数学稀有度指标 |

## 31.1 Rarity Score

$$
\text{Rarity Score}
=
\text{Pool Supply Score}
+
\text{Weight Score}
+
\text{Color Score}
+
\text{Clarity Score}
+
\text{Cut Score}
$$

分数分配如下。

| Attribute | Max Score |
| --------- | --------: |
| Pool Supply Score | 20 |
| Weight | 20 |
| Color | 20 |
| Clarity | 20 |
| Cut | 20 |
| Total | 100 |

Pool Supply Score 基于每种宝石的 Max Supply 计算。该项目并不是为了让某一种宝石自动获得更高稀有度的奖励。相反，Max Supply 越低的矿池会获得越低的基础分数，使其更难达到高等级最终结果。

$$
\text{Pool Supply Score}
=
15 + 5 \times
\frac{\text{StoneMaxSupply} - \text{MinCollectionSupply}}
{\text{MaxCollectionSupply} - \text{MinCollectionSupply}}
$$

基准值如下。

* MaxCollectionSupply = 220,000
* MinCollectionSupply = 110,000

Pool Supply Score 使用 15 到 20 之间的固定值。

| Stone | Max Supply | Pool Supply Score |
| ----- | ---------: | ----------------: |
| Diamond | 110,000 | 15.0 |
| Emerald | 120,000 | 15.5 |
| Ruby | 130,000 | 15.9 |
| Sapphire | 140,000 | 16.4 |
| Pearl | 150,000 | 16.8 |
| Garnet | 160,000 | 17.3 |
| Amethyst | 170,000 | 17.7 |
| Aquamarine | 180,000 | 18.2 |
| Spinel | 190,000 | 18.6 |
| Opal | 200,000 | 19.1 |
| Topaz | 210,000 | 19.5 |
| Zircon | 220,000 | 20.0 |

例如，Diamond 的 Max Supply 为 110,000，因此拥有最低的 Pool Supply Score。Zircon 的 Max Supply 为 220,000，因此拥有最高的 Pool Supply Score。因此，在 Diamond Pool 中获得 Epic、Legendary、Genesis 会更困难。但这样挖出的高等级 Diamond Gem NFT 同时满足低供应量与高等级两个条件，因此可能在市场中形成更高的收藏价值。

这一结构并不是用简单分数固定矿池之间的优劣，而是将各矿池发行量差异反映到最终等级难度中。供应量较低的矿池更难获得高等级结果，供应量较高的矿池相对更容易。

## 31.2 Probability Rarity Index

如果说 Rarity Score 是面向用户的直观比较指标，那么 Probability Rarity Index 则是基于各属性发生概率的数学稀有度指标。

Gem NFT (`g`) 的属性组合发生概率 (`P(g)`) 定义如下。

$$
P(g) = P_{\text{stone}} \times P_{\text{weight}} \times P_{\text{color}} \times P_{\text{clarity}} \times P_{\text{cut}}
$$

由此计算概率型稀有度指标。

$$
\text{Probability Rarity Index} = -\log_{10}(P(g))
$$

该指标用于显示某个 Gem NFT 的属性组合在统计上有多稀有。

Rarity Score 用作最终等级计算的用户友好标准。基础等级区间如下。

| Final Tier | Rarity Score Range | 角色 |
| ---------- | ------------------ | ---- |
| Common | 0 ~ 34 | 最常见的宝石群，基础收藏层与精炼材料 |
| Rare | 35 ~ 50 | 比普通挖矿结果更稀有的中间收藏层 |
| Epic | 51 ~ 74 | 用户可感知为有意义成功的高等级区间 |
| Legendary | 75 ~ 89 | 非常稀有的高价值收藏区间 |
| Genesis | 90 ~ 100 | 反映极端属性组合与最高分的顶级区间 |

当 Pool Supply Score 15~20 与 Weight、Color、Clarity、Cut 分数表共同适用时，该区间目标是平均每挖出约 36 个 NFT，可期待 1 个 Epic 或以上结果。实际结果会因随机属性组合与矿池供应修正值而变化。

CryptoStone 同时使用 Rarity Score 与 Probability Rarity Index，为收藏者提供直观分数体系与基于数据的可验证稀有度体系。
