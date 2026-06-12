# 26\_digitalization\_of\_the\_weight\_attribute

Weight uses CT, or carat, as the common unit for all stones. However, the weight value of each gemstone is randomly generated.

* Minimum Weight = 0.10 CT
* Maximum Weight = 200.00 CT
* Storage Unit = 0.01 CT

The smart contract does not store decimals directly. Instead, it stores values as integers in units of 0.01 CT.

| Displayed Weight | Contract Stored Value |
| ---------------- | --------------------- |
| 0.10 CT          | 10                    |
| 1.25 CT          | 125                   |
| 10.50 CT         | 1050                  |
| 200.00 CT        | 20000                 |

Weight is not generated with equal probability. Just as larger carat gemstones are rarer in the real world, larger weights are generated with lower probability in CryptoStone.

| Weight Range        | Probability | Rarity Tier | Score |
| ------------------- | ----------- | ----------- | ----- |
| 0.10 \~ 0.99 CT     | 50.00%      | Common      | 2     |
| 1.00 \~ 1.99 CT     | 25.00%      | Uncommon    | 5     |
| 2.00 \~ 4.99 CT     | 15.00%      | Rare        | 9     |
| 5.00 \~ 9.99 CT     | 6.00%       | Epic        | 13    |
| 10.00 \~ 19.99 CT   | 2.50%       | Legendary   | 17    |
| 20.00 \~ 49.99 CT   | 1.00%       | Mythic      | 20    |
| 50.00 \~ 99.99 CT   | 0.40%       | Ancient     | 23    |
| 100.00 \~ 200.00 CT | 0.10%       | Genesis     | 25    |
