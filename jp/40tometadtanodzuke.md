# 40\_画像とメタデータの位置づけ

CryptoStoneは視覚的表現を否定しない。宝石NFTは、ユーザー体験と収集の利便性のために、画像、3Dモデル、視覚的カード形式で表現され得る。

しかし、画像はCryptoStoneの本質ではない。CryptoStoneの本質は次のデータにある。

| データ                    | 説明                |
| ---------------------- | ----------------- |
| stoneType              | 宝石種類              |
| weight                 | 重量                |
| colorGrade             | 色等級               |
| clarityGrade           | 透明度等級             |
| cutGrade               | カット等級             |
| rarityScore            | ユーザーフレンドリーな希少度スコア |
| probabilityRarityIndex | 確率ベース希少度指標        |
| minedAt                | 採掘時点              |
| minedFromPool          | 採掘されたマイニングプール     |
| tokenId                | NFT固有識別子          |
| generation             | オリジナルまたは精錬世代      |

したがって、画像サーバーが一時的に停止しても、CryptoStone NFTの核心属性はオンチェーンまたは検証可能なデータ構造に残っていなければならない。これは、既存NFTが外部画像や中央サーバーに過度に依存する問題を補完するための設計である。
