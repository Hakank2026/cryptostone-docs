# 31\_rarity\_score\_and\_probability\_rarity\_index

CryptoStone uses two indicators to quantify the rarity of each gemstone.

| Indicator                | Purpose                                                                |
| ------------------------ | ---------------------------------------------------------------------- |
| Rarity Score             | A user-friendly 0\~100 score that users can intuitively understand     |
| Probability Rarity Index | A mathematical rarity indicator based on actual occurrence probability |

## 31.1 Rarity Score

**Rarity Score** is calculated as:

$$
\text{Rarity Score} = \text{Stone Scarcity Score} + \text{Weight Score} + \text{Color Score} + \text{Clarity Score} + \text{Cut Score}
$$

The score allocation is as follows.

| Attribute      | Max Score |
| -------------- | --------- |
| Stone Scarcity | 20        |
| Weight         | 25        |
| Color          | 15        |
| Clarity        | 20        |
| Cut            | 20        |
| Total          | 100       |

Stone Scarcity Score is calculated based on the total supply of each stone.

$$
\text{Stone Scarcity Score} = 20 \times \frac{\text{MaxCollectionSupply} - \text{StoneMaxSupply}}{\text{MaxCollectionSupply} - \text{MinCollectionSupply}}
$$

The reference values are as follows.

* MaxCollectionSupply = 220,000
* MinCollectionSupply = 110,000

For example, Diamond has a Max Supply of 110,000, so it has the highest Stone Scarcity Score. Zircon has a Max Supply of 220,000, so it has the lowest Stone Scarcity Score.

## 31.2 Probability Rarity Index

While Rarity Score is a user-friendly comparison indicator, Probability Rarity Index is a mathematical rarity indicator based on the occurrence probability of each attribute.

The probability (P(g)) that the attribute combination of Gem NFT ((g)) occurs is defined as follows:

$$
P(g) = P_{\text{stone}} \times P_{\text{weight}} \times P_{\text{color}} \times P_{\text{clarity}} \times P_{\text{cut}}
$$

Based on this, the probability-based rarity indicator is calculated.

$$
\text{Probability Rarity Index} = -\log_{10}(P(g))
$$

This indicator shows how statistically rare a specific Gem NFT’s combination is.

For example, the following combination is extremely rare.

* Diamond
* 100.00 CT or higher
* D Color
* FL Clarity
* 6 Star Cut

Such a combination receives a high Rarity Score and also has a very high Probability Rarity Index.

By using these two indicators together, CryptoStone provides both an intuitive score system that collectors can easily understand and a data-based rarity system that can be verified mathematically.
