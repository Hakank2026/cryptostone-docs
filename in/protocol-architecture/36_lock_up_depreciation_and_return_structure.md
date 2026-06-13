# 36 Lock-up, depreciation और return structure

STONX mining participation lock-up और withdrawal rules से जुड़ सकता है।

Design considerations:

* longer lock-up higher Mining Power multiplier दे सकता है
* flexible participation lower multiplier दे सकती है
* withdrawal cooldown sudden liquidity shock को कम कर सकता है
* lock-up को yield promise की तरह प्रस्तुत नहीं करना चाहिए

यदि user unstake करता है, तो भविष्य की PoM accumulation रुक सकती है या घट सकती है। पहले से accumulated PoM pool-specific record के रूप में रह सकता है, यदि contract design इसे support करता है।

Lock-up structure का उद्देश्य protocol participation को संतुलित करना है, न कि interest-bearing deposit बनाना।