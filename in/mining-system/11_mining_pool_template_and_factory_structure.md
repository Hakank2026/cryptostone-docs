# 11 Mining Pool Template और Factory

12 Mining Pool Contracts अलग-अलग logic से नहीं बनाए जाने चाहिए। सभी pools एक समान audited Mining Pool Template से deploy किए जा सकते हैं।

प्रत्येक pool में केवल parameters अलग होते हैं:

| Parameter | Meaning |
| --- | --- |
| stoneType | उस pool का gemstone type |
| maxSupply | maximum Gem NFT supply |
| baseMiningInterval | reference mining time |
| targetPoolPower | target total Mining Power |
| burnMultiplier | claim burn calculation के लिए difficulty |

Pool Factory 12 stone-specific pools को एक ही template के आधार पर बना सकता है। इससे code consistency, audit efficiency और transparency बढ़ती है।

इस structure से CryptoStone “12 independent mines” की economic logic को बनाए रखते हुए smart contract stability को मजबूत कर सकता है।