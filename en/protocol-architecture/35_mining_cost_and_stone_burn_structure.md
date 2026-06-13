# 35 STONX Burn Structure

In CryptoStone, STONX is not merely a payment method. It is a mining resource used to participate in digital gemstone mining. Just as real-world mining equipment and energy are consumed and equipment depreciates over time, STONX deposited into CryptoStone mining pools has a digital depreciation structure during the mining process.

The developer views the STONX burn structure not as a mechanism to guarantee token price appreciation, but as a mechanism to express the resource consumption and scarcity structure required for digital gemstone mining.

CryptoStone's base STONX burn structure may occur in two main cases.

| Burn Type | Time of Occurrence | Purpose |
| --------- | ------------------ | ------- |
| Claim Burn | When claiming a Gem NFT | Expression of mining cost and scarcity |
| Maturity Burn | When unstaking after lock-up maturity | Expression of mining resource depreciation |

These two cases form the base burn structure of CryptoStone. As the ecosystem expands, additional STONX burn mechanisms may be introduced. Examples include partial burns from Marketplace fees, entry fee or settlement burns in Arena or other game modules, and execution-cost burns in Gem Refinement. Any expanded burn mechanism should be defined through separate contracts and public rules without damaging the core mining rules.

The burn amount (B\_{claim,j}) that occurs when claiming a Gem NFT is calculated by the following formula:

$$
B_{claim,j} = \beta \times S_j
$$

Here, (\beta) is the Base Claim Burn, and (S\_j) is the Scarcity Multiplier of the corresponding stone.

Claim Burn is not a fixed 2 STONX for every pool. The base value is 2 STONX, but the actual burn amount changes according to each stone pool's Scarcity Multiplier. For example, a pool in the 2x zone burns 4 STONX per claim, while a pool in the 4x zone burns 8 STONX. Therefore, Claim Burn is a dynamic burn cost that reflects each pool's mining progress and difficulty.

The initial reference values are:

| Scarcity Multiplier | Claim Burn |
| ------------------- | ---------- |
| 1x                  | 2 STONX    |
| 2x                  | 4 STONX    |
| 4x                  | 8 STONX    |
| 8x                  | 16 STONX   |
| 16x                 | 32 STONX   |
| 32x                 | 64 STONX   |

Base Claim Burn represents the minimum consumption structure of mining cost. It is not designed to rapidly reduce total supply. Burned STONX is not paid to an operator or foundation; it is permanently removed from circulation. Through this, STONX functions not merely as a deposited asset, but as a digital mining resource that is actually used and consumed within the CryptoStone ecosystem.
