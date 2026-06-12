# 24\_halving\_and\_scarcity\_multiplier

The halving structure of CryptoStone is applied independently for each stone, not across the entire collection.

If the maximum supply of stone (j) is (N\_j), the quantity mined so far is (n\_j), and the mining progress ratio is (q\_j), then it is calculated as follows:

$$
q_j = n_j \div N_j
$$

For example, if Diamond’s maximum supply is 110,000 and 55,000 have been mined so far:

$$
q_{\text{Diamond}} = 55,000 \div 110,000 = 0.5
$$

This means that the Diamond Pool has reached the 50% mining stage.

The scarcity multiplier (S\_j) of each stone increases according to the mining progress ratio (q\_j).

| Mined Supply Ratio | Remaining Supply | Scarcity Multiplier |
| ------------------ | ---------------- | ------------------- |
| 0% \~ 50%          | 100% \~ 50%      | 1x                  |
| 50% \~ 75%         | 50% \~ 25%       | 2x                  |
| 75% \~ 87.5%       | 25% \~ 12.5%     | 4x                  |
| 87.5% \~ 93.75%    | 12.5% \~ 6.25%   | 8x                  |
| 93.75% \~ 96.875%  | 6.25% \~ 3.125%  | 16x                 |
| 96.875% or more    | 3.125% or less   | 32x                 |

This can be generalized as follows:

$$
S_j(q_j) = 2^{\min\left(5, \lfloor \log_2 \left( 1 \div (1 - q_j) \right) \rfloor \right)}
$$

However, when (q\_j) corresponds to the initial range, (S\_j(q\_j)) remains at a minimum of 1x. In actual smart contract implementation, rather than calculating the formula directly, it may be implemented based on a pre-disclosed range table.

This formula expresses a structure in which mining difficulty increases geometrically as the remaining supply of each stone decreases. This brings the real-world structure of mining costs and difficulty increasing as mine reserves decrease into the digital environment.
