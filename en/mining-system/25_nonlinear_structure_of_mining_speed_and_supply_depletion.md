# 25 Nonlinear Mining Speed and Supply Depletion

## Depletion

CryptoStone's mining structure is not a simple linear issuance model. Each stone has an independent supply, mining interval, pool difficulty, and scarcity multiplier, and as mining progress increases, mining speed slows due to the scarcity multiplier.

If the effective Mining Power of stone pool $(j)$ is $(P\_{eff,j})$, it can be expressed as follows:

$$
P_{eff,j} = \min(P_j, P_j^*)
$$

This means that when total Mining Power is below Target Pool Power, actual participating power affects mining speed, and when total Mining Power exceeds Target Pool Power, the effective mining speed is limited through difficulty increase.

The expected mining quantity per unit time of stone pool $(j)$, $(\lambda\_j)$, can conceptually be expressed as follows:

$$
\lambda_j = P_{eff,j} \div (M_{ref} \times T_j \times S_j)
$$

Here, $(M\_{ref})$ is Protocol Reference Power, $(T\_j)$ is the Base Mining Interval of the stone, and $(S\_j)$ is the Scarcity Multiplier. Base Mining Unit is the minimum participation unit, while long-term mining speed is calibrated by Protocol Reference Power and Target Pool Power.

The time required for a specific stone to reach mining progress $(q)$ can be expressed as the following nonlinear model:

$$
Time_j(q) = (N_j \times M_{ref} \times T_j \div P_{eff,j}) \times \int_0^q S_j(x)\,dx
$$

This formula shows that CryptoStone's mining structure is not a model that depletes linearly, but a nonlinear mining model in which the mining speed gradually slows as the remaining supply of the stone decreases.

Therefore, Gem NFTs may be mined relatively actively in the early stage, but after the 90% stage, the Scarcity Multiplier increases and the mining speed of the remaining supply slows significantly.
