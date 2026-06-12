# 11\_Mining\_Pool\_Template\_与\_Factory\_结构

12 个 Mining Pool Contract 并不是拥有不同逻辑的独立开发物。所有矿池都基于同一个经过审计的 Mining Pool Template 部署。各矿池使用同样的核心逻辑，只是在以下参数上有所不同。

| 参数                   | 说明              |
| -------------------- | --------------- |
| `stoneType`          | 该矿池中被挖掘的宝石种类    |
| `maxSupply`          | 该宝石的最大发行量       |
| `baseMiningInterval` | 基础挖矿周期          |
| `targetPoolPower`    | 基准挖矿算力          |
| `scarcitySchedule`   | 各宝石的减半结构        |
| `poolAddress`        | NFT 合约允许的发行权限地址 |

为此，CryptoStone 可以采用 Pool Factory 结构。Pool Factory 基于同一个 Mining Pool Template 创建 12 个宝石池，并在部署后固定各矿池的核心参数。

| 优点    | 说明                          |
| ----- | --------------------------- |
| 代码一致性 | 12 个矿池使用相同逻辑。               |
| 审计效率  | 可围绕一个 Pool Template 进行安全审计。 |
| 风险降低  | 减少因每个矿池代码不同而产生的例外性漏洞风险。     |
| 参数透明性 | 各矿池差异仅由公开的固定参数产生。           |
| 扩展性   | 未来扩展新宝石池时可继续使用相同结构。         |

因此，CryptoStone 在保持“12 个独立矿山”这一经济结构的同时，在开发层面通过使用统一且可验证的智能合约模板来提高稳定性与透明度。
