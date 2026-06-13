# 20\_long\_term\_participation\_adjustment\_and\_flexible\_cooldown

A Lock Multiplier may be applied according to the staking period to reward long-term participants.

| Lock Type   | Lock Period | Mining Multiplier (L\_i) | Maturity Burn | Returned STONX | Cooldown |
| ----------- | ----------- | ------------------------ | ------------- | -------------- | -------- |
| Flexible    | None        | 1.00x                    | 0%            | 100%           | 7 days   |
| Short Lock  | 90 days     | 1.05x                    | 2.5%          | 97.5%          | None     |
| Medium Lock | 180 days    | 1.12x                    | 5%            | 95%            | None     |
| Long Lock   | 365 days    | 1.25x                    | 10%           | 90%            | None     |

Flexible Lock has no depreciation burn, but a 7-day cooldown period is applied after an unstake request to prevent short-term liquidity from entering and exiting too quickly.

Long-term lock-up is not mandatory. Users can choose the Flexible method without depreciation, and only choose longer lock-ups with depreciation if they want higher Mining Power.

This structure seeks the following balance.

| Choice       | Benefit                             | Cost                        |
| ------------ | ----------------------------------- | --------------------------- |
| Flexible     | Free participation, no depreciation | 7-day return waiting period |
| 90-day Lock  | Slightly higher Mining Power        | 2.5% depreciation           |
| 180-day Lock | Medium-level Mining Power           | 5% depreciation             |
| 365-day Lock | Highest Mining Power                | 10% depreciation            |

The lock-up multiplier is limited to a maximum of 1.25x. This is designed to provide reasonable compensation to long-term participants while preventing any specific large participant from gaining an excessively advantageous position.

Even during the lock-up period, a user can claim a Gem NFT once their PoM reaches the required threshold. In other words, lock-up limits the time at which STONX can be returned, but does not prohibit Gem NFT claims themselves.
