# 22\_必要PoM閾値

宝石1個を採掘するために必要なPoM閾値は、Base Mining Unit、ストーン別基本マイニング周期、プール難易度、希少性倍率によって決定される。

ストーン `j` の基本マイニング周期を `T_j`、Base Mining Unit を `B`、プール難易度を `D_j`、希少性倍率を `S_j` とすると、必要PoM閾値 `R_j` は次のように定義される。

$$
R_j = B \times T_j \times D_j \times S_j
$$

CryptoStoneの基準値は次のとおりである。

* `B = 100,000 STONE`
* `Target Pool Power = 40,000,000 Power`

たとえばDiamond Poolの基本マイニング周期が220,000秒であり、Pool DifficultyとScarcity Multiplierがいずれも1xである場合、次のようになる。

$$
R_{Diamond} = 100,000 \times 220,000 \times 1 \times 1
$$

$$
R_{Diamond} = 22,000,000,000 \text{ PoM}
$$

ユーザー `i` のマイニングパワーが `P_{i,j}` のとき、当該ユーザーがストーン `j` のNFT1個をclaimするまでに必要な予想時間は、次のように表現できる。

$$
E[T_{i,j}] = R_j \div P_{i,j}
$$

たとえば、ユーザーがDiamond Poolに100,000 STONEをFlexible条件でステーキングした場合：

$$
E[T_{i,Diamond}] = 22,000,000,000 \div 100,000
$$

$$
= 220,000 \text{秒}
$$

$$
\approx 2.55 \text{日}
$$

つまり、初期条件において100,000 STONEをステーキングしたユーザーは、約2.55日ごとにDiamond NFT 1個をclaimできる。
