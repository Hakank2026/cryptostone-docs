# 22\_所需\_PoM\_阈值

挖掘 1 个宝石所需的 PoM 阈值，由 Base Mining Unit、各宝石基础挖矿周期、矿池难度和稀缺性倍率共同决定。

当宝石 `j` 的基础挖矿周期为 `Tj`，Base Mining Unit 为 `B`，矿池难度为 `Dj`，稀缺性倍率为 `Sj` 时，所需 PoM 阈值 `Rj` 定义如下：

$$
R_j = B \times T_j \times D_j \times S_j
$$

CryptoStone 的基准值如下：

* `B = 100,000 STONE`
* `Target Pool Power = 40,000,000 Power`

例如，Diamond Pool 的基础挖矿周期为 `220,000` 秒，且 Pool Difficulty 与 Scarcity Multiplier 均为 `1x` 时，计算如下：

$$
R_{Diamond} = 100,000 \times 220,000 \times 1 \times 1
$$

$$
R_{Diamond} = 22,000,000,000 \text{ PoM}
$$

当用户 `i` 的挖矿算力为 `Pi,j` 时，该用户 claim 1 个宝石 `j` NFT 所需的预计时间可以表示如下：

$$
E[T_{i,j}] = R_j \div P_{i,j}
$$

例如，用户以 Flexible 条件在 Diamond Pool 中质押 `100,000 STONE` 时：

$$
E[T_{i,Diamond}] = 22,000,000,000 \div 100,000
$$

$$
= 220,000 \text{ 秒}
$$

$$
\approx 2.55 \text{ 天}
$$

也就是说，在初始条件下，质押 `100,000 STONE` 的用户大约每 `2.55` 天可以 claim 1 个 Diamond NFT。
