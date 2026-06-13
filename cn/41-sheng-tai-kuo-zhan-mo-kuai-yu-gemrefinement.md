# 41 生态扩展与精炼

CryptoStone 可以在不替代核心挖矿结构的前提下，通过 Marketplace、Arena、Gem Refinement 扩展 Gem NFT 的用途。

Marketplace 支持已挖出 Gem NFT 的价格发现与所有权转移。用户可以将自己挖出或精炼出的 Gem NFT 挂到公开市场，买家可以根据宝石类型、等级、Rarity Score、属性、tokenId、交易历史和媒体状态选择收藏对象。Marketplace 并不保证稀有度本身，它是基于公开属性与链上 provenance 形成市场价格的场所。

Arena 是扩展 Gem NFT 用途的游戏型模块。用户可以将持有的 Gem NFT 作为入场 seed 或参与资格，并通过基于 STONX 的 entry fee 参与 Duel、Battle、Arena 等桌台。Arena 为 Gem NFT 增加收藏以外的使用场景，但不直接改变挖矿概率或 NFT 等级。

Gem Refinement，即宝石精炼，是一种可选的后挖矿用途结构，让已挖出的 Gem NFT 可以再次被使用。Gem Refinement 不是无限追加 NFT 发行结构，而是将两个相同 `stoneType` 的 Gem NFT 合成为一个相同 `stoneType` 的 Refined Gem NFT，从而形成供应压缩机制。

| Input | Output | Supply Change |
| ----- | ------ | ------------- |
| 相同宝石的 2 个 Gem NFT | 相同宝石的 1 个 Refined Gem NFT | 总 NFT 供应减少 1 个 |

每执行一次精炼，两个父级 Gem NFT 会被销毁或以不可回收方式处理，并只生成一个新的 Refined Gem NFT。因此，流通中的 NFT 总量减少一个。

初期 Gem Refinement 最好只允许相同宝石之间的精炼。例如，两个 Garnet Gem NFT 可以精炼为一个 Refined Garnet Gem NFT，两个 Ruby Gem NFT 可以精炼为一个 Refined Ruby Gem NFT。跨宝石精炼可能会使各宝石供应量、稀缺性、减半机制和挖矿难度结构变得复杂，因此初期模型中排除更为合适。

Gem Refinement 可以生成具有以下特征的新 Gem NFT。

* 更高的 Rarity Score
* 精炼世代元数据
* 父级 tokenId 记录
* 附加视觉效果
* 更低的供应数量

不过，精炼不应被设计为无条件保证升级成功的结构。更合理的方式是包含基于概率的结果，使供应压缩、收藏张力和低等级 NFT 的用途能够共存。

精炼结果可以基于两个父级 Gem NFT 中较高的等级。

$$
T_{base} = \max(T_1, T_2)
$$

稀有度等级统一为 Common、Rare、Epic、Legendary、Genesis 五个等级。

| Tier Index | Tier |
| ---------- | ---- |
| 0 | Common |
| 1 | Rare |
| 2 | Epic |
| 3 | Legendary |
| 4 | Genesis |

精炼结果应当以保持基准等级的概率最高。降级概率应较低，即使发生升级，也应限制在最多 1~2 个等级。低等级 NFT 可以拥有相对更高的升级可能性，而高等级 NFT 应保持较低升级可能性，以保护高等级 Gem NFT 的稀缺性。

| Base Tier | Downgrade | Same Tier | +1 Tier | +2 Tier |
| --------- | --------: | --------: | ------: | ------: |
| Common | 无 | 68.0% | 27.0% | 5.0% |
| Rare | 1.0% | 76.0% | 20.0% | 3.0% |
| Epic | 1.5% | 88.0% | 10.0% | 0.5% |
| Legendary | 2.0% | 97.0% | 1.0% | 无 |
| Genesis | 限制 | 限制 | 限制 | 限制 |

Genesis 被视为最高收藏区间。初期模型中，限制其作为精炼材料更为稳妥。该结构既保留精炼期待感，又防止高等级 NFT 被过度生成。

通过精炼，低等级 Gem NFT 不会被简单抛弃，而可以作为供应压缩的原材料发挥作用。高等级 Gem NFT 继续保持稀缺，低等级 Gem NFT 则获得精炼材料用途。由此，CryptoStone 可以形成 Gem NFT 的内部循环结构。
