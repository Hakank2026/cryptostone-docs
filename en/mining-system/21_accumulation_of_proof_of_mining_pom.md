# 21\_accumulation\_of\_proof\_of\_mining\_pom

CryptoStone uses a Proof of Mining, or PoM, model that abstracts Bitcoin’s Proof-of-Work concept into a digital gemstone mining structure, rather than a simple point or credit system.

PoM refers to the mining work amount accumulated over time by a user staking STONX in a specific stone pool. PoM is not a separately transferable or tradable token, but an on-chain work amount indicator recorded by the contract based on the user’s mining participation and the passage of time.

The PoM value of user `(i)` for specific stone pool `(j)` accumulates over time as follows.

$$
PoM_{i,j}(t + \Delta t) = PoM_{i,j}(t) + P_{i,j} \times \Delta t
$$

For example, the Mining Power of a user who stakes 100,000 STONX into the Diamond Pool under Flexible conditions is as follows.

$$
P_{i,Diamond} = 100,000 \times 1.00 = 100,000
$$

If the user waits for 100,000 seconds, the accumulated PoM is as follows.

$$
PoM = 100,000 \times 100,000
$$

$$
PoM = 10,000,000,000
$$

When the user’s accumulated PoM reaches or exceeds the required PoM threshold of the corresponding pool, the user can claim a Gem NFT.

$$
PoM_{i,j}(t) \geq R_j
$$

When a Gem NFT is claimed, the required threshold `(R_j)` is deducted from the user’s PoM value in that pool.

$$
PoM_{i,j,new} = PoM_{i,j,old} - R_j
$$

This structure prevents excess PoM accumulated above the threshold from being unnecessarily lost. For example, if the required PoM threshold is 22,000,000,000 and the user holds 23,000,000,000 PoM when claiming a Gem NFT, then 1,000,000,000 PoM remains after the claim and is preserved for the next mining cycle.

PoM accumulates independently for each STONX pool. PoM accumulated in the Diamond Pool can only be used to claim Diamond NFTs, and cannot be converted into PoM for the Ruby Pool or Sapphire Pool. This structure protects the independence, scarcity, and mining difficulty of each STONX pool.

Even if a user unstakes STONX from a specific pool, the already accumulated PoM may remain recorded in that pool. However, after unstaking, the user’s Mining Power in that pool becomes 0, so no additional PoM accumulates. If the user stakes STONX again in the same pool, new PoM accumulates on top of the existing PoM.

If a user stakes additional STONX in the same pool, the existing PoM remains, and only the Mining Power after the additional staking increases. Conversely, if the staking amount is reduced, the existing PoM remains, but the future accumulation speed decreases.

PoM cannot be transferred externally or traded, and cannot be moved to another STONX pool. This is because PoM is not an asset itself, but a work amount indicator accumulated by a specific user through actual mining participation in a specific pool.
