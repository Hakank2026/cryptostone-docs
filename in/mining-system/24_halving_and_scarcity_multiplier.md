# 24 Halving और Scarcity Multiplier

CryptoStone में scarcity केवल fixed supply से नहीं आती। जैसे-जैसे किसी stone की mined supply बढ़ती है, remaining supply कम होती जाती है और mining कठिन हो सकती है।

Progress ratio:

$$
q_j = n_j / N_j
$$

जहाँ `(n_j)` mined supply और `(N_j)` max supply है।

Scarcity Multiplier supply progress के अनुसार बढ़ सकता है। सरल design में:

| Progress | Scarcity Multiplier |
| --- | ---: |
| 0% - 50% | 1x |
| 50% - 75% | 2x |
| 75% - 90% | 4x |
| 90%+ | higher |

इस structure से शुरुआती stage में mining active रहती है, लेकिन अंतिम supply धीरे-धीरे mined होती है। यह real-world mines की decreasing reserve logic को digital environment में व्यक्त करता है।