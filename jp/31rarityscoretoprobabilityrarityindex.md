# 31\_Rarity\_ScoreとProbability\_Rarity\_Index

CryptoStoneは、各宝石の希少度を数値化するために2つの指標を使用する。

| 指標                       | 目的                      |
| ------------------------ | ----------------------- |
| Rarity Score             | ユーザーが直感的に理解できる0〜100のスコア |
| Probability Rarity Index | 実際の発生確率に基づく数学的希少度指標     |

## 31.1 Rarity Score

Rarity Score

$$
= \text{Stone Scarcity Score}
+ \text{Weight Score}
+ \text{Color Score}
+ \text{Clarity Score}
+ \text{Cut Score}
$$

スコア配分は次のとおりである。

| Attribute      | Max Score |
| -------------- | --------: |
| Stone Scarcity |        20 |
| Weight         |        25 |
| Color          |        15 |
| Clarity        |        20 |
| Cut            |        20 |
| Total          |       100 |

Stone Scarcity Scoreは、ストーン別総発行量を基準に計算される。

$$
\text{Stone Scarcity Score}
= 20 \times \frac{\text{MaxCollectionSupply} - \text{StoneMaxSupply}}{\text{MaxCollectionSupply} - \text{MinCollectionSupply}}
$$

基準値は次のとおりである。

* MaxCollectionSupply = 220,000
* MinCollectionSupply = 110,000

たとえば、DiamondのMax Supplyは110,000個であるため、最も高いStone Scarcity Scoreを持つ。

ZirconのMax Supplyは220,000個であるため、最も低いStone Scarcity Scoreを持つ。

## 31.2 Probability Rarity Index

Rarity Scoreがユーザーフレンドリーな比較指標であるなら、Probability Rarity Indexは各属性の発生確率に基づく数学的希少度指標である。

Gem NFT `g` の属性組み合わせが発生する確率 `P(g)` は、次のように定義される。

$$
P(g) = P_{stone} \times P_{weight} \times P_{color} \times P_{clarity} \times P_{cut}
$$

これを基に、確率ベース希少度指標を算定する。

$$
\text{Probability Rarity Index} = -\log_{10}(P(g))
$$

この指標は、特定Gem NFTが確率的にどれほど希少な組み合わせであるかを示す。

たとえば、次の組み合わせは極めて希少である。

* Diamond
* 100.00 CT以上
* D Color
* FL Clarity
* 6 Star Cut

このような組み合わせは、Rarity Score上でも高いスコアを受けるだけでなく、Probability Rarity Indexにおいても非常に高い希少度を持つ。

CryptoStoneは、この2つの指標を併用することで、コレクターが直感的に理解できるスコア体系と、データベースで検証可能な希少度体系を同時に提供する。
