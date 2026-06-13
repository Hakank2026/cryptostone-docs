# 25 Mining speed और supply depletion की nonlinear structure

CryptoStone की mining supply linear issuance model नहीं है। प्रत्येक stone की supply, interval, difficulty और scarcity multiplier अलग हो सकते हैं।

Effective mining speed को सरल रूप में इस तरह समझा जा सकता है:

$$
Speed_j \propto \frac{P_{eff,j}}{M_{ref} \times T_j \times S_j}
$$

यहाँ:

* `P_{eff,j}` pool की effective Mining Power है
* `M_{ref}` Protocol Reference Power है
* `T_j` Base Mining Interval है
* `S_j` Scarcity Multiplier है

जब supply progress कम होता है, mining अपेक्षाकृत तेज हो सकती है। लेकिन 90% के बाद Scarcity Multiplier बढ़ने से remaining supply बहुत धीरे mined हो सकती है।

इसलिए “10 वर्षों में 100% mining” को hard promise की तरह नहीं देखा जाना चाहिए। Design expectation यह है कि 8-9 वर्षों में बड़ी supply mined हो सकती है, लेकिन अंतिम हिस्से को पूरा होने में अधिक समय लग सकता है।