# 23 Pool difficulty adjustment

यदि किसी pool में कुल Mining Power बहुत बढ़ता है, तो Gem NFT बहुत तेजी से mined हो सकते हैं। इसे रोकने के लिए Pool Difficulty total Mining Power के अनुसार adjust हो सकती है।

Formula:

$$
D_j = max(1, P_j / P_j^*)
$$

जहाँ:

| Symbol | Meaning |
| --- | --- |
| `P_j` | pool `(j)` का total Mining Power |
| `P_j^*` | Target Pool Power |
| `D_j` | Pool Difficulty |

यदि target 40,000,000 Power है और actual power 80,000,000 Power तक पहुँचता है, तो:

$$
D_j = 80,000,000 / 40,000,000 = 2.0
$$

इस स्थिति में same user के लिए claim time लगभग दोगुना हो सकता है। यह mechanism pool को excessive speed से depleted होने से बचाता है।