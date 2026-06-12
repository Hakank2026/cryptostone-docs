# 16\_Base\_Mining\_Unit\_与小额参与结构

CryptoStone 的基准挖矿单位设定如下：

**Base Mining Unit = 100,000 STONE**

不过，这并不是最低参与数量。Base Mining Unit 是用于计算挖矿速度和难度的基准单位。

CryptoStone 采用 PoM 累积结构，使尽可能多的用户能够参与挖矿。用户即使持有少于 100,000 STONE 的数量，也可以参与挖矿池，并按质押数量和时间比例累积 PoM 值。

当用户累积的 PoM 值大于或等于该矿池所需 PoM 阈值 (R\_j) 时，即可 claim Gem NFT。

$$
PoM_{i,j}(t) \ge R_j
$$

例如，在 Diamond Pool 初始条件下，假设 Pool Difficulty 和 Scarcity Multiplier 均为 1x，则情况如下：

| Active Stake  | 挖掘 1 个 Diamond NFT 的预计时间 |
| ------------- | ------------------------ |
| 100,000 STONE | 约 2.55 天                 |
| 10,000 STONE  | 约 25.5 天                 |
| 5,000 STONE   | 约 51 天                   |
| 1,000 STONE   | 约 255 天                  |
| 100 STONE     | 约 6.98 年                 |

这一结构既为高挖矿算力用户提供更快的挖矿机会，也使小额参与者能够长期累积 PoM 并最终 claim Gem NFT。

本文作者认为，该结构对于 CryptoStone 的生态扩展非常重要。NFT 的稀缺性应通过总发行量、属性概率和减半结构来维持，而用户参与度则应通过低进入门槛和 PoM 累积结构来扩大。
