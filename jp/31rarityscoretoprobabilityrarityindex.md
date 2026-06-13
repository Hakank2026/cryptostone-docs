# 31 Rarity ScoreとProbability Rarity Index

CryptoStoneは、各宝石の希少度を数値化するために2つの指標を使用する。

| 指標 | 目的 |
| ---- | ---- |
| Rarity Score | ユーザーが直感的に理解できる0~100のスコア |
| Probability Rarity Index | 実際の発生確率に基づく数学的な希少度指標 |

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

スコア配分は次のとおりである。

| Attribute | Max Score |
| --------- | --------: |
| Pool Supply Score | 20 |
| Weight | 20 |
| Color | 20 |
| Clarity | 20 |
| Cut | 20 |
| Total | 100 |

Pool Supply Scoreは、ストーン別Max Supplyを基準に計算される。この項目は、特定のストーンを他のストーンより自動的に高い希少度として評価するためのボーナスではない。むしろMax Supplyが少ないプールほど基本点を低く設定し、そのプールで高い最終等級に到達しにくくする難易度補正項目である。

$$
\text{Pool Supply Score}
=
15 + 5 \times
\frac{\text{StoneMaxSupply} - \text{MinCollectionSupply}}
{\text{MaxCollectionSupply} - \text{MinCollectionSupply}}
$$

基準値:

* MaxCollectionSupply = 220,000
* MinCollectionSupply = 110,000

Pool Supply Scoreは15点から20点の固定値として使用する。

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

たとえば、DiamondのMax Supplyは110,000個であるため、最も低いPool Supply Scoreを持つ。ZirconのMax Supplyは220,000個であるため、最も高いPool Supply Scoreを持つ。そのため、Diamond PoolでEpic、Legendary、Genesisを獲得することはより難しい。一方で、そのように採掘された高等級Diamond Gem NFTは、低い供給量と高い等級を同時に満たすため、市場でより高い収集価値を形成し得る。

この構造は、プール間の優劣を単純な点数で固定するものではない。各プールの発行量差を最終等級の難易度へ反映するための仕組みである。

## 31.2 Probability Rarity Index

Rarity Scoreがユーザーに分かりやすい比較指標であるなら、Probability Rarity Indexは各属性の発生確率に基づく数学的希少度指標である。

Gem NFT (`g`) の属性組み合わせが発生する確率 (`P(g)`) は次のように定義される。

$$
P(g) = P_{\text{stone}} \times P_{\text{weight}} \times P_{\text{color}} \times P_{\text{clarity}} \times P_{\text{cut}}
$$

これを基に、確率ベース希少度指標を算定する。

$$
\text{Probability Rarity Index} = -\log_{10}(P(g))
$$

この指標は、特定Gem NFTの属性組み合わせが統計的にどれほど希少であるかを示す。

Rarity Scoreは、最終等級算定のユーザーフレンドリーな基準として使われる。基本等級区間は次のとおりである。

| Final Tier | Rarity Score Range | 役割 |
| ---------- | ------------------ | ---- |
| Common | 0 ~ 34 | 最も一般的な宝石群、基本収集層および精錬材料 |
| Rare | 35 ~ 50 | 通常の採掘結果より希少な中間収集層 |
| Epic | 51 ~ 74 | ユーザーが意味ある成功として認識できる高等級区間 |
| Legendary | 75 ~ 89 | 非常に希少な高価値収集区間 |
| Genesis | 90 ~ 100 | 極端な属性組み合わせと最高点が反映された最上位区間 |

上記の点数区間は、Pool Supply Score 15~20とWeight、Color、Clarity、Cutの点数表を共に適用したとき、平均的に約36個の採掘につきEpic以上が1個期待される水準を目標とする。実際の結果はランダム属性組み合わせとプール別供給補正値によって変わる。

CryptoStoneは、Rarity ScoreとProbability Rarity Indexを併用することで、コレクターが直感的に理解できる点数体系と、データに基づいて検証可能な希少度体系を同時に提供する。
