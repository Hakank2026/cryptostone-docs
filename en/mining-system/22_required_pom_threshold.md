# 22 Required PoM Threshold

The PoM threshold required to mine one gemstone is determined by Protocol Reference Power, the base mining interval of each stone, pool difficulty, and scarcity multiplier.

If the base mining interval of stone (j) is (T\_j), Protocol Reference Power is (M\_{ref}), pool difficulty is (D\_j), and scarcity multiplier is (S\_j), then the required PoM threshold (R\_j) is defined as follows:

$$
R_j = M_{ref} \times T_j \times D_j \times S_j
$$

The reference values of CryptoStone are as follows:

* Base Mining Unit = 1,000 STONX
* Protocol Reference Power = 100,000 Power
* Target Pool Power = 40,000,000 Power

Base Mining Unit is the minimum participation unit, while Protocol Reference Power is the reference power used to calibrate mining speed. By separating these two values, CryptoStone can maintain both an accessible participation unit and long-term supply control.

For example, if the base mining interval of the Garnet Pool is 170,000 seconds and both Pool Difficulty and Scarcity Multiplier are 1x, the calculation is as follows:

$$
R_{\text{Garnet}} = 100{,}000 \times 170{,}000 \times 1 \times 1
$$

$$
R_{\text{Garnet}} = 17{,}000{,}000{,}000 \text{ PoM}
$$

When the Mining Power of user (i) is (P\_{i,j}), the estimated time required for that user to claim one NFT of stone (j) can be expressed as follows:

$$
E[T_{i,j}] = R_j \div P_{i,j}
$$

For example, when a user stakes 6,000 STONX into the Garnet Pool under Flexible conditions:

$$
E[T_{i,\text{Garnet}}] = 17{,}000{,}000{,}000 \div 6{,}000
$$

$$
= 2{,}833{,}333 \text{ seconds}
$$

$$
\approx 32.8 \text{ days}
$$

In other words, under initial conditions, a user staking 6,000 STONX can claim approximately one Garnet NFT in about one month. Users with smaller stakes accumulate PoM more slowly, while users with larger stakes can reach claim conditions more quickly.
