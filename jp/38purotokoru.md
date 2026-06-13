# 38 プロトコル固定原則

CryptoStoneがビットコインのような分散型資産性を志向するためには、デプロイ後に核心規則が恣意的に変更されてはならない。

| 固定項目 | 説明 |
| -------- | ---- |
| STONX総発行量 | 1,200,000,000 STONX |
| STONX配分構造 | DEX 50%、Direct Sale Pool 20%、Strategic / VC 10%、Listing / Liquidity Reserve 20% |
| ストーン別Max Supply | 各ストーン別最大NFT発行量 |
| ストーン別Base Mining Interval | 基本マイニング周期 |
| Target Pool Power | 初期基準値40,000,000 Power |
| Base Mining Unit | 1,000 STONX |
| Weight確率表 | 重量生成確率 |
| Color確率表 | 色等級生成確率 |
| Clarity確率表 | 透明度等級生成確率 |
| Cut確率表 | カット等級生成確率 |
| Scarcity Multiplier | 半減期ベース難易度倍率 |
| Claim Burn公式 | claim時バーン公式 |
| Mining Power公式 | ステーキングベースのマイニングパワー公式 |
| PoM公式 | Proof of Mining蓄積およびclaim条件 |
| Lock Multiplier | ロックアップ期間別マイニング倍率 |
| Maturity Burn公式 | ロックアップ終了時の減価償却バーン公式 |

初期設定が完了すると、プロトコルはfinalizeされなければならない。その後、運営者は恣意的に発行量を増やしたり、希少度確率を変更したり、特定ユーザーにNFTを手動発行したりできてはならない。

CryptoStoneの核心コントラクトはデプロイ後にソースコードが公開検証されるべきであり、トークン発行量、NFT供給量、確率表、マイニング公式、PoM閾値算定構造は、finalize後に変更できてはならない。

finalize前に必要な限定的管理機能が存在する場合、その機能の一覧、目的、削除時点、統制方式は明確に公開されなければならない。finalize後には、核心発行量、確率表、発行権限、PoM算定方式に関連する管理者権限が削除または非活性化されるべきである。

分散性は、単にブロックチェーン上にデプロイされたという事実だけで完成するものではない。分散性は、運営者が変更できない規則、誰でも検証可能なコード、誰でも参加可能な構造から形成される。
