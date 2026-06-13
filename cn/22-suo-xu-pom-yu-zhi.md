# 22 所需 PoM 阈值

挖出 1 个宝石所需的 PoM 阈值，由 Protocol Reference Power、各宝石基础挖矿周期、矿池难度和稀缺性倍率决定。

若宝石 (j) 的基础挖矿周期为 (T\_j)、Protocol Reference Power 为 (M\_{ref})、矿池难度为 (D\_j)、稀缺性倍率为 (S\_j)，则所需 PoM 阈值 (R\_j) 定义如下。

$$
R_j = M_{ref} \times T_j \times D_j \times S_j
$$

CryptoStone 的基准值如下。

* Base Mining Unit = 1,000 STONX
* Protocol Reference Power = 100,000 Power
* Target Pool Power = 40,000,000 Power

Base Mining Unit 是最小参与单位，而 Protocol Reference Power 是用于修正挖矿速度的基准算力。通过分离二者，CryptoStone 能够同时维持可参与的基础单位与长期供应控制。

例如，Garnet Pool 的基础挖矿周期为 170,000 秒，Pool Difficulty 与 Scarcity Multiplier 均为 1x 时:

$$
R_{Garnet} = 100,000 \times 170,000 \times 1 \times 1
$$

$$
R_{Garnet} = 17,000,000,000 \text{ PoM}
$$

当用户 (i) 的 Mining Power 为 (P\_{i,j}) 时，该用户 claim 宝石 (j) 的 NFT 1 个所需预计时间可表示为:

$$
E[T_{i,j}] = R_j \div P_{i,j}
$$

例如，用户以 Flexible 条件在 Garnet Pool 质押 6,000 STONX 时:

$$
E[T_{i,Garnet}] = 17,000,000,000 \div 6,000
$$

$$
= 2,833,333\text{秒}
$$

$$
\approx 32.8\text{天}
$$

也就是说，在初始条件下，质押 6,000 STONX 的用户大约一个月左右可以 claim 1 个 Garnet NFT。更少数量的用户会更慢累积 PoM，更多数量的用户会更快达到 claim 条件。
