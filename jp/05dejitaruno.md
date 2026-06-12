# 05\_デジタル宝石資産の基本概念

CryptoStoneは、1つのSTONE Token、12種類の宝石マイニングプール、1つのGem NFTコントラクトで構成される。

| 構成要素                     | 役割                             |
| ------------------------ | ------------------------------ |
| STONE Token              | デジタル鉱山に参加するための単一マイニング資源        |
| 12 Gemstone Mining Pools | 各誕生石を採掘する独立したデジタル鉱山            |
| CryptoStone Gem NFT      | 採掘されたデジタル宝石を表現する固有NFT資産        |
| Mining Pool Contract     | ステーキング、マイニングパワー、難易度、claim条件を管理 |
| Gem NFT Contract         | 宝石NFTの属性、発行量、所有権を管理            |

STONEは宝石そのものではない。STONEはデジタル鉱山に参加するためのマイニングパワーの源泉である。ユーザーはSTONEを希望する宝石マイニングプールにステーキングすることでマイニングパワーを獲得し、時間の経過とともにPoMを蓄積する。

採掘結果物はCryptoStone Gem NFTである。Gem NFTは1つの統合NFTコントラクトから発行され、各NFTは自分がどのストーンであるか、どのような重量と等級を持つかをオンチェーン属性として保有する。

現実の宝石採掘構造を抽象化すると、次のようになる。

| 現実の宝石採掘      | CryptoStone                       |
| ------------ | --------------------------------- |
| 鉱山           | Gemstone Mining Pool              |
| 採掘装備およびエネルギー | STONE Token                       |
| 採掘作業量        | Proof of Mining、PoM               |
| 採掘結果物        | Gem NFT                           |
| 鉱山難易度        | Pool Difficulty                   |
| 埋蔵量減少        | Scarcity Multiplier               |
| 宝石鑑定         | On-chain Attribute & Rarity Score |
