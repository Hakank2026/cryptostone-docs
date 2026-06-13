# 37 开发结构

CryptoStone 采用以下结构。

* STONX Token
* CryptoStone Gem NFT
* 12 个 Mining Pool Contract
* Pool Factory

该结构用于实现不永久依赖特定链的数字宝石协议。初期阶段使用 EVM 兼容智能合约网络作为 Launch Network。

## 当前部署状态

下表总结当前测试网与协议文档基准下的部署状态。正式主网部署或合约升级时，地址和版本将在独立公开文档中更新。

| 项目 | 当前状态 | 备注 |
| ---- | -------- | ---- |
| Launch Network | Ethereum Sepolia | 测试网运行基准 |
| STONX Token | `0xBd10DA40Dec511c11100dd2927dDf8c53A5248Ed` | ERC-20 测试网部署 |
| GEMS NFT | `0x01CE9e3Ee0fb51B6b0cE1E5B3C72A5F981A50056` | V5.3 HTTPS metadata 结构 |
| Garnet Mining Pool | `0xd885D9865A1e7C9094EcD0982421bE9670Fabe16` | 当前 Live pool |
| Other 11 Mining Pools | 准备中 | 主网或顺序开放对象 |
| Refinery | `0xB7b55068163d6d8E4f8eD2e8B511e234520576DC` | 测试网精炼功能 |
| Marketplace | `0x673d64550c718A3770064ee3cDdC8b20093D0913` | 测试网 NFT 交易功能 |
| Metadata Model | HTTPS API + watcher finalization + IPFS media | 分离核心属性与媒体显示层 |
| Randomness Standard | 用户熵 + 多区块熵 + `prevrandao` | 新矿池与升级基准 |
| Mainnet Status | 准备中 | 安全审查、文档整理、流动性政策确定后推进 |

## 选择理由

| 选择 | 理由 |
| ---- | ---- |
| STONX Token | 提供统一挖矿资源与流动性结构 |
| CryptoStone Gem NFT | 表达每颗宝石的唯一性与属性 |
| 12 Mining Pools | 实现各宝石独立矿山结构 |
| Pool Factory | 使用同一经验证模板部署矿池 |
| Unified NFT Contract | 集中集合身份与交易数据 |
| Verifiable Randomness | 实现无运营方操纵的属性生成 |
| Finalize Mechanism | 防止核心规则被改变 |

第一，分离 STONX 与 Gem NFT 的角色。STONX 是用于 Mining Power 的代币，Gem NFT 是挖矿结果。

第二，保护宝石唯一性。每个 Gem NFT 拥有 tokenId 与属性组合，mint 后属性不会改变。

第三，保持各宝石之间的独立性。每个挖矿池都有独立供应量、挖矿周期和减半结构，适合将现实中的独立矿山概念数字化。

第四，NFT 集合保持统一。这将 CryptoStone 的品牌与市场数据集中在一起，使交易和稀有度排名能够统一管理。

第五，未来扩展性高。CryptoStone 可以从 EVM 兼容 Launch Network 起步，长期可扩展为独立 Appchain 或 CryptoStone Mainnet。

第六，降低中心化依赖。挖矿与 mint 由合约而不是服务器执行，任何人都可以验证条件。
