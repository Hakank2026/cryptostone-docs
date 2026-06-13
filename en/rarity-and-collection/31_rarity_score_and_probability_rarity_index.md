# 31 Rarity Score and Probability Rarity Index

CryptoStone uses two indicators to quantify the rarity of each gemstone.

| Indicator | Purpose |
| --------- | ------- |
| Rarity Score | A user-friendly 0~100 score |
| Probability Rarity Index | A mathematical rarity indicator based on actual occurrence probability |

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

The score allocation is as follows.

| Attribute | Max Score |
| --------- | --------: |
| Pool Supply Score | 20 |
| Weight | 20 |
| Color | 20 |
| Clarity | 20 |
| Cut | 20 |
| Total | 100 |

Pool Supply Score is calculated based on each stone's Max Supply. This item is not a bonus that automatically makes one stone more valuable than another. Instead, pools with lower Max Supply receive a lower base score, making it more difficult to reach high final tiers in those pools.

$$
\text{Pool Supply Score}
=
15 + 5 \times
\frac{\text{StoneMaxSupply} - \text{MinCollectionSupply}}
{\text{MaxCollectionSupply} - \text{MinCollectionSupply}}
$$

Reference values:

* MaxCollectionSupply = 220,000
* MinCollectionSupply = 110,000

Pool Supply Score is used as a fixed value between 15 and 20.

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

For example, Diamond has a Max Supply of 110,000 and therefore receives the lowest Pool Supply Score. Zircon has a Max Supply of 220,000 and receives the highest Pool Supply Score. As a result, obtaining Epic, Legendary, or Genesis in the Diamond Pool is more difficult. However, a high-grade Diamond Gem NFT satisfies both low supply and high grade, so it may form stronger collectible value in the market.

This structure is not intended to rank pools by a simple score. It reflects supply differences between pools in final tier difficulty. Lower-supply pools make high-tier outcomes harder, while higher-supply pools make them relatively easier.

## 31.2 Probability Rarity Index

While Rarity Score is a user-friendly comparison indicator, Probability Rarity Index is a mathematical rarity indicator based on the occurrence probability of each attribute.

The probability (P(g)) that the attribute combination of Gem NFT (`g`) occurs is defined as follows:

$$
P(g) = P_{\text{stone}} \times P_{\text{weight}} \times P_{\text{color}} \times P_{\text{clarity}} \times P_{\text{cut}}
$$

Based on this, the probability-based rarity indicator is calculated.

$$
\text{Probability Rarity Index} = -\log_{10}(P(g))
$$

This indicator shows how statistically rare a specific Gem NFT attribute combination is.

For example, the following combination is extremely rare.

* Diamond
* 100.00 CT or higher
* D Color
* FL Clarity
* 6 Star Cut

Such a combination receives a high Rarity Score and also has a very high Probability Rarity Index.

Rarity Score is used as the user-friendly basis for final tier calculation. The base tier ranges are:

| Final Tier | Rarity Score Range | Role |
| ---------- | ------------------ | ---- |
| Common | 0 ~ 34 | Most common gemstone group, basic collectibles and refinement material |
| Rare | 35 ~ 50 | Mid-tier collectibles that are rarer than ordinary mining results |
| Epic | 51 ~ 74 | High-tier range that users can perceive as a meaningful success |
| Legendary | 75 ~ 89 | Very rare, high-value collectible range |
| Genesis | 90 ~ 100 | Top-tier range reflecting extreme attribute combinations and the highest scores |

When Pool Supply Score 15~20 and the Weight, Color, Clarity, and Cut score tables are applied together, these ranges target an average expectation of about one Epic-or-higher result per 36 mined NFTs. Actual results vary depending on random attribute combinations and pool-specific supply adjustment.

The target can be expressed with the following expectation model. When `n` NFTs are mined from a specific pool `s`, the expected number of Epic-or-higher results is calculated by summing all attribute probabilities with the pool's Pool Supply Score.

$$
E_{\ge Epic}(n)
=
n \cdot
\sum_{s \in S}
\pi_s
\sum_{w \in W}
\sum_{c \in C}
\sum_{q \in Q}
\sum_{u \in U}
\mathbf{1}
\left[
Score_s + Score_w + Score_c + Score_q + Score_u \ge 51
\right]
P_s(w)P_s(c)P_s(q)P_s(u)
\approx
\frac{n}{36}
$$

Here, `S` is the set of stone pools, `π_s` is the participation share of each pool, and `W/C/Q/U` are the Weight, Color, Clarity, and Cut attribute sets. This formula is not intended to guarantee market price. It is a protocol design reference used to prevent the rarity distribution from becoming either too common or too closed.

By using Rarity Score and Probability Rarity Index together, CryptoStone provides both an intuitive score system for collectors and a data-based rarity system that can be verified mathematically.
