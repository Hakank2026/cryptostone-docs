# 40 Metadata Structure

The essence of CryptoStone Gem NFT is not the image itself, but the attribute data that represents the gemstone.

| Attribute | Example |
| --------- | ------- |
| `stoneType` | Garnet, Ruby, Sapphire |
| `weight` | 3.42 CT |
| `color` | D, E, F, G and others |
| `clarity` | FL, IF, VVS1 and others |
| `cut` | 1 Star ~ 6 Star |
| `rarity` | One of Common, Rare, Epic, Legendary, Genesis |
| `minedAt` | Mined block or timestamp |
| `pool` | Mining pool address |
| `generation` | Original or refinement generation |

CryptoStone may provide NFT base metadata through an HTTPS metadata API. This allows users to see the name, description, attributes, grade, and tokenId quickly in wallets or marketplaces immediately after minting.

## 40.1 Metadata Trust Model

CryptoStone separates core attributes from the presentation layer. The essential attributes of a gemstone are determined by contracts and publicly verifiable data. The HTTPS metadata API provides those attributes in JSON form that wallets, marketplaces, and frontends can easily read.

The trust model is as follows.

| Layer | Role | Trust Standard |
| ----- | ---- | -------------- |
| Smart Contract | Determines minting, ownership, tokenId, and core attributes | On-chain verification |
| HTTPS Metadata API | Provides name, description, attributes, and media URLs in JSON | Public response and deterministic attribute mapping |
| Watcher Finalization | Generates image and video, uploads IPFS media, and updates metadata response | Public logs and tokenId-based mapping |
| IPFS Media | Stores image and video files | Content-addressed media verification |

Images and videos are generated later by the watcher finalization process, uploaded to IPFS, and reflected in the metadata API and JSON response. This process does not require additional wallet confirmation from the user. The wallet-confirmed core transaction should be limited to claim or refinement execution.

This means CryptoStone Gem NFT can preserve both technical verifiability and visual expression. The gemstone is not defined by the image alone. The image is a visual representation of the on-chain and metadata attributes, while the attributes themselves define the collectible value.

The image and video may change in display format as the ecosystem develops, but the core attributes and tokenId should remain unchanged. For example, a Garnet Gem NFT with the following attributes:

* Garnet
* 3.42 CT
* D Color
* IF Clarity
* 5 Star Cut

retains the same core identity regardless of whether it is shown as a static image, animation, or 3D representation.

Therefore, even if IPFS upload or media generation is delayed, the core attributes of the Gem NFT should be visible first through the contract and HTTPS metadata API. Once the watcher fills IPFS image and video data, NFT marketplaces and wallet UIs can display the updated media.

This design prevents users from repeating additional wallet confirmations solely for metadata finalization. It also ensures that even if an image server or API is temporarily delayed, the core attributes of a CryptoStone NFT remain in an on-chain or publicly verifiable data structure.
