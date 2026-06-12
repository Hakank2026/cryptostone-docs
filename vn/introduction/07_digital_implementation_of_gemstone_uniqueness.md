# 07\_digital\_implementation\_of\_gemstone\_uniqueness

CryptoStone can consider various technical options to express the uniqueness of each gemstone. Fungible token structures, semi-fungible token structures, and composite token structures may all be possible, but the core objective of CryptoStone is for each gemstone to have a unique attribute combination and tokenId.

Therefore, gemstones in CryptoStone are represented as Gem NFTs with unique tokenIds and attribute combinations. This choice is not intended to emphasize a specific technical standard, but is the result of implementing the following functions.

| Implementation Requirement                              | Reason for Adopting NFT Structure                                           |
| ------------------------------------------------------- | --------------------------------------------------------------------------- |
| Need for a unique tokenId for each gemstone             | NFT structure is suitable for representing assets based on unique tokenIds. |
| Storage of different attributes for each gemstone       | tokenId-specific metadata and on-chain attribute structures are possible.   |
| Need for ownership transfer records                     | Standard NFT transfer and ownership recording are possible.                 |
| Representation of multiple stones within one collection | 12 stones can be distinguished through the stoneType attribute.             |
| Tracking of rarity and transaction history              | Provenance and rarity tracking for each NFT are possible.                   |

In other words, the Gem NFT structure in CryptoStone is not a means of creating image NFTs. It is a technical container for expressing the uniqueness and attribute-based asset nature of digital gemstones.
