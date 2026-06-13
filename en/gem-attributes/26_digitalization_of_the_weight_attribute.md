# 26 Weight Attribute

Weight uses CT, or carat, as the common unit for all stones. The weight value of each gemstone is generated randomly.

* Minimum Weight = 0.10 CT
* Maximum Weight = 200.00 CT
* Storage Unit = 0.01 CT

The smart contract does not store decimals directly. Instead, it stores values as integers in units of 0.01 CT.

| Displayed Weight | Contract Stored Value |
| ---------------- | --------------------- |
| 0.10 CT          | 10                    |
| 1.25 CT          | 125                   |
| 10.50 CT         | 1050                  |
| 200.00 CT        | 20000                 |

Weight is not generated with equal probability. As larger carat gemstones are rarer in the real world, larger weights are generated with lower probability in CryptoStone.

| Weight Range       | Probability | Score |
| ------------------ | ----------- | ----: |
| 0.10 ~ 1.99 CT     | 75.00%      |     0 |
| 2.00 ~ 4.99 CT     | 15.00%      |     5 |
| 5.00 ~ 9.99 CT     | 6.00%       |    10 |
| 10.00 ~ 49.99 CT   | 3.50%       |    16 |
| 50.00 ~ 200.00 CT  | 0.50%       |    20 |

The Score in the table is not a direct final Gem NFT tier. It is the Weight attribute score used to calculate Rarity Score and Probability Rarity Index. The final Gem NFT tier is determined by combining Pool Supply Score, Weight, Color, Clarity, and Cut into the five-tier system: Common, Rare, Epic, Legendary, and Genesis.
