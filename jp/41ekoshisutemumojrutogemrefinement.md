# 41\_エコシステム拡張モジュールとGem\_Refinement

CryptoStoneの核心プロトコルは、STONE、12個のストーン別マイニングプール、Proof of Mining、そしてGem NFTで構成される。\
ただし、CryptoStoneエコシステムは核心的な採掘構造だけに限定されず、将来的に別途のスマートコントラクトを追加したり、既存コントラクトと連携する拡張モジュールを通じて、さまざまな活用機能へ拡張できる。\
このような拡張機能には、Marketplace、Ranking System、Collection Quest、Gem Refinementなどが含まれ得る。

Gem Refinement、すなわち宝石精錬は、このようなエコシステム拡張モジュールの1つであり、採掘されたGem NFTを再び活用できるように設計された選択型の事後ユーティリティ構造である。\
Gem Refinementは追加的な無制限NFT発行構造ではなく、同一のstoneTypeを持つGem NFT 2個を結合して、同一のstoneTypeのRefined Gem NFT 1個を生成する供給圧縮メカニズムである。

```
Gem NFT 2個
+ 少量のSTONE使用またはバーン
→ Parent Gem NFTs Burned
→ Refined Gem NFT 1個 Minted
```

精錬が1回実行されるたびに、親Gem NFT 2個はバーンされるか回収不可能な方式で処理され、新しいRefined Gem NFT 1個のみが生成される。したがって、全体流通NFT数量は1個減少する。

```
2 Gem NFTs Burned → 1 Refined Gem NFT Minted
Net Circulating NFT Supply = -1
```

初期Gem Refinementは、同一ストーンベースの精錬のみを許可することが望ましい。たとえば、Diamond Gem NFT 2個はRefined Diamond Gem NFT 1個へ、Ruby Gem NFT 2個はRefined Ruby Gem NFT 1個へ精錬できる。\
異なるストーン間の精錬は、ストーン別供給量、希少性、半減期、採掘難易度構造を複雑にする可能性があるため、初期モデルでは除外することが適切である。

| 項目         | 原則                             |
| ---------- | ------------------------------ |
| 必要材料       | 同一stoneTypeのGem NFT 2個         |
| 追加費用       | 少量のSTONE使用またはバーン               |
| 親NFT処理     | 親Gem NFT 2個のバーンまたは回収不可能処理      |
| 結果物        | 同一stoneTypeのRefined Gem NFT 1個 |
| 世代情報       | Gen1またはRefined Generationとして記録 |
| 供給効果       | 全体流通NFT数量の減少                   |
| 発行権限       | Refining Contractに限定           |
| Admin Mint | なし                             |
| ランダム性      | 検証可能なランダム構造を使用                 |

Refined Gem NFTの基準等級は、2つの親Gem NFTのうち、より高い等級を基準として算定できる。

$$
T_{base} = \max(T_1, T_2)
$$

ここで、T1、T2 は2つの親Gem NFTの等級であり、Tbase は精錬結果算定の基準等級である。

等級体系は次のように単純化できる。

| Tier Level | Tier      |
| ---------- | --------- |
| 1          | Common    |
| 2          | Rare      |
| 3          | Epic      |
| 4          | Legendary |

精錬結果は、基準等級と同一等級が出る確率を最も高く設定する。1段階低い等級が出る確率は非常に低く設定し、上昇結果が発生する場合でも最大1〜2段階の上昇に制限する。\
また、低い等級ほど上昇可能性を相対的に高くし、高い等級ほど上昇可能性を低く設定することで、高等級Gem NFTの希少性を保護する。

0から9,999までのランダム値 U を使用するBPS方式の基本閾値例は次のとおりである。

* U ∈ \[0, 9,999]
* 10,000 BPS = 100%

| Base Tier | Tier -1 | Same Tier | +1 Tier | +2 Tier |
| --------- | ------- | --------- | ------- | ------- |
| Common    | なし      | 68.0%     | 27.0%   | 5.0%    |
| Rare      | 1.0%    | 76.0%     | 20.0%   | 3.0%    |
| Epic      | 1.5%    | 88.5%     | 10.0%   | なし      |
| Legendary | 2.0%    | 98.0%     | なし      | なし      |

上記構造において、CommonとRareは精錬を通じた上昇可能性が相対的に高いが、Epic以降は上昇確率が大きく低下する。\
Legendaryは精錬モデルの最上位等級として扱われ、追加上昇は許可しない。\
この構造は、精錬の期待感を維持しつつ、高等級NFTが過度に生成されることを防ぐためのものである。

2つの親Gem NFT間の等級差が大きい場合、上昇確率は追加で調整され得る。等級差 G は次のように定義する。

$$
G = |T_1 - T_2|
$$

| Tier Gap G | Upgrade Modifier | 処理原則              |
| ---------- | ---------------- | ----------------- |
| 0          | 100%             | 同一等級精錬。基本確率を適用    |
| 1          | 70%              | 隣接等級精錬。上昇確率を一部減少  |
| 2          | 35%              | 大きな等級差。上昇確率を大幅に減少 |
| 3以上        | 制限               | 初期モデルでは精錬制限可能     |

上昇確率は次のように調整できる。

$$
\text{Adjusted Upgrade Probability}
= \text{Base Upgrade Probability} \times \text{Upgrade Modifier}
$$

調整により減少した上昇確率は、同一等級維持確率に加算される。これにより、高等級Gem NFT 1個に低等級Gem NFTを繰り返し結合して上位等級生成を試みる行為を制限できる。

Refining Contractは、所有権検証、同一ストーン検証、等級差検証、STONE使用またはバーン、親NFTバーン、ランダム値リクエスト、Refined Gem NFT発行リクエストを実行する。\
Refined Gem NFTは、運営者の恣意的発行によって生成されてはならず、Refining Contractが事前定義された条件を検証した場合にのみ生成されなければならない。

Gem Refinementは、CryptoStoneの基本マイニング構造を代替する機能ではない。これは、採掘後のGem NFTの活用性、収集性、取引需要を拡張するための選択型モジュールである。\
将来的にCryptoStoneは、Gem Refinementをはじめとする多様な拡張モジュールを通じて、デジタル宝石エコシステムを段階的に拡張できる。
