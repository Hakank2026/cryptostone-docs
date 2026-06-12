# 23\_adjustment\_of\_pool\_difficulty

If the number of participants increases and total Mining Power grows, gemstones may be mined too quickly. To prevent this, each pool adjusts difficulty based on total Mining Power.

If the total Mining Power of stone pool (j) is (P\_j), the Target Pool Power is (P\_j^\*), and pool difficulty is (D\_j), then it is calculated as follows:

$$
D_j = \max(1, P_j \div P_j^*)
$$

The reference value of CryptoStone is as follows:

$$
P_j^* = 40,000,000 \text{ Power}
$$

Examples are as follows.

| Target Pool Power | Total Pool Mining Power | Calculation                                 | Pool Difficulty |
| ----------------- | ----------------------: | ------------------------------------------- | --------------: |
| 40,000,000        |              20,000,000 | 20,000,000 ÷ 40,000,000 = 0.5 → max(1, 0.5) |            1.0x |
| 40,000,000        |              40,000,000 | 40,000,000 ÷ 40,000,000 = 1.0               |            1.0x |
| 40,000,000        |              80,000,000 | 80,000,000 ÷ 40,000,000 = 2.0               |            2.0x |
| 40,000,000        |             200,000,000 | 200,000,000 ÷ 40,000,000 = 5.0              |            5.0x |

The reason for applying the `max(1, ·)` structure is to prevent difficulty from falling below 1.0x even when total Mining Power is lower than the Target Pool Power. In other words, it prevents mining speed from becoming excessively faster than the reference speed even in early stages when participation is low.

Conversely, when total Mining Power exceeds the Target Pool Power, Pool Difficulty increases proportionally. For example, if the total Mining Power of a specific pool increases to 80,000,000 Power, Pool Difficulty becomes 2.0x. In this case, the time required for the same user to mine one NFT also approximately doubles.

In smart contract implementation, BPS can be used to avoid decimal operations.

$$
D_{j,\mathrm{BPS}} = \max(10,000, P_j \times 10,000 \div P_j^*)
$$

Here, 10,000 BPS = 1.0x.

This structure allows overall mining speed to adjust naturally as participation increases, and prevents the supply of each stone from being depleted too quickly.
