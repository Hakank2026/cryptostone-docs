# 21\_Proof\_of\_Mining\_PoM\_的累积

CryptoStone 使用的是将比特币 Proof-of-Work 概念抽象为数字宝石挖矿结构的 Proof of Mining，即 PoM 模型，而不是简单的积分或信用点系统。

PoM 是用户在特定宝石池中质押 STONX，并随着时间推移所累积的挖矿工作量。PoM 并不是可以单独转移或交易的代币，而是合约根据用户挖矿参与和时间流逝记录的链上工作量指标。

用户 i 针对特定宝石池 j 的 PoM 值会随着时间按如下方式累积。

$$
PoM_{i,j}(t + \Delta t) = PoM_{i,j}(t) + P_{i,j} \times \Delta t
$$

例如，用户以 Flexible 条件在 Diamond Pool 中质押 100,000 STONX 时，其挖矿算力如下。

$$
P_{i,Diamond} = 100,000 \times 1.00 = 100,000
$$

若该用户等待 100,000 秒，则累积的 PoM 值如下。

$$
PoM = 100,000 \times 100,000
$$

$$
PoM = 10,000,000,000
$$

当用户累积的 PoM 值达到或超过对应矿池的所需 PoM 阈值时，即可 claim Gem NFT。

$$
PoM_{i,j}(t) \ge R_j
$$

当 Gem NFT 被 claim 后，用户在该矿池中的 PoM 值会扣除所需阈值 (R\_j)。

$$
PoM_{i,j,new} = PoM_{i,j,old} - R_j
$$

该结构避免用户超过阈值累积的 PoM 被不必要地清零。例如，当所需 PoM 阈值为 22,000,000,000，而用户在 claim 时持有 23,000,000,000 PoM，则 claim 之后剩余的 1,000,000,000 PoM 会被保留，用于下一次挖矿。

PoM 按各宝石池独立累积。在 Diamond Pool 中累积的 PoM 只能用于 claim Diamond NFT，不能转换为 Ruby Pool 或 Sapphire Pool 的 PoM。该结构保护了各宝石池的独立性、稀缺性和挖矿难度。

即使用户从特定矿池中 unstake STONX，已经累积的 PoM 也可以保留在该矿池记录中。不过，unstake 之后，用户在该矿池中的 Mining Power 变为 0，因此不会继续累积新的 PoM。若用户再次在同一矿池中质押 STONX，则可在既有 PoM 基础上继续累积新的 PoM。

当用户在同一矿池中追加质押 STONX 时，既有 PoM 会被保留，追加质押后的 Mining Power 会增加。相反，若减少质押数量，则既有 PoM 仍会保留，但未来累积速度会降低。

PoM 不能对外转让或交易，也不能转移至其他宝石池。这是因为 PoM 并不是资产本身，而是特定用户在特定矿池中通过实际挖矿参与所累积的工作量指标。
