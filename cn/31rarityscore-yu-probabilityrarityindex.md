# 31\_Rarity\_Score\_与\_Probability\_Rarity\_Index

CryptoStone 使用两个指标来量化每颗宝石的稀有度。

| 指标                       | 目的                 |
| ------------------------ | ------------------ |
| Rarity Score             | 用户可直观理解的 0\~100 分数 |
| Probability Rarity Index | 基于实际发生概率的数学稀有度指标   |

## 31.1 Rarity Score

Rarity Score：

$$
\text{Rarity Score}
=
\text{Stone Scarcity Score}
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

| Attribute      | Max Score |
| -------------- | --------- |
| Stone Scarcity | 20        |
| Weight         | 25        |
| Color          | 15        |
| Clarity        | 20        |
| Cut            | 20        |
| Total          | 100       |

Stone Scarcity Score 基于各宝石总发行量计算：

$$
\text{Stone Scarcity Score}
=
20 \times
\frac{\text{MaxCollectionSupply} - \text{StoneMaxSupply}}{\text{MaxCollectionSupply} - \text{MinCollectionSupply}}
$$

基准值如下：

* `MaxCollectionSupply = 220,000`
* `MinCollectionSupply = 110,000`

例如，Diamond 的 Max Supply 为 110,000 个，因此拥有最高的 Stone Scarcity Score。Zircon 的 Max Supply 为 220,000 个，因此拥有最低的 Stone Scarcity Score。

## 31.2 Probability Rarity Index

如果说 Rarity Score 是用户友好的比较指标，那么 Probability Rarity Index 则是基于各属性发生概率的数学稀有度指标。

Gem NFT `g` 的属性组合发生概率 `P(g)` 定义如下：

$$
P(g) = P_{\text{stone}} \times P_{\text{weight}} \times P_{\text{color}} \times P_{\text{clarity}} \times P_{\text{cut}}
$$

基于该概率，可以计算概率型稀有度指标：

$$
\text{Probability Rarity Index} = -\log_{10}(P(g))
$$

该指标显示特定 Gem NFT 的属性组合在概率上有多稀有。

例如，以下组合极为稀有：

* Diamond
* 100.00 CT 以上
* D Color
* FL Clarity
* 6 Star Cut

这样的组合不仅会在 Rarity Score 中获得高分，在 Probability Rarity Index 中也会具有非常高的稀有度。

CryptoStone 同时使用这两个指标，从而既提供收藏者可直观理解的分数体系，也提供基于数据且可验证的稀有度体系。
