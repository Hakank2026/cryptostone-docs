# 19 Mining Power की गणना

Mining Power उपयोगकर्ता की STONX participation और lock-up condition से निकाला जाता है।

सरल रूप:

$$
P_{i,j} = s_{i,j} \times L_i
$$

जहाँ:

| Symbol | Meaning |
| --- | --- |
| `P_{i,j}` | user `(i)` का pool `(j)` में Mining Power |
| `s_{i,j}` | pool में stake किया गया STONX |
| `L_i` | lock-up multiplier |

उदाहरण:

यदि उपयोगकर्ता 6,000 STONX stake करता है और multiplier 1.0 है:

$$
P = 6,000 \times 1.0 = 6,000
$$

यदि lock-up multiplier अधिक है, तो Mining Power बढ़ सकता है। फिर भी उच्च Mining Power का अर्थ बेहतर grade की guarantee नहीं है। यह केवल claim threshold तक पहुँचने की speed को प्रभावित करता है।