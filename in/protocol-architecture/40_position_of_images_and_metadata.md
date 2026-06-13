# 40 Images और metadata की स्थिति

CryptoStone में image और video महत्वपूर्ण visual layer हैं, लेकिन Gem NFT की core identity metadata और on-chain records से बनती है।

Metadata fields:

| Field | Example |
| --- | --- |
| `name` | CryptoStone Garnet #1 |
| `description` | digital gemstone protocol asset |
| `stoneType` | Garnet |
| `weight` | digital weight grade |
| `color` | D, E, F आदि |
| `clarity` | FL, IF, VVS1 आदि |
| `cut` | cut grade |
| `image` | HTTPS या IPFS media URL |
| `animation_url` | video URL |

CryptoStone HTTPS metadata API के माध्यम से wallets और marketplaces को readable JSON दे सकता है। Watcher बाद में image/video generate करके IPFS पर upload कर सकता है और metadata response update कर सकता है।

यह process user से additional wallet confirmation नहीं माँगना चाहिए। Core transaction claim या refinement execution तक सीमित रहनी चाहिए।

Media delay होने पर भी core attributes पहले दिखाई देने चाहिए। इससे NFT की identity image server पर निर्भर नहीं रहती।