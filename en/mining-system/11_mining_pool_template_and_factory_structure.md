# 11\_mining\_pool\_template\_and\_factory\_structure

The 12 Mining Pool Contracts are not separate developments with different logic. All pools are deployed based on the same audited Mining Pool Template. Each pool uses the same core logic, while only the following parameters are set differently.

| Parameter          | Description                                             |
| ------------------ | ------------------------------------------------------- |
| stoneType          | The Stone Type mined from that pool                     |
| maxSupply          | The maximum issuance quantity of that STONX             |
| baseMiningInterval | Basic mining interval                                   |
| targetPoolPower    | Reference mining power                                  |
| scarcitySchedule   | Halving structure by STONX                              |
| poolAddress        | Authorized issuance address allowed by the NFT contract |

For this purpose, CryptoStone may use a Pool Factory structure. The Pool Factory creates the 12 STONX-specific pools based on the same Mining Pool Template, and fixes the core parameters of each pool after deployment.

| Advantage              | Description                                                                        |
| ---------------------- | ---------------------------------------------------------------------------------- |
| Code consistency       | All 12 pools use the same logic.                                                   |
| Audit efficiency       | Security audits can focus on one Pool Template.                                    |
| Risk reduction         | Reduces the possibility of exceptional bugs caused by different code in each pool. |
| Parameter transparency | Differences between pools arise only from publicly disclosed fixed values.         |
| Scalability            | The same structure can be used when adding new stone pools in the future.          |

Thus, CryptoStone maintains the economic structure of “12 independent mines” while increasing stability and transparency by using the same verifiable smart contract template in development.
