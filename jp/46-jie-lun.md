# 46 結論

CryptoStoneは、デジタル宝石という概念をスマートコントラクト上に実装するプロトコルである。

CryptoStoneはSTONXをマイニング資源、Gem NFTを採掘結果として定義し、その2つをProof of Mining、PoMで接続する。ユーザーはSTONXをマイニングプールに投入し、時間の経過とともにMining PowerとPoMを蓄積し、必要閾値に到達した時点でGem NFTをclaimする。

## 核心構造

| 項目 | 構造 |
| ---- | ---- |
| Mining Resource | STONX |
| Initial Supply | 1,200,000,000 STONX |
| Mining Result | CryptoStone Gem NFT |
| Stone Types | 12 birthstone-based pools |
| Attribute Generation | Weight, Color, Clarity, Cut, Rarity |
| Metadata | HTTPS metadata API + watcher finalization + IPFS media |
| Rarity Standard | Rarity Score + Probability Rarity Index |

## プロトコル実行構造

| 段階 | 説明 |
| ---- | ---- |
| Participation | 1,000 STONXからマイニングプールに参加 |
| Mining Power | ステーキング数量、ロックアップ期間、プールパラメータから計算 |
| PoM | 時間に応じて蓄積される採掘作業量 |
| Claim | 必要PoM閾値到達後にGem NFTをclaim |
| Claim Burn | 2 STONX x Scarcity Multiplier |
| Maturity Burn | ロックアップ期間に応じた減価償却バーン |
| Randomness | ユーザーエントロピー、直近複数ブロックエントロピー、`prevrandao`、claim状態、コントラクト固有値 |
| Finalization | 核心属性はclaim時に確定し、メディアはwatcherが後続更新 |
| Open Verification | ソースコード、監査報告書、LP処理履歴、確率表検証 |

CryptoStoneの目的は、NFTを現実の宝石所有権と接続することではない。採掘難易度、希少性、個別属性、収集価値という宝石の構造を、デジタルネイティブな資産モデルとして再解釈することである。

本ホワイトペーパーは、CryptoStoneが偉大な発見や完全に新しい発明であると主張するものではない。これは発想の転換であり、新しい試みである。ただし、宝石の属性、希少性、収集性が市場で意味ある価値体系として認められるなら、CryptoStoneはデジタル宝石という新しいカテゴリへ発展し得る。

CryptoStoneは今後も、透明なコントラクト、検証可能なランダム性、公開供給データ、安全なメタデータ構造、そしてユーザーが理解し検証しやすいツールを通じて発展していくべきである。
