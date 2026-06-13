# 10\_hash\_power\_mining\_power\_and\_proof\_of\_mining

In Bitcoin, miners obtain the probability of creating blocks through hash power. The higher the hash power, the higher the likelihood of discovering a block. However, hash power cannot arbitrarily change Bitcoin’s overall issuance rules or difficulty structure. In other words, hash power is not authority to change network rules, but a computational resource for obtaining more mining opportunities within fixed rules.

CryptoStone abstracts this concept into a digital gemstone mining structure. In CryptoStone, the concept corresponding to hash power is **Mining Power**, and the work amount accumulated by Mining Power over time is **Proof of Mining**, or **PoM**.

| Bitcoin                 | CryptoStone              |
| ----------------------- | ------------------------ |
| Hash Power              | Mining Power             |
| Proof of Work           | Proof of Mining, PoM     |
| ASIC / Mining Equipment | Staked STONX             |
| Block Reward            | Gem NFT                  |
| Network Difficulty      | Pool Difficulty          |
| Halving                 | Scarcity Multiplier      |
| BTC Issuance            | Gem NFT Issuance         |
| Miner                   | STONX Staker / Gem Miner |

PoM is not a separately transferable or tradable token. PoM is an on-chain work amount indicator recorded by the contract based on the user’s mining participation and the passage of time. PoM is also not a network consensus algorithm. In CryptoStone, PoM is an internal protocol value used to determine whether a user has reached the condition to claim a Gem NFT from a specific stone pool.

When user (i) stakes an amount of STONX ((s\_{i,j})) into STONX pool ((j)), and the lock-up multiplier is ((L\_i)), the user’s Mining Power ((P\_{i,j})) is defined as follows.

$$
P_{i,j} = s_{i,j} \times L_i
$$

The user’s PoM value accumulates over time as follows.

$$
PoM_{i,j}(t + \Delta t) = PoM_{i,j}(t) + P_{i,j} \times \Delta t
$$

Here, (PoM\_{i,j}(t)) is the Proof of Mining value accumulated by user ((i)) in STONX pool ((j)) up to time ((t)).

PoM accumulates independently for each STONX pool. For example, PoM accumulated in the Diamond Pool can only be used to claim a Diamond NFT, and cannot be converted into PoM for the Ruby Pool or Sapphire Pool. This structure protects the independence, scarcity, and mining difficulty of each STONX pool.

A user with higher Mining Power can reach the required PoM threshold more quickly, but cannot arbitrarily increase the probability of receiving a rarer gemstone or select a specific gemstone grade.
