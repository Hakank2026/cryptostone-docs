# 41 Ekspansi Ekosistem dan Gem Refinement

CryptoStone dapat memperluas utility Gem NFT melalui Marketplace, Arena, dan Gem Refinement tanpa menggantikan struktur mining inti.

Marketplace mendukung price discovery dan transfer kepemilikan untuk Gem NFT yang telah ditambang. Pengguna dapat list Gem NFT yang mereka tambang atau refine, sementara pembeli dapat memilih target koleksi berdasarkan stone type, grade, Rarity Score, attributes, tokenId, riwayat trading, dan status media. Marketplace tidak menjamin rarity itu sendiri; marketplace adalah tempat harga pasar terbentuk berdasarkan atribut yang dipublikasikan dan provenance on-chain.

Arena adalah module bergaya game yang memperluas utility Gem NFT. Pengguna dapat menggunakan Gem NFT sebagai entry seed atau participation credential dan bergabung ke meja Duel, Battle, atau Arena melalui entry fee berbasis STONX. Arena menambahkan konteks penggunaan di luar koleksi, tetapi tidak secara langsung mengubah probabilitas mining atau grade NFT.

Gem Refinement adalah struktur utility pascamining opsional yang memungkinkan Gem NFT hasil mining digunakan kembali. Ini bukan sistem penerbitan tambahan tanpa batas. Sebaliknya, dua Gem NFT dengan `stoneType` yang sama digabung untuk membuat satu Refined Gem NFT dengan `stoneType` yang sama, membentuk mekanisme supply compression.

Struktur refinement dasar adalah:

| Input | Output | Supply Change |
| ----- | ------ | ------------- |
| 2 Gem NFT dari stone yang sama | 1 Refined Gem NFT dari stone yang sama | Total supply NFT berkurang 1 |

Saat satu refinement dieksekusi, dua parent Gem NFT diburn atau dibuat tidak dapat dipulihkan, dan hanya satu Refined Gem NFT baru yang dibuat. Karena itu, total circulating NFT supply berkurang satu.

Contoh:

* Garnet #102 + Garnet #481 -> Refined Garnet #9001
* Ruby #220 + Ruby #841 -> Refined Ruby #9102

Dalam model awal, Gem Refinement sebaiknya hanya mengizinkan refinement sesama stone. Misalnya, dua Garnet Gem NFT dapat menjadi satu Refined Garnet Gem NFT, dan dua Ruby Gem NFT dapat menjadi satu Refined Ruby Gem NFT. Cross-stone refinement dapat membuat struktur supply, scarcity, halving, dan mining difficulty terlalu kompleks, sehingga tepat untuk dikecualikan dari model awal.

Gem Refinement dapat membuat Gem NFT baru dengan:

* Rarity Score lebih tinggi,
* metadata generasi refinement,
* catatan parent tokenId,
* efek visual tambahan,
* dan jumlah supply lebih rendah.

Namun, refinement tidak boleh dirancang untuk menjamin upgrade berhasil tanpa syarat. Lebih baik memasukkan hasil berbasis probabilitas agar supply compression, ketegangan koleksi, dan use case untuk NFT tier rendah dapat hidup bersama.

Hasil refinement dapat didasarkan pada tier yang lebih tinggi dari dua parent Gem NFT.

$$
T_{base} = \max(T_1, T_2)
$$

Di sini, (T\_1) dan (T\_2) adalah tier dari dua parent Gem NFT, dan (T\_{base}) adalah tier referensi untuk menentukan hasil refinement.

Rarity tier disatukan menjadi lima grade: Common, Rare, Epic, Legendary, dan Genesis.

| Tier Index | Tier |
| ---------- | ---- |
| 0 | Common |
| 1 | Rare |
| 2 | Epic |
| 3 | Legendary |
| 4 | Genesis |

Hasil refinement sebaiknya paling sering tetap berada pada base tier. Probabilitas downgrade harus rendah, dan upgrade, ketika terjadi, harus dibatasi satu atau dua tier. NFT tier rendah dapat memiliki probabilitas upgrade relatif lebih tinggi, sementara NFT tier tinggi harus memiliki probabilitas upgrade lebih rendah untuk melindungi scarcity tier tinggi.

Contoh model probabilitas awal:

| Base Tier | Downgrade | Same Tier | +1 Tier | +2 Tier |
| --------- | --------: | --------: | ------: | ------: |
| Common | None | 68.0% | 27.0% | 5.0% |
| Rare | 1.0% | 76.0% | 20.0% | 3.0% |
| Epic | 1.5% | 88.0% | 10.0% | 0.5% |
| Legendary | 2.0% | 97.0% | 1.0% | None |
| Genesis | Limited | Limited | Limited | Limited |

Genesis diperlakukan sebagai tier koleksi tertinggi. Dalam model awal, sebaiknya penggunaannya sebagai material refinement dibatasi. Struktur ini menjaga excitement refinement sambil mencegah penciptaan NFT high-grade yang berlebihan.

Jika refinement antar parent tier berbeda diizinkan, probabilitas hasil dapat disesuaikan berdasarkan tier gap.

$$
\Delta T = |T_1 - T_2|
$$

| Tier Gap | Adjustment Coefficient | Meaning |
| -------- | ---------------------: | ------- |
| 0 | 100% | Refinement tier sama; probabilitas dasar berlaku |
| 1 | 70% | Refinement tier berdekatan; probabilitas upgrade sedikit berkurang |
| 2 | 40% | Gap tier besar; probabilitas upgrade berkurang signifikan |
| 3 or more | Limited | Dapat dibatasi pada model awal |

Melalui refinement, Gem NFT grade rendah tidak sekadar ditinggalkan. Mereka dapat berfungsi sebagai bahan baku supply compression. Gem NFT grade tinggi tetap langka, sementara NFT grade rendah memperoleh utility sebagai input refinement. Ini memberi CryptoStone struktur sirkulasi internal untuk Gem NFT.
