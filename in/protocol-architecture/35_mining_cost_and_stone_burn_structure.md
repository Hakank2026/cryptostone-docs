# 35\_mining\_cost\_and\_stone\_burn\_structure

In CryptoStone, STONE is not merely a payment method, but a mining resource used to participate in digital gemstone mining. Just as mining equipment and energy are used in real-world mines and equipment depreciates over time, STONE deposited into mining pools in CryptoStone has a certain digital depreciation structure during the mining process.

The author views the STONE burn structure not as a mechanism to guarantee token price appreciation, but as a mechanism to express the resource consumption and scarcity structure required for digital gemstone mining.

STONE burns in CryptoStone may occur mainly in two cases.

| Burn Type     | Time of Occurrence                    | Purpose                                    |
| ------------- | ------------------------------------- | ------------------------------------------ |
| Claim Burn    | When claiming a Gem NFT               | Expression of mining cost and scarcity     |
| Maturity Burn | When unstaking after lock-up maturity | Expression of mining resource depreciation |

The burn amount $B\_{claim,j}$ that occurs when claiming a Gem NFT is calculated by the following formula:

$$
B_{claim,j} = \beta \times S_j
$$

Here, $\beta$ is the Base Claim Burn, and $S\_j$ is the Scarcity Multiplier of the corresponding stone.

The initial reference value is set as follows:

$$
\beta = 20 \text{ STONE}
$$

| Scarcity Multiplier | Claim Burn |
| ------------------- | ---------- |
| 1x                  | 20 STONE   |
| 2x                  | 40 STONE   |
| 4x                  | 80 STONE   |
| 8x                  | 160 STONE  |
| 16x                 | 320 STONE  |
| 32x                 | 640 STONE  |

The Base Claim Burn is a minimum consumption structure representing mining cost, not a mechanism designed to rapidly reduce total supply. Burned STONE is not paid to the operator or foundation, but permanently removed from circulation. Through this, STONE functions not merely as a deposited asset, but as a digital mining resource actually used and consumed within the CryptoStone ecosystem.
