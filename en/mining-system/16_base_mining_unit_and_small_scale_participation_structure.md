# 16 Base Mining Unit

CryptoStone sets the basic participation unit as follows.

**Base Mining Unit = 1,000 STONX**

The Base Mining Unit is the minimum reference unit required for a user to participate in a mining pool. It prevents meaningless fragmentation caused by excessively small deposits while still allowing ordinary users to begin accumulating Proof of Mining, or PoM, at an accessible scale. The Base Mining Unit is not a promise of short-term claim availability.

CryptoStone adopts a PoM accumulation model so that many users can participate in mining. Users can enter a mining pool from 1,000 STONX and accumulate PoM in proportion to both staked amount and time.

Users can claim a Gem NFT when their accumulated PoM reaches or exceeds the required threshold (R\_j) of the corresponding pool.

$$
PoM_{i,j}(t) \ge R_j
$$

Long-term supply speed is not determined by the Base Mining Unit alone. CryptoStone combines the 1,000 STONX participation unit with Target Pool Power, Protocol Reference Power, Pool Difficulty, and Scarcity Multiplier so that the total Gem NFT supply is mined gradually over a long period.

Under the initial Garnet Pool model, assuming both Pool Difficulty and Scarcity Multiplier are 1x and Protocol Reference Power is 100,000 Power, the expected claim interval can be interpreted as follows.

| Active Stake  | Estimated claim interval for 1 Garnet NFT |
| ------------- | ----------------------------------------- |
| 1,000 STONX   | About 197 days                            |
| 4,800 STONX   | About 41 days                             |
| 6,000 STONX   | About 32.8 days                           |
| 100,000 STONX | About 1.97 days                           |

This structure allows a 1,000 STONX participant to accumulate PoM, gives mid-sized participants a monthly mining experience, and gives high-mining-power users more frequent claim opportunities. Mining Power affects claim frequency only; it does not let users choose the grade or attributes of a Gem NFT.

The developer considers this structure important for CryptoStone's ecosystem expansion. NFT scarcity should be preserved through total supply, attribute probability, and halving structure, while user participation should be expanded through a lower entry threshold and a PoM accumulation model.
