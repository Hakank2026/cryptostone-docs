# 41 Ecosystem Expansion and Refinement

CryptoStone can expand Gem NFT utility through Marketplace, Arena, and Gem Refinement without replacing the core mining structure.

Marketplace supports price discovery and ownership transfer for mined Gem NFTs. Users can list Gem NFTs they have mined or refined, while buyers can select collectible targets by stone type, grade, Rarity Score, attributes, tokenId, trading history, and media status. Marketplace does not guarantee rarity itself; it is where market price forms based on disclosed attributes and on-chain provenance.

Arena is a game-style module that expands the utility of Gem NFTs. Users can use their Gem NFT as an entry seed or participation credential and join Duel, Battle, or Arena tables through STONX-based entry fees. Arena adds a use context beyond collection, but it does not directly change mining probability or NFT grade.

Gem Refinement is an optional post-mining utility structure that lets mined Gem NFTs be used again. It is not an unlimited additional issuance system. Instead, two Gem NFTs with the same `stoneType` are combined to create one Refined Gem NFT of the same `stoneType`, forming a supply compression mechanism.

The basic refinement structure is:

| Input | Output | Supply Change |
| ----- | ------ | ------------- |
| 2 Gem NFTs of the same stone | 1 Refined Gem NFT of the same stone | Total NFT supply decreases by 1 |

When one refinement is executed, the two parent Gem NFTs are burned or rendered unrecoverable, and only one new Refined Gem NFT is created. Therefore, total circulating NFT supply decreases by one.

Example:

* Garnet #102 + Garnet #481 -> Refined Garnet #9001
* Ruby #220 + Ruby #841 -> Refined Ruby #9102

In the initial model, Gem Refinement should preferably allow only same-stone refinement. For example, two Garnet Gem NFTs may become one Refined Garnet Gem NFT, and two Ruby Gem NFTs may become one Refined Ruby Gem NFT. Cross-stone refinement can make supply, scarcity, halving, and mining difficulty structures too complex, so it is appropriate to exclude it from the initial model.

Gem Refinement may create a new Gem NFT with:

* higher Rarity Score,
* refined generation metadata,
* parent tokenId records,
* additional visual effects,
* and a lower supply count.

However, refinement should not be designed to guarantee upgrade success unconditionally. It is preferable to include a probability-based result so that supply compression, collectible tension, and use cases for low-tier NFTs coexist.

The refinement result can be based on the higher tier of the two parent Gem NFTs.

$$
T_{base} = \max(T_1, T_2)
$$

Here, (T\_1) and (T\_2) are the tiers of the two parent Gem NFTs, and (T\_{base}) is the reference tier for determining the refinement result.

Rarity tiers are unified into five grades: Common, Rare, Epic, Legendary, and Genesis.

| Tier Index | Tier |
| ---------- | ---- |
| 0 | Common |
| 1 | Rare |
| 2 | Epic |
| 3 | Legendary |
| 4 | Genesis |

The refinement result should most often remain at the base tier. Downgrade probability should remain low, and upgrades, when they occur, should be limited to one or two tiers. Lower-tier NFTs may have relatively higher upgrade probability, while higher-tier NFTs should have lower upgrade probability to protect high-tier scarcity.

Example initial probability model:

| Base Tier | Downgrade | Same Tier | +1 Tier | +2 Tier |
| --------- | --------: | --------: | ------: | ------: |
| Common | None | 68.0% | 27.0% | 5.0% |
| Rare | 1.0% | 76.0% | 20.0% | 3.0% |
| Epic | 1.5% | 88.0% | 10.0% | 0.5% |
| Legendary | 2.0% | 97.0% | 1.0% | None |
| Genesis | Limited | Limited | Limited | Limited |

Genesis is treated as the top collectible tier. In the initial model, it is preferable to limit its use as refinement material. This structure preserves excitement around refinement while preventing excessive creation of high-grade NFTs.

If refinement between different parent tiers is allowed, the result probability can be adjusted based on the tier gap.

$$
\Delta T = |T_1 - T_2|
$$

| Tier Gap | Adjustment Coefficient | Meaning |
| -------- | ---------------------: | ------- |
| 0 | 100% | Same-tier refinement; base probability applies |
| 1 | 70% | Adjacent-tier refinement; upgrade probability slightly reduced |
| 2 | 40% | Large tier gap; upgrade probability significantly reduced |
| 3 or more | Limited | May be restricted in the initial model |

Through refinement, low-grade Gem NFTs are not simply abandoned. They can function as raw materials for supply compression. High-grade Gem NFTs remain scarce, while lower-grade NFTs gain utility as refinement inputs. This gives CryptoStone an internal circulation structure for Gem NFTs.
