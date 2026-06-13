# 40 Struktur Metadata

Esensi CryptoStone Gem NFT bukan gambar itu sendiri, melainkan data atribut yang merepresentasikan batu permata.

| Attribute | Example |
| --------- | ------- |
| `stoneType` | Garnet, Ruby, Sapphire |
| `weight` | 3.42 CT |
| `color` | D, E, F, G dan lainnya |
| `clarity` | FL, IF, VVS1 dan lainnya |
| `cut` | 1 Star ~ 6 Star |
| `rarity` | Salah satu dari Common, Rare, Epic, Legendary, Genesis |
| `minedAt` | Block atau timestamp mining |
| `pool` | Alamat mining pool |
| `generation` | Original atau refinement generation |

CryptoStone dapat menyediakan metadata dasar NFT melalui HTTPS metadata API. Ini memungkinkan pengguna melihat name, description, attributes, grade, dan tokenId dengan cepat di wallet atau marketplace segera setelah minting.

## 40.1 Metadata Trust Model

CryptoStone memisahkan atribut inti dari layer presentasi. Atribut esensial batu permata ditentukan oleh contract dan data yang dapat diverifikasi publik. HTTPS metadata API menyediakan atribut tersebut dalam bentuk JSON yang mudah dibaca oleh wallet, marketplace, dan frontend.

Model trust adalah sebagai berikut.

| Layer | Role | Trust Standard |
| ----- | ---- | -------------- |
| Smart Contract | Menentukan minting, ownership, tokenId, dan atribut inti | On-chain verification |
| HTTPS Metadata API | Menyediakan name, description, attributes, dan media URL dalam JSON | Respons publik dan mapping atribut deterministik |
| Watcher Finalization | Menghasilkan image/video, mengupload IPFS media, dan memperbarui metadata response | Log publik dan mapping berdasarkan tokenId |
| IPFS Media | Menyimpan file image dan video | Content-addressed media verification |

Image dan video dibuat kemudian melalui proses watcher finalization, diupload ke IPFS, dan direfleksikan dalam metadata API serta JSON response. Proses ini tidak memerlukan konfirmasi wallet tambahan dari pengguna. Transaksi inti yang dikonfirmasi wallet sebaiknya terbatas pada eksekusi claim atau refinement.

Ini berarti CryptoStone Gem NFT dapat mempertahankan verifiability teknis sekaligus ekspresi visual. Batu tidak didefinisikan oleh gambar saja. Gambar adalah representasi visual dari atribut on-chain dan metadata, sedangkan atribut itu sendiri mendefinisikan nilai koleksi.

Image dan video dapat berubah dalam format tampilan seiring perkembangan ekosistem, tetapi atribut inti dan tokenId harus tetap tidak berubah. Misalnya, Garnet Gem NFT dengan atribut berikut:

* Garnet
* 3.42 CT
* D Color
* IF Clarity
* 5 Star Cut

tetap mempertahankan identitas inti yang sama, baik ditampilkan sebagai gambar statis, animasi, maupun representasi 3D.

Karena itu, meskipun upload IPFS atau media generation tertunda, atribut inti Gem NFT harus terlihat terlebih dahulu melalui contract dan HTTPS metadata API. Setelah watcher mengisi data image dan video IPFS, NFT marketplace dan UI wallet dapat menampilkan media yang telah diperbarui.

Desain ini mencegah pengguna mengulangi konfirmasi wallet tambahan hanya untuk metadata finalization. Desain ini juga memastikan bahwa meskipun image server atau API sementara tertunda, atribut inti CryptoStone NFT tetap berada dalam struktur data on-chain atau dapat diverifikasi publik.
