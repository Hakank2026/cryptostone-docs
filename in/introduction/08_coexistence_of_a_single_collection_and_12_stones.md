# 08 Koeksistensi satu collection dan 12 stone

CryptoStone tidak memisahkan 12 stone menjadi NFT collection individual. Semua batu permata diterbitkan dari satu Gem NFT contract.

Namun, setiap NFT dibedakan oleh atribut `stoneType`.

| Token ID | Stone Type | Weight | Color | Clarity | Cut |
| -------- | ---------- | ------ | ----- | ------- | --- |
| #10291 | Diamond | 3.42 CT | D | VVS1 | 6 Star |
| #58102 | Ruby | 8.13 CT | G | VS2 | 4 Star |
| #77410 | Sapphire | 1.25 CT | E | IF | 5 Star |

Struktur ini memiliki keunggulan berikut.

| Keunggulan | Deskripsi |
| ---------- | --------- |
| Collection terpadu | Menjaga identitas satu collection CryptoStone. |
| Data transaksi terkonsentrasi | Mencegah nilai collection dan data transaksi terfragmentasi di berbagai marketplace. |
| Manajemen rarity lebih mudah | Memungkinkan semua batu dibandingkan dalam satu sistem ranking rarity. |
| Pelestarian individualitas stone | Mengekspresikan independensi setiap batu melalui atribut `stoneType`. |
| Batas supply | NFT contract dapat memverifikasi supply maksimum berdasarkan stone. |

NFT contract mengelola jumlah penerbitan secara terpisah berdasarkan stone.

```
maxSupplyByStone[Diamond] = 110,000
mintedByStone[Diamond] < maxSupplyByStone[Diamond]
```

Karena itu, meskipun permintaan penerbitan berasal dari Diamond Pool, Diamond NFT tidak dapat diterbitkan lagi setelah supply maksimum Diamond tercapai.
