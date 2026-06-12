# 16\_base\_mining\_unit\_and\_small\_scale\_participation\_structure

The reference mining unit of CryptoStone is set as follows.

**Base Mining Unit = 100,000 STONE**

However, this is not the minimum participation amount. The Base Mining Unit is a reference unit used to calculate mining speed and difficulty.

CryptoStone adopts a PoM accumulation structure so that as many users as possible can participate in mining. Users can participate in mining pools with less than 100,000 STONE, and PoM accumulates in proportion to the staked amount and time.

A user can claim a Gem NFT when the accumulated PoM value becomes equal to or greater than the required PoM threshold ((R\_j)) of that pool.

$$
PoM_{i,j}(t) \ge R_j
$$

For example, assuming that both Pool Difficulty and Scarcity Multiplier are 1x in the initial condition of the Diamond Pool, the estimated mining time is as follows.

| Active Stake  | Estimated Time to Mine 1 Diamond NFT |
| ------------- | ------------------------------------ |
| 100,000 STONE | about 2.55 days                      |
| 10,000 STONE  | about 25.5 days                      |
| 5,000 STONE   | about 51 days                        |
| 1,000 STONE   | about 255 days                       |
| 100 STONE     | about 6.98 years                     |

This structure gives high-Mining Power users faster mining opportunities while also allowing small participants to accumulate PoM over the long term and claim Gem NFTs.

The author considers this structure very important for the expansion of the CryptoStone ecosystem. NFT scarcity should be maintained through total supply, attribute probabilities, and halving structure, while user participation should be expanded through low entry barriers and PoM accumulation.
