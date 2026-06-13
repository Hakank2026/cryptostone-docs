# 19\_挖矿算力的计算

在 CryptoStone 中，挖矿算力决定用户挖掘宝石的速度和机会。质押更多 STONX 的参与者会获得更多 Mining Power，并更频繁地达到 claim 条件。

当用户 i 的质押数量为 `s_{i,j}`，锁仓倍率为 `L_i`，用户挖矿算力为 `P_{i,j}` 时，计算如下：

$$
P_{i,j} = s_{i,j} \times L_i
$$

Mining Power 并不会直接提高宝石等级概率。Mining Power 只影响 PoM 的累积速度。

这与比特币挖矿结构相似。拥有更多挖矿设备的参与者会获得更多挖矿机会，但无法改变挖矿规则本身。在 CryptoStone 中也是如此。质押更多 STONX 的参与者可以更快累积 PoM，但无法任意提高获得更好宝石的概率。
