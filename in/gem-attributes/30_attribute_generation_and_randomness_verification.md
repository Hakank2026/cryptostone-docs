# 30 Attribute generation और randomness verification

Gem NFT attributes random-like process से generate होते हैं, लेकिन यह process single source पर निर्भर नहीं होना चाहिए।

CryptoStone randomness design में निम्न elements शामिल हो सकते हैं:

* user-provided entropy
* recent multi-block entropy
* Ethereum `prevrandao`
* claim state values
* contract-specific values

उद्देश्य यह है कि किसी एक random element पर निर्भरता कम हो। User या operator किसी single input से result को आसानी से control न कर सके।

Randomness design को public documentation, contract verification और probability table hash के माध्यम से समझाया जाना चाहिए। इससे users attribute generation logic को बेहतर तरीके से verify कर सकते हैं।