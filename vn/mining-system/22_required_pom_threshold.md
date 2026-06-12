# 22\_required\_pom\_threshold

The PoM threshold required to mine one gemstone is determined by the Base Mining Unit, the base mining interval of each stone, pool difficulty, and scarcity multiplier.

If the base mining interval of stone (j) is (T\_j), the Base Mining Unit is (B), pool difficulty is (D\_j), and scarcity multiplier is (S\_j), then the required PoM threshold (R\_j) is defined as follows:

$$
R_j = B \times T_j \times D_j \times S_j
$$

The reference values of CryptoStone are as follows:

* (B = 100{,}000) STONE
* Target Pool Power = 40,000,000 Power

For example, if the base mining interval of the Diamond Pool is 220,000 seconds and both Pool Difficulty and Scarcity Multiplier are 1x, the calculation is as follows:

$$
R_{\text{Diamond}} = 100{,}000 \times 220{,}000 \times 1 \times 1
$$

$$
R_{\text{Diamond}} = 22{,}000{,}000{,}000 \text{ PoM}
$$

When the Mining Power of user (i) is (P\_{i,j}), the estimated time required for that user to claim one NFT of stone (j) can be expressed as follows:

$$
E[T_{i,j}] = R_j \div P_{i,j}
$$

For example, when a user stakes 100,000 STONE into the Diamond Pool under Flexible conditions:

$$
E[T_{i,\text{Diamond}}] = 22{,}000{,}000{,}000 \div 100{,}000
$$

$$
= 220{,}000 \text{ seconds}
$$

$$
\approx 2.55 \text{ days}
$$

In other words, under initial conditions, a user staking 100,000 STONE can claim approximately one Diamond NFT every 2.55 days.
