# 13 Mining interval design

Base Mining Interval वह reference time है जिसके आधार पर किसी stone pool में एक Gem NFT claim condition तक पहुँच सकता है।

यह interval सभी stones के लिए समान नहीं होना चाहिए। अधिक दुर्लभ या कम supply stones के लिए interval लंबा हो सकता है, जबकि अधिक common stones के लिए interval छोटा हो सकता है।

Mining interval का उद्देश्य:

* initial mining speed को calibrate करना
* pool-specific scarcity को व्यक्त करना
* total supply depletion को नियंत्रित करना
* user participation को लंबे समय तक बनाए रखना

CryptoStone में long-term mining period का लक्ष्य यह है कि Gem NFT supply बहुत तेज़ी से समाप्त न हो। प्रारंभिक phase में mining अपेक्षाकृत सक्रिय हो सकती है, लेकिन supply progress बढ़ने पर Scarcity Multiplier के कारण mining धीरे होती जाती है।