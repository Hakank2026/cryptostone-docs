# 26 Weight 属性

Weight 使用 CT，即克拉，作为所有宝石的共同单位。不过，每颗宝石的 Weight 值是随机生成的。

* Minimum Weight = 0.10 CT
* Maximum Weight = 200.00 CT
* Storage Unit = 0.01 CT

智能合约不会直接存储小数，而是以 0.01 CT 为单位存储整数值。

| 显示 Weight | 合约存储值 |
| ----------- | ---------- |
| 0.10 CT | 10 |
| 1.25 CT | 125 |
| 10.50 CT | 1050 |
| 200.00 CT | 20000 |

Weight 并非以相同概率生成。正如现实中更大克拉的宝石更稀有一样，在 CryptoStone 中，更高 Weight 会以更低概率生成。

| Weight Range | Probability | Score |
| ------------ | ----------- | ----: |
| 0.10 ~ 1.99 CT | 75.00% | 0 |
| 2.00 ~ 4.99 CT | 15.00% | 5 |
| 5.00 ~ 9.99 CT | 6.00% | 10 |
| 10.00 ~ 49.99 CT | 3.50% | 16 |
| 50.00 ~ 200.00 CT | 0.50% | 20 |

表中的 Score 并不是直接决定最终 Gem NFT 等级的值，而是用于计算 Rarity Score 与 Probability Rarity Index 的 Weight 属性分数。最终 Gem NFT 等级由 Pool Supply Score、Weight、Color、Clarity、Cut 综合计算，并统一为 Common、Rare、Epic、Legendary、Genesis 五个等级。
