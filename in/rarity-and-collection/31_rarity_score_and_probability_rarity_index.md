# 31 Rarity Score और Probability Rarity Index

Rarity Score विभिन्न attribute scores को मिलाकर Gem NFT की overall rarity को व्यक्त करता है।

Reference components:

| Component | Meaning |
| --- | --- |
| Pool Supply Score | stone type की fixed scarcity range |
| Weight Score | weight attribute score |
| Color Score | color attribute score |
| Clarity Score | clarity attribute score |
| Cut Score | cut attribute score |

Example:

$$
RarityScore = PoolSupplyScore + Weight + Color + Clarity + Cut
$$

Probability Rarity Index यह संकेत दे सकता है कि किसी combination का occurrence कितना दुर्लभ है। यह market price guarantee नहीं है, बल्कि rarity interpretation tool है।

Pool Supply Score को 15-20 range में रखा जा सकता है। इससे कम supply stone को identity मिलती है, लेकिन final tier पूरी तरह supply से तय नहीं होता।