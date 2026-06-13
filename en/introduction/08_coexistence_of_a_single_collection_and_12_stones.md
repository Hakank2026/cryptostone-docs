# 08\_coexistence\_of\_a\_single\_collection\_and\_12\_stones

CryptoStone does not separate the 12 stones into individual NFT collections. All gemstones are issued from one Gem NFT contract.

However, each NFT is distinguished by the `stoneType` attribute.

| Token ID | Stone Type | Weight  | Color | Clarity | Cut    |
| -------- | ---------- | ------- | ----- | ------- | ------ |
| #10291   | Diamond    | 3.42 CT | D     | VVS1    | 6 Star |
| #58102   | Ruby       | 8.13 CT | G     | VS2     | 4 Star |
| #77410   | Sapphire   | 1.25 CT | E     | IF      | 5 Star |

This structure has the following advantages.

| Advantage                           | Description                                                                               |
| ----------------------------------- | ----------------------------------------------------------------------------------------- |
| Unified collection                  | Maintains the single collection identity of CryptoStone.                                  |
| Concentrated transaction data       | Prevents collection value and transaction data from being fragmented across marketplaces. |
| Easier rarity management            | Allows all gemstones to be compared within one rarity ranking system.                     |
| Preservation of STONX individuality | Expresses the independence of each gemstone through the `stoneType` attribute.            |
| Supply limitation                   | The NFT contract can verify maximum supply by STONX.                                      |

The NFT contract separately manages issuance quantity by STONX.

```
maxSupplyByStone[Diamond] = 110,000
mintedByStone[Diamond] < maxSupplyByStone[Diamond]
```

Therefore, even if an issuance request comes from the Diamond Pool, no further Diamond NFTs can be issued once the maximum Diamond supply has been reached.
