# 22 Required PoM threshold

एक Gem NFT claim करने के लिए required PoM threshold निम्न elements से निर्धारित हो सकता है:

* Protocol Reference Power
* Base Mining Interval
* Pool Difficulty
* Scarcity Multiplier

Formula:

$$
R_j = M_{ref} \times T_j \times D_j \times S_j
$$

जहाँ:

| Symbol | Meaning |
| --- | --- |
| `R_j` | stone `(j)` का required PoM |
| `M_{ref}` | Protocol Reference Power |
| `T_j` | Base Mining Interval |
| `D_j` | Pool Difficulty |
| `S_j` | Scarcity Multiplier |

Baseline:

| Parameter | Value |
| --- | ---: |
| Base Mining Unit | 1,000 STONX |
| Protocol Reference Power | 100,000 Power |

यदि Garnet Pool का Base Mining Interval 170,000 seconds है और Difficulty तथा Scarcity Multiplier दोनों 1x हैं:

$$
R = 100,000 \times 170,000 = 17,000,000,000
$$

यदि user Mining Power 6,000 है:

$$
17,000,000,000 / 6,000 \approx 2,833,333 \; seconds
$$

यह लगभग 32.8 days है।