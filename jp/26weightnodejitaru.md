# 26 Weight属性

Weightは、すべてのストーンに共通してCT、すなわちカラットを単位として使用する。ただし、各宝石のWeight値はランダムに生成される。

* Minimum Weight = 0.10 CT
* Maximum Weight = 200.00 CT
* Storage Unit = 0.01 CT

スマートコントラクトは小数を直接保存しない。代わりに0.01 CT単位の整数として値を保存する。

| 表示Weight | コントラクト保存値 |
| ---------- | ------------------ |
| 0.10 CT | 10 |
| 1.25 CT | 125 |
| 10.50 CT | 1050 |
| 200.00 CT | 20000 |

Weightは均等確率で生成されない。現実の宝石で大きなカラットが希少であるように、CryptoStoneでも大きなWeightほど低い確率で生成される。

| Weight Range | Probability | Score |
| ------------ | ----------- | ----: |
| 0.10 ~ 1.99 CT | 75.00% | 0 |
| 2.00 ~ 4.99 CT | 15.00% | 5 |
| 5.00 ~ 9.99 CT | 6.00% | 10 |
| 10.00 ~ 49.99 CT | 3.50% | 16 |
| 50.00 ~ 200.00 CT | 0.50% | 20 |

この表のScoreは、最終Gem NFT等級を直接確定する値ではない。Rarity ScoreとProbability Rarity Indexを計算するためのWeight属性スコアである。最終Gem NFT等級は、Pool Supply Score、Weight、Color、Clarity、Cutを総合してCommon、Rare、Epic、Legendary、Genesisの5等級で算定される。
