# 16 Base Mining Unit

CryptoStone menetapkan unit partisipasi dasar sebagai berikut.

**Base Mining Unit = 1,000 STONX**

Base Mining Unit adalah unit referensi minimum yang diperlukan agar pengguna dapat berpartisipasi dalam mining pool. Unit ini mencegah fragmentasi partisipasi yang tidak bermakna akibat deposit terlalu kecil, sambil tetap memungkinkan pengguna umum mulai mengakumulasi Proof of Mining, atau PoM, pada skala yang dapat diakses. Base Mining Unit bukan janji bahwa claim dapat dilakukan dalam jangka pendek.

CryptoStone mengadopsi model akumulasi PoM agar banyak pengguna dapat berpartisipasi dalam mining. Pengguna dapat masuk ke mining pool mulai dari 1,000 STONX dan mengakumulasi PoM sebanding dengan jumlah stake dan waktu.

Pengguna dapat claim Gem NFT ketika PoM terakumulasi mencapai atau melebihi ambang yang diperlukan (R\_j) dari pool terkait.

$$
PoM_{i,j}(t) \ge R_j
$$

Kecepatan supply jangka panjang tidak ditentukan oleh Base Mining Unit saja. CryptoStone menggabungkan unit partisipasi 1,000 STONX dengan Target Pool Power, Protocol Reference Power, Pool Difficulty, dan Scarcity Multiplier agar total supply Gem NFT ditambang secara bertahap dalam jangka panjang.

Dalam model awal Garnet Pool, dengan asumsi Pool Difficulty dan Scarcity Multiplier keduanya 1x serta Protocol Reference Power 100,000 Power, estimasi interval claim dapat dipahami sebagai berikut.

| Active Stake | Estimasi interval claim untuk 1 Garnet NFT |
| ------------ | ------------------------------------------ |
| 1,000 STONX | Sekitar 197 hari |
| 4,800 STONX | Sekitar 41 hari |
| 6,000 STONX | Sekitar 32.8 hari |
| 100,000 STONX | Sekitar 1.97 hari |

Struktur ini memungkinkan peserta dasar dengan 1,000 STONX tetap mengakumulasi PoM, memberikan pengalaman mining bulanan bagi peserta skala menengah, dan memberi peluang claim lebih sering bagi pengguna dengan Mining Power tinggi. Mining Power hanya memengaruhi frekuensi claim; Mining Power tidak memberi pengguna kemampuan memilih grade atau atribut Gem NFT.

Pengembang menganggap struktur ini penting bagi ekspansi ekosistem CryptoStone. Kelangkaan NFT harus dijaga melalui total supply, probabilitas atribut, dan struktur halving, sementara partisipasi pengguna harus diperluas melalui hambatan masuk yang rendah dan model akumulasi PoM.
