# 36\_lock\_up\_depreciation\_and\_return\_structure

When a user chooses a lock-up period and deposits STONE into a mining pool, a portion of STONE is burned as depreciation at the time of unstaking after the lock-up expires, and the remaining STONE is returned.

| Lock Type   | Lock Period | Mining Multiplier | Maturity Burn | Returned STONE | Cooldown |
| ----------- | ----------- | ----------------- | ------------- | -------------- | -------- |
| Flexible    | None        | 1.00x             | 0%            | 100%           | 7 days   |
| Short Lock  | 90 days     | 1.05x             | 2.5%          | 97.5%          | None     |
| Medium Lock | 180 days    | 1.12x             | 5%            | 95%            | None     |
| Long Lock   | 365 days    | 1.25x             | 10%           | 90%            | None     |

If the amount of STONE staked by user _i_ is _s_<sub>_i_</sub>, and the depreciation rate according to the lock-up period is _δ_<sub>_i_</sub>, then the amount of STONE burned at maturity (_M_<sub>_i_</sub>) is defined as follows.

$$
M_i = s_i \times \delta_i
$$

The amount of STONE returned (_R_<sub>_i_</sub>) is as follows.

$$
R_i = s_i - M_i
$$

This structure provides higher Mining Power to long-term participants while also reflecting the cost of using mining resources. In other words, users can choose longer lock-up periods to gain higher mining speed, but must accept higher depreciation burns at the end of the lock-up.

Long-term lock-up is not mandatory. Users who do not want STONE burn burden can choose the Flexible method. Long-term lock-up is an optional structure for participants who want higher Mining Power, and depreciation is interpreted as the cost of using digital mining resources that comes with that choice.

The author believes this structure should be interpreted not simply as a penalty, but as “depreciation caused by the use of digital mining equipment.” Just as real mining equipment wears out over time, STONE in CryptoStone provides Mining Power while deposited in mining pools, and a portion is burned according to the usage period.
