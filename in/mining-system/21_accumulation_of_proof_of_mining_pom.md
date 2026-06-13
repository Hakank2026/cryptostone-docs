# 21 Proof of Mining accumulation

PoM वह accumulated mining work है जो उपयोगकर्ता किसी specific stone pool में समय के साथ जमा करता है।

Formula:

$$
PoM_{i,j}(t) = P_{i,j} \times t
$$

यदि उपयोगकर्ता का Mining Power 6,000 है और वह 10,000 seconds wait करता है:

$$
PoM = 6,000 \times 10,000 = 60,000,000
$$

जब PoM required threshold से अधिक या बराबर होता है, तो user Gem NFT claim कर सकता है। Claim के समय required PoM घटाया जा सकता है और excess PoM अगले cycle के लिए रह सकता है।

PoM pool-specific है। Diamond Pool में जमा PoM Ruby Pool में उपयोग नहीं किया जा सकता। यह प्रत्येक stone की स्वतंत्र scarcity और mining difficulty की रक्षा करता है।