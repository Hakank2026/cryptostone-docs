# 08\_単一コレクションと12種類のストーンの共存

CryptoStoneは、12種類のストーンをそれぞれ別個のNFTコレクションとして分離しない。すべての宝石は、1つのGem NFTコントラクトから発行される。\
ただし、各NFTは `STONXType` 属性によって、自分がどの宝石であるかを区分する。

| Token ID | Stone Type | Weight  | Color | Clarity | Cut    |
| -------- | ---------- | ------- | ----- | ------- | ------ |
| #10291   | Diamond    | 3.42 CT | D     | VVS1    | 6 Star |
| #58102   | Ruby       | 8.13 CT | G     | VS2     | 4 Star |
| #77410   | Sapphire   | 1.25 CT | E     | IF      | 5 Star |

この構造には次の利点がある。

| 利点          | 説明                                    |
| ----------- | ------------------------------------- |
| コレクション統合    | CryptoStoneという単一コレクションのアイデンティティを維持する。 |
| 取引データの集中    | マーケットプレイスでコレクション価値と取引データが分散することを防ぐ。   |
| 希少度管理の容易性   | すべての宝石を1つのrarity ranking体系で比較できる。     |
| ストーン別個別性の維持 | `STONXType` 属性により各宝石の独立性を表現する。        |
| 供給量制限が可能    | NFTコントラクト内部でストーン別max supplyを検証できる。    |

NFTコントラクトは、ストーン別発行量を別途管理する。

```
maxSupplyBySTONX[Diamond] = 110,000
mintedBySTONX[Diamond] < maxSupplyBySTONX[Diamond]
```

したがって、Diamond Poolから発行リクエストが入った場合でも、Diamondの最大発行量に到達していれば、それ以上Diamond NFTは発行されない。
