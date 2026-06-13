# 41 エコシステム拡張と精錬

CryptoStoneは、核心採掘構造を置き換えることなく、Marketplace、Arena、Gem Refinementを通じてGem NFTのユーティリティを拡張できる。

Marketplaceは、採掘されたGem NFTの価格発見と所有権移転を支援する。ユーザーは自身が採掘または精錬したGem NFTを公開市場に登録でき、購入者はストーン種類、等級、Rarity Score、属性、tokenId、取引履歴、メディア状態を基準に収集対象を選択できる。Marketplaceは希少度そのものを保証する装置ではなく、公開された属性とオンチェーンprovenanceを基に市場価格が形成される場所である。

Arenaは、Gem NFTのユーティリティを拡張するゲーム型モジュールである。ユーザーは保有するGem NFTを入場seedまたは参加資格として使用し、STONXベースのentry feeを通じてDuel、Battle、Arenaのテーブルに参加できる。ArenaはGem NFTに収集以外の使用文脈を与えるが、採掘確率やNFT等級を直接変更しない。

Gem Refinement、すなわち宝石精錬は、採掘されたGem NFTを再び活用できるよう設計された選択型の事後ユーティリティ構造である。Gem Refinementは無制限の追加NFT発行構造ではなく、同じ`stoneType`を持つGem NFT 2個を結合し、同じ`stoneType`のRefined Gem NFT 1個を生成する供給圧縮メカニズムである。

| Input | Output | Supply Change |
| ----- | ------ | ------------- |
| 同一ストーンのGem NFT 2個 | 同一ストーンのRefined Gem NFT 1個 | 総NFT供給量が1個減少 |

精錬が1回実行されるたびに、親Gem NFT 2個はバーンまたは回収不可能な方式で処理され、新しいRefined Gem NFT 1個だけが生成される。したがって、流通NFT総数は1個減少する。

初期Gem Refinementでは、同一ストーンベースの精錬のみを許可することが望ましい。たとえばGarnet Gem NFT 2個はRefined Garnet Gem NFT 1個に、Ruby Gem NFT 2個はRefined Ruby Gem NFT 1個に精錬できる。異なるストーン間の精錬は、ストーン別供給量、希少性、半減期、採掘難易度構造を複雑にするため、初期モデルでは除外するのが適切である。

精錬結果は次の要素を持つことができる。

* より高いRarity Score
* 精錬世代メタデータ
* 親tokenId記録
* 追加視覚効果
* 供給量の減少

ただし、精錬はアップグレード成功を無条件に保証する構造であってはならない。確率ベースの結果を含めることで、供給圧縮、収集上の緊張感、低等級NFTの利用先が共存できる。

精錬結果は、2つの親Gem NFTのうち高い等級を基準にできる。

$$
T_{base} = \max(T_1, T_2)
$$

希少度等級はCommon、Rare、Epic、Legendary、Genesisの5等級に統一する。

| Tier Index | Tier |
| ---------- | ---- |
| 0 | Common |
| 1 | Rare |
| 2 | Epic |
| 3 | Legendary |
| 4 | Genesis |

精錬結果は基準等級と同じ等級が出る確率を最も高く設定する。低下確率は低く置き、上昇結果が発生しても最大1~2段階の上昇に制限する。低い等級ほど相対的に上昇可能性を高め、高い等級ほど上昇可能性を低く設定することで、高等級Gem NFTの希少性を保護する。

| Base Tier | Downgrade | Same Tier | +1 Tier | +2 Tier |
| --------- | --------: | --------: | ------: | ------: |
| Common | なし | 68.0% | 27.0% | 5.0% |
| Rare | 1.0% | 76.0% | 20.0% | 3.0% |
| Epic | 1.5% | 88.0% | 10.0% | 0.5% |
| Legendary | 2.0% | 97.0% | 1.0% | なし |
| Genesis | 制限 | 制限 | 制限 | 制限 |

Genesisは最上位収集区間として扱われ、初期モデルでは精錬材料として使用することを制限する方が望ましい。この構造は精錬の期待感を維持しながら、高等級NFTが過度に生成されることを防ぐためである。

精錬により、低等級Gem NFTは単に放置されるのではなく、供給圧縮の原材料として機能できる。高等級Gem NFTは希少性を維持し、低等級Gem NFTにも精錬材料としての用途が生まれる。これによりCryptoStoneはGem NFTの内部循環構造を持つ。
