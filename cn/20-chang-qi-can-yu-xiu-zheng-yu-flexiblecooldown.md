# 20\_长期参与修正与\_Flexible\_Cooldown

为了奖励长期参与者，可以根据质押期限适用 Lock Multiplier。

| Lock Type   | Lock Period | Mining Multiplier | Maturity Burn | Returned STONE | Cooldown |
| ----------- | ----------- | ----------------- | ------------- | -------------- | -------- |
| Flexible    | 无           | 1.00x             | 0%            | 100%           | 7 days   |
| Short Lock  | 90 天        | 1.05x             | 2.5%          | 97.5%          | 无        |
| Medium Lock | 180 天       | 1.12x             | 5%            | 95%            | 无        |
| Long Lock   | 365 天       | 1.25x             | 10%           | 90%            | 无        |

Flexible Lock 没有折旧销毁，但为了防止短期流动性过快进出，在 unstake 请求之后设置 7 天 cooldown 期。

长期锁仓不是强制条件，而是可选条件。用户可以选择无折旧的 Flexible 方式，只有希望获得更高 Mining Power 时，才选择伴随一定折旧销毁的长期锁仓。

该结构追求以下平衡。

| 选择         | 优点       | 成本      |
| ---------- | -------- | ------- |
| Flexible   | 自由参与，无折旧 | 7 天返还等待 |
| 90 天 Lock  | 略高的挖矿算力  | 2.5% 折旧 |
| 180 天 Lock | 中等水平挖矿算力 | 5% 折旧   |
| 365 天 Lock | 最高挖矿算力   | 10% 折旧  |

锁仓倍率最高限制为 1.25 倍。这是为了在合理奖励长期参与者的同时，防止特定大型参与者获得过度优势。

在锁仓期间，只要用户的 PoM 值达到所需阈值，也可以 claim Gem NFT。也就是说，锁仓限制的是 STONE 可返还的时间，而不是禁止 Gem NFT 的 claim。
