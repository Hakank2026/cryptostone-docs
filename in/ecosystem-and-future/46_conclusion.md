# 46 Kesimpulan

CryptoStone adalah protokol yang menerapkan konsep batu permata digital pada smart contract.

Protokol ini mendefinisikan STONX sebagai resource mining dan Gem NFT sebagai hasil mining, menghubungkan keduanya melalui Proof of Mining, atau PoM. Pengguna menyetor STONX ke mining pool, mengakumulasi Mining Power dan PoM seiring waktu, lalu claim Gem NFT ketika ambang yang diperlukan tercapai.

## Struktur inti

| Item | Struktur |
| ---- | -------- |
| Mining Resource | STONX |
| Initial Supply | 1,200,000,000 STONX |
| Mining Result | CryptoStone Gem NFT |
| Stone Types | 12 pool berbasis birthstone |
| Attribute Generation | Weight, Color, Clarity, Cut, Rarity |
| Metadata | HTTPS metadata API + watcher finalization + IPFS media |
| Rarity Standard | Rarity Score + Probability Rarity Index |

## Struktur eksekusi protokol

| Tahap | Deskripsi |
| ----- | --------- |
| Participation | Masuk ke mining pool mulai dari 1,000 STONX |
| Mining Power | Dihitung dari jumlah stake, periode lock-up, dan parameter pool |
| PoM | Nilai kerja mining yang terakumulasi seiring waktu |
| Claim | Claim Gem NFT setelah mencapai ambang PoM yang diperlukan |
| Claim Burn | 2 STONX x Scarcity Multiplier |
| Maturity Burn | Depreciation burn berdasarkan periode lock-up |
| Randomness | User entropy, recent multi-block entropy, `prevrandao`, claim state, dan nilai khusus contract |
| Finalization | Atribut inti tetap saat claim; media diperbarui kemudian oleh watcher |
| Open Verification | Source code, audit reports, catatan penanganan LP, dan tabel probabilitas |

Tujuan CryptoStone bukan menghubungkan NFT dengan kepemilikan batu permata nyata. Tujuannya adalah menafsirkan kembali struktur batu permata sebagai model aset digital-native: mining difficulty, scarcity, atribut individual, dan nilai koleksi.

Whitepaper ini tidak mengklaim bahwa CryptoStone adalah penemuan besar atau invensi yang sepenuhnya baru. Ini adalah perubahan perspektif dan percobaan baru. Jika atribut, kelangkaan, dan collectibility batu permata diterima oleh pasar sebagai sistem nilai yang bermakna, CryptoStone dapat berkembang menjadi kategori baru batu permata digital.

CryptoStone harus terus berkembang dengan contract transparan, randomness yang dapat diverifikasi, data supply publik, struktur metadata yang aman, dan alat yang ramah pengguna agar sistem lebih mudah dipahami dan diverifikasi.
