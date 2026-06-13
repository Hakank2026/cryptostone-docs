# 07 Implementasi digital atas keunikan batu permata

CryptoStone dapat mempertimbangkan berbagai opsi teknis untuk mengekspresikan keunikan setiap batu. Struktur fungible token, semi-fungible token, dan composite token semuanya mungkin, tetapi tujuan inti CryptoStone adalah agar setiap batu memiliki kombinasi atribut dan tokenId yang unik.

Karena itu, batu permata dalam CryptoStone direpresentasikan sebagai Gem NFT dengan tokenId dan kombinasi atribut unik. Pilihan ini tidak dimaksudkan untuk menekankan standar teknis tertentu, tetapi merupakan hasil dari penerapan fungsi berikut.

| Kebutuhan Implementasi | Alasan Mengadopsi Struktur NFT |
| ---------------------- | ------------------------------ |
| Membutuhkan tokenId unik untuk setiap batu | Struktur NFT cocok untuk merepresentasikan aset berbasis tokenId unik. |
| Penyimpanan atribut berbeda untuk setiap batu | Metadata spesifik tokenId dan struktur atribut on-chain memungkinkan hal ini. |
| Membutuhkan catatan transfer kepemilikan | Transfer NFT standar dan pencatatan kepemilikan dimungkinkan. |
| Representasi banyak stone dalam satu collection | 12 stone dapat dibedakan melalui atribut `stoneType`. |
| Pelacakan rarity dan riwayat transaksi | Provenance dan rarity tiap NFT dapat dilacak. |

Dengan kata lain, struktur Gem NFT dalam CryptoStone bukan sarana untuk membuat image NFT. Struktur ini adalah wadah teknis untuk mengekspresikan keunikan dan sifat aset berbasis atribut dari batu permata digital.
