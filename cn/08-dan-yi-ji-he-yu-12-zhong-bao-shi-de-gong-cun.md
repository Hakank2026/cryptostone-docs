# 08\_单一集合与\_12\_种宝石的共存

CryptoStone 不会将 12 种宝石分别拆分为不同的 NFT 集合。所有宝石都由一个 Gem NFT 合约发行。\
不过，每个 NFT 会通过 `stoneType` 属性来区分自己属于哪一种宝石。

| Token ID | Stone Type | Weight  | Color | Clarity | Cut    |
| -------- | ---------- | ------- | ----- | ------- | ------ |
| #10291   | Diamond    | 3.42 CT | D     | VVS1    | 6 Star |
| #58102   | Ruby       | 8.13 CT | G     | VS2     | 4 Star |
| #77410   | Sapphire   | 1.25 CT | E     | IF      | 5 Star |

这一结构具有以下优点。

| 优点       | 说明                             |
| -------- | ------------------------------ |
| 集合统一     | 保持 CryptoStone 作为一个集合的统一身份。    |
| 交易数据集中   | 防止在市场中集合价值和交易数据被分散。            |
| 稀有度管理更容易 | 可在一个 rarity ranking 体系中比较所有宝石。 |
| 保持各宝石独立性 | 通过 `stoneType` 属性表达每一种宝石的独立性。  |
| 可限制供应量   | NFT 合约内部可以验证各宝石的 `max supply`。 |

NFT 合约会分别管理各宝石的发行量。

```
maxSupplyByStone[Diamond] = 110,000
mintedByStone[Diamond] < maxSupplyByStone[Diamond]
```

因此，即使 `Diamond Pool` 发起发行请求，当 `Diamond` 的最大发行量已达到上限时，也无法继续发行 `Diamond NFT`。
