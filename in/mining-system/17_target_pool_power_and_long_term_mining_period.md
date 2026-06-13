# 17 Target Pool Power और दीर्घकालिक mining period

Target Pool Power वह reference level है जिसके आसपास किसी pool की mining speed संतुलित मानी जाती है।

Baseline:

| Parameter | Value |
| --- | ---: |
| Pool count | 12 |
| Target Pool Power per pool | 40,000,000 Power |
| Total Target Pool Power | 480,000,000 Power |

यदि total Mining Power target से अधिक हो जाता है, तो Pool Difficulty बढ़ सकती है। इससे mining speed अनियंत्रित रूप से तेज़ नहीं होती।

यह design long-term depletion को नियंत्रित करता है। लक्ष्य यह नहीं है कि सारी supply ठीक 10 वर्षों में mined हो जाए। प्रारंभिक वर्षों में अधिक activity हो सकती है, लेकिन अंतिम supply Scarcity Multiplier के कारण धीरे-धीरे mined होती है।