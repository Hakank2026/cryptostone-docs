# 10\_ハッシュパワー\_マイニングパワー\_Proof\_of\_Mining

ビットコインにおいて、採掘者はハッシュパワーを通じてブロックを生成する確率を得る。ハッシュパワーが高いほどブロックを発見する可能性は高まるが、ビットコイン全体の発行規則や難易度構造を恣意的に変更することはできない。つまり、ハッシュパワーはネットワーク規則を変える権限ではなく、定められた規則の中でより多くの採掘機会を得るための演算資源である。

CryptoStoneは、この概念をデジタル宝石採掘構造に合わせて抽象化する。CryptoStoneにおいてハッシュパワーに対応する概念はMining Powerであり、Mining Powerが時間の経過とともに蓄積された作業量がProof of Mining、PoMである。

| Bitcoin                     | CryptoStone              |
| --------------------------- | ------------------------ |
| Hash Power                  | Mining Power             |
| Proof of Work               | Proof of Mining、PoM      |
| ASIC / Mining Equipment     | Staked STONE             |
| Block Reward                | Gem NFT                  |
| Network Difficulty          | Pool Difficulty          |
| Halving Scarcity Multiplier |                          |
| BTC Issuance                | Gem NFT Minting          |
| Miner                       | STONE Staker / Gem Miner |

PoMは、別途転送または取引されるトークンではない。PoMは、ユーザーの採掘参加と時間経過をコントラクトが記録するオンチェーン作業量指標である。また、PoMはネットワーク合意アルゴリズムを意味しない。CryptoStoneにおけるPoMは、特定ストーンプールでユーザーがGem NFTをclaimできる条件に到達したかを判断するためのプロトコル内部値である。

ユーザー _i_ が特定ストーンプール _j_ にステーキングしたSTONE数量を _s_<sub>_i,j_</sub>、ロックアップ期間に応じた倍率を _L_<sub>_i_</sub> とすると、ユーザーのマイニングパワー _P_<sub>_i,j_</sub> は次のように定義される。

$$
P_{i,j} = s_{i,j} \times L_i
$$

ユーザーのPoM値は、時間の経過とともに次のように蓄積される。

$$
PoM_{i,j}(t + \Delta t) = PoM_{i,j}(t) + P_{i,j} \times \Delta t
$$

ここで、_PoM_<sub>_i,j_</sub>_(t)_ は、ユーザー _i_ がストーンプール _j_ において時点 _t_ までに蓄積したProof of Mining値である。

PoMはストーンプールごとに独立して蓄積される。たとえば、Diamond Poolで蓄積されたPoMはDiamond NFTのclaimにのみ使用でき、Ruby PoolやSapphire PoolのPoMに変換することはできない。この構造は、各ストーンプールの独立性、希少性、採掘難易度を保護する。

マイニングパワーが高いユーザーは、必要PoM閾値により早く到達できるが、宝石の希少度確率を恣意的に高めたり、特定等級の宝石を選択したりすることはできない。
