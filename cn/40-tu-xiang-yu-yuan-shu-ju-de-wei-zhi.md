# 40 元数据结构

CryptoStone Gem NFT 的本质并不是图像本身，而是表达宝石的属性数据。

| Attribute | Example |
| --------- | ------- |
| `stoneType` | Garnet, Ruby, Sapphire |
| `weight` | 3.42 CT |
| `color` | D, E, F, G 等 |
| `clarity` | FL, IF, VVS1 等 |
| `cut` | 1 Star ~ 6 Star |
| `rarity` | Common、Rare、Epic、Legendary、Genesis 之一 |
| `minedAt` | 挖矿区块或时间 |
| `pool` | Mining pool address |
| `generation` | 原始或精炼世代 |

CryptoStone 可以通过 HTTPS metadata API 提供 NFT 基础元数据。这样，用户在 mint 后即可在钱包或市场中快速看到名称、描述、属性、等级和 tokenId。

## 40.1 Metadata Trust Model

CryptoStone 的元数据结构将核心属性与展示层分离。宝石的本质属性由合约和公开可验证数据决定，HTTPS metadata API 将这些属性以钱包、市场和前端易于读取的 JSON 形式提供。

| 层级 | 作用 | 信任标准 |
| ---- | ---- | -------- |
| Smart Contract | 决定 mint、所有权、tokenId 与核心属性 | 链上验证 |
| HTTPS Metadata API | 以 JSON 提供 name、description、attributes、media URL | 公开响应与确定性属性映射 |
| Watcher Finalization | 生成图像/视频、上传 IPFS、更新元数据响应 | 公开日志与 tokenId 映射 |
| IPFS Media | 保存图像与视频文件 | 内容寻址媒体验证 |

图像和视频由 watcher finalization 流程后续生成、上传至 IPFS，并更新 metadata API 与 JSON 响应。该过程不需要用户进行额外钱包确认。用户需要在钱包中确认的核心交易，应限制在 claim 或 refinement 执行阶段。

因此，CryptoStone Gem NFT 可以同时保持技术可验证性与视觉表达。宝石并不是由图像本身定义的。图像是链上与元数据属性的视觉表达，而属性本身定义收藏价值。

即使 IPFS 上传或媒体生成延迟，Gem NFT 的核心属性也应先通过合约和 HTTPS metadata API 被确认。之后 watcher 填充 IPFS image/video data 后，NFT 市场和钱包 UI 可以显示更新后的媒体。

该设计是为了避免用户为了元数据最终化而反复进行额外钱包确认。同时，即使图像服务器或 API 暂时延迟，CryptoStone NFT 的核心属性也应保留在链上或公开可验证的数据结构中。
