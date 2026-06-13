# 25 供应耗尽结构

CryptoStone 的挖矿结构并不是简单的线性 mint 模型。每一种宝石都有独立的供应量、挖矿周期、矿池难度和稀缺性倍率，并且随着挖矿进度提高，挖矿速度会因 Scarcity Multiplier 上升而放缓。

若宝石池 (j) 的有效 Mining Power 为 (P\_{eff,j})，则可表示为:

$$
P_{eff,j} = \min(P_j, P_j^*)
$$

这意味着，当整体 Mining Power 低于 Target Pool Power 时，实际参与算力会影响挖矿速度；而当整体 Mining Power 超过 Target Pool Power 时，则通过难度上升限制有效挖矿速度。

宝石池 (j) 的单位时间预计挖矿量 (\lambda\_j) 可在概念上表示如下:

$$
\lambda_j = P_{eff,j} \div (M_{ref} \times T_j \times S_j)
$$

其中，(M\_{ref}) 是 Protocol Reference Power，(T\_j) 是该宝石的 Base Mining Interval，(S\_j) 是 Scarcity Multiplier。Base Mining Unit 是最小参与单位，长期挖矿速度由 Protocol Reference Power 与 Target Pool Power 修正。

某一种宝石达到挖矿进度 (q) 所需时间，可以用以下非线性模型表示:

$$
Time_j(q) = (N_j \times M_{ref} \times T_j \div P_{eff,j}) \times \int^q S_j(x)\, dx
$$

该公式表明，CryptoStone 的挖矿结构不是线性耗尽模型，而是随着宝石剩余供应量减少而逐步放缓的非线性挖矿模型。

因此，初期区间中 Gem NFT 会相对活跃地被挖出，但在 90% 之后的区间，Scarcity Multiplier 上升，剩余供应量的挖矿速度会明显放缓。
