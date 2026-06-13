# 22 必要PoM閾値

宝石1個を採掘するために必要なPoM閾値は、Protocol Reference Power、ストーン別基本採掘周期、プール難易度、希少性倍率によって決定される。

ストーン (j) の基本採掘周期を (T\_j)、Protocol Reference Powerを (M\_{ref})、プール難易度を (D\_j)、希少性倍率を (S\_j) とすると、必要PoM閾値 (R\_j) は次のように定義される。

$$
R_j = M_{ref} \times T_j \times D_j \times S_j
$$

CryptoStoneの基準値は次のとおりである。

* Base Mining Unit = 1,000 STONX
* Protocol Reference Power = 100,000 Power
* Target Pool Power = 40,000,000 Power

Base Mining Unitは最小参加単位であり、Protocol Reference Powerは採掘速度を補正するための基準パワーである。この2つを分離することで、CryptoStoneは参加しやすい単位と長期供給制御を同時に維持する。

たとえばGarnet Poolの基本採掘周期が170,000秒であり、Pool DifficultyとScarcity Multiplierがともに1xである場合、次のようになる。

$$
R_{Garnet} = 100,000 \times 170,000 \times 1 \times 1
$$

$$
R_{Garnet} = 17,000,000,000 \text{ PoM}
$$

ユーザー (i) のマイニングパワーが (P\_{i,j}) のとき、当該ユーザーがストーン (j) のNFT 1個をclaimするまでに必要な予想時間は次のように表現できる。

$$
E[T_{i,j}] = R_j \div P_{i,j}
$$

たとえばユーザーがGarnet Poolに6,000 STONXをFlexible条件でステーキングした場合:

$$
E[T_{i,Garnet}] = 17,000,000,000 \div 6,000
$$

$$
= 2,833,333\text{秒}
$$

$$
\approx 32.8\text{日}
$$

つまり、初期条件で6,000 STONXをステーキングしたユーザーは、約1か月前後でGarnet NFT 1個をclaimできる。より少ない数量のユーザーはよりゆっくりPoMを蓄積し、より多い数量のユーザーはより早くclaim条件に到達する。
