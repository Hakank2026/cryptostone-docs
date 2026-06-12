# 39\_安全应对与去中心化之间的平衡

CryptoStone 将 No Admin Mint 和 No Central Server 作为核心原则。不过，在初期开发与部署阶段，为了安全审计、测试和漏洞应对，可能需要有限的管理结构。

| 阶段         | 管理结构                                                 |
| ---------- | ---------------------------------------------------- |
| 测试网与审计阶段   | 可存在有限管理权限                                            |
| 正式部署前      | 参数验证与安全检查                                            |
| 正式上线后      | 移除核心发行、供应和概率更改权限                                     |
| finalize 后 | No Admin Mint、No Supply Change、No Probability Change |

如果存在紧急暂停功能，该功能只能作为防止安全事故的有限功能使用，而不得用于操纵发行结果或更改供应量。同时，紧急功能应通过时间锁或多签等公开可验证方式进行限制，不能成为运营方任意更改稀有度或发行量的手段。

CryptoStone 的主要合约由代币合约、Gem NFT 合约、Mining Pool Template、Pool Factory 和随机生成结构组成。这些合约在部署前后都最好经过安全审计，审计结果和主要漏洞应对记录也应公开。

应公开的核心验证要素如下。

| 验证项目                         | 说明              |
| ---------------------------- | --------------- |
| Contract Source Verification | 已部署合约源码公开与验证    |
| Audit Report                 | 主要合约与随机结构的审计报告  |
| Admin Function List          | 管理员函数是否存在及其移除计划 |
| Finalize Event               | 核心参数固定时间与事件记录   |
| LP Lock / Burn Proof         | 初始流动性相关 LP 处理记录 |
| Probability Table Hash       | 确认概率表与部署前公开值一致  |
| Metadata Freeze              | 发行后核心属性是否不可更改   |

该结构旨在在实务安全应对与去中心化资产性之间取得平衡。
