# 41\_ecosystem\_expansion\_modules\_and\_gem\_refinement

The core protocol of CryptoStone consists of STONE, 12 stone-specific mining pools, Proof of Mining, and Gem NFTs. However, the CryptoStone ecosystem is not limited to the core mining structure. In the future, it can expand into various utility functions through additional smart contracts or expansion modules connected to existing contracts. These expansion functions may include Marketplace, Ranking System, Collection Quest, and Gem Refinement.

Gem Refinement is one of these ecosystem expansion modules, designed as an optional post-mining utility structure that allows mined Gem NFTs to be used again. Gem Refinement is not an unlimited additional NFT issuance structure, but a supply compression mechanism in which two Gem NFTs with the same stoneType are combined to create one Refined Gem NFT of the same stoneType.

```
2 Gem NFTs
+ small STONE use or burn
-> Parent Gem NFTs Burned
-> 1 Refined Gem NFT Issued
```

Each time a refinement is executed, the two parent Gem NFTs are burned or made permanently unrecoverable, and only one new Refined Gem NFT is issued. Therefore, the total circulating NFT supply decreases by one.

```
2 Gem NFTs Burned -> 1 Refined Gem NFT Issued
Net Circulating NFT Supply = -1
```

In the initial Gem Refinement model, it is desirable to allow only same-stone refinement. For example, two Diamond Gem NFTs can be refined into one Refined Diamond Gem NFT, and two Ruby Gem NFTs can be refined into one Refined Ruby Gem NFT. Cross-stone refinement can make the stone-specific supply, scarcity, halving, and mining difficulty structures complicated, so it is appropriate to exclude it from the initial model.

| Item                | Principle                                 |
| ------------------- | ----------------------------------------- |
| Required materials  | 2 Gem NFTs with the same stoneType        |
| Additional cost     | Small STONE use or burn                   |
| Parent NFT handling | Burned or made permanently unrecoverable  |
| Result              | 1 Refined Gem NFT with the same stoneType |
| Generation info     | Recorded as Gen1 or Refined Generation    |
| Supply effect       | Decrease in total circulating NFT supply  |
| Issuance authority  | Limited to the Refining Contract          |
| Admin Mint          | None                                      |
| Randomness          | Uses a verifiable randomness structure    |

The base tier of a Refined Gem NFT can be calculated based on the higher tier among the two parent Gem NFTs.

$$T_{base} = \max(T_1, T_2)$$

Here, (T\_1) and (T\_2) are the tiers of the two parent Gem NFTs, and (T\_{base}) is the base tier used to determine the refinement result.

The tier structure can be simplified as follows.

| Tier Level | Tier      |
| ---------- | --------- |
| 1          | Common    |
| 2          | Rare      |
| 3          | Epic      |
| 4          | Legendary |

The refinement result is designed so that the probability of receiving the same tier as the base tier is the highest. The probability of dropping by one tier is kept very low. Even if an upgrade occurs, it is limited to a maximum of 1 to 2 tiers. Also, lower tiers have relatively higher upgrade possibilities, while higher tiers have lower upgrade possibilities, protecting the scarcity of high-grade Gem NFTs.

An example of the basic threshold using a BPS-style random value (U) from 0 to 9,999 is as follows.

$$U \in [0, 9,999]$$

10,000 BPS = 100%

| Base Tier | -1 Tier | Same Tier | +1 Tier | +2 Tier |
| --------- | ------- | --------- | ------- | ------- |
| Common    | None    | 68.0%     | 27.0%   | 5.0%    |
| Rare      | 1.0%    | 76.0%     | 20.0%   | 3.0%    |
| Epic      | 1.5%    | 88.5%     | 10.0%   | None    |
| Legendary | 2.0%    | 98.0%     | None    | None    |

In this structure, Common and Rare have relatively higher upgrade possibilities through refinement, while upgrade probabilities decrease significantly from Epic onward. Legendary is treated as the highest tier in the refinement model, and no further upgrade is allowed. This structure maintains the excitement of refinement while preventing excessive creation of high-grade NFTs.

When the tier gap between the two parent Gem NFTs is large, the upgrade probability can be additionally adjusted. The tier gap (G) is defined as follows.

$$G = |T_1 - T_2|$$

| Tier Gap (G) | Upgrade Modifier | Processing Principle                                            |
| ------------ | ---------------- | --------------------------------------------------------------- |
| 0            | 100%             | Same-tier refinement. Basic probability applied                 |
| 1            | 70%              | Adjacent-tier refinement. Upgrade probability partially reduced |
| 2            | 35%              | Large tier gap. Upgrade probability greatly reduced             |
| 3 or more    | Restricted       | Refinement may be restricted in the initial model               |

The upgrade probability can be adjusted as follows.

$$\text{Adjusted Upgrade Probability} = \text{Base Upgrade Probability} \times \text{Upgrade Modifier}$$

The upgrade probability reduced by the adjustment is added to the probability of remaining at the same tier. This limits attempts to repeatedly combine one high-tier Gem NFT with low-tier Gem NFTs to create higher-tier results.

The Refining Contract performs ownership verification, same-stone verification, tier gap verification, STONE use or burn, parent NFT burn, randomness request, and Refined Gem NFT issuance request. A Refined Gem NFT must not be created by arbitrary operator issuance. It should only be created when the Refining Contract verifies the predefined conditions.

Gem Refinement does not replace the basic mining structure of CryptoStone. It is an optional module designed to expand the utility, collectibility, and trading demand of Gem NFTs after mining. In the future, CryptoStone may gradually expand the digital gemstone ecosystem through Gem Refinement and other expansion modules.
