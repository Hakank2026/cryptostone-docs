# 10 Hash Power, Mining Power और Proof of Mining

Bitcoin में hash power network security और mining probability से जुड़ा है। CryptoStone इस अवधारणा को digital gemstone mining में abstract करता है।

CryptoStone में hash power के समकक्ष concept को **Mining Power** कहा जाता है। Mining Power समय के साथ जो work accumulate करता है, उसे **Proof of Mining**, या **PoM**, कहा जाता है।

जब उपयोगकर्ता `(i)` stone pool `(j)` में STONX stake करता है, तो उसकी Mining Power इस प्रकार व्यक्त की जा सकती है:

$$
P_{i,j} = s_{i,j} \times L_i
$$

यहाँ `(s_{i,j})` stake amount है और `(L_i)` lock-up multiplier है।

PoM समय के साथ accumulate होता है:

$$
PoM_{i,j}(t) = P_{i,j} \times t
$$

PoM transferable token नहीं है। यह internal protocol indicator है, जो दिखाता है कि उपयोगकर्ता ने किसी specific stone pool में कितना mining work जमा किया है।