# 35 STONXバーン構造

CryptoStoneにおいて、STONXは単なる決済手段ではなく、デジタル宝石採掘に参加するためのマイニング資源である。現実の鉱山で採掘設備やエネルギーが使用され、時間とともに設備が摩耗するように、CryptoStoneでもマイニングプールに投入されたSTONXは採掘過程で一定のデジタル減価償却構造を持つ。

開発者は、STONXのバーン構造がトークン価格上昇を保証するための装置ではなく、デジタル宝石採掘に必要な資源消費と希少性構造を表現するための装置であると考える。

CryptoStoneの基本STONXバーン構造は、大きく2つの場合に発生し得る。

| バーン種類 | 発生時点 | 目的 |
| ---------- | -------- | ---- |
| Claim Burn | Gem NFTをclaimする時点 | 採掘コストと希少性の表現 |
| Maturity Burn | ロックアップ終了後のunstake時点 | マイニング資源の減価償却表現 |

上記2つはCryptoStoneの基本バーン構造である。ただし、エコシステムが拡張されるとSTONXバーンメカニズムは追加され得る。たとえばMarketplace手数料の一部バーン、Arenaまたはゲーム型モジュールのentry fee/settlementバーン、Gem Refinement実行費用バーンなどが追加バーン経路になり得る。これらの拡張バーンは、核心採掘規則を損なわない範囲で、別途コントラクトと公開ルールによって定義されるべきである。

Gem NFTをclaimする際に発生するバーン量 (B\_{claim,j}) は、次の式で計算される。

$$
B_{claim,j} = \beta \times S_j
$$

ここで、(\beta) はBase Claim Burnであり、(S\_j) は該当ストーンのScarcity Multiplierである。

Claim Burnはすべてのプールで固定2 STONXではない。基本値は2 STONXだが、各ストーンプールのScarcity Multiplierに応じて実際のバーン量が変わる。たとえば、あるプールが2x区間ならclaim時に4 STONX、4x区間なら8 STONXがバーンされる。したがって、Claim Burnはプール別の採掘進行度と難易度を反映する動的バーンコストである。

初期基準値は次のとおりである。

| Scarcity Multiplier | Claim Burn |
| ------------------- | ---------- |
| 1x | 2 STONX |
| 2x | 4 STONX |
| 4x | 8 STONX |
| 8x | 16 STONX |
| 16x | 32 STONX |
| 32x | 64 STONX |

Base Claim Burnは採掘コストを表現する最小消費構造であり、総供給量を急激に縮小させるための装置ではない。バーンされたSTONXは運営者や財団に支払われず、流通量から永久に除去される。これによりSTONXは単に預けられる資産ではなく、CryptoStoneエコシステム内で実際に使用され消費されるデジタルマイニング資源として機能する。
