# 22 Ambang PoM yang Diperlukan

Ambang PoM yang diperlukan untuk menambang satu batu permata ditentukan oleh Protocol Reference Power, Base Mining Interval tiap stone, Pool Difficulty, dan Scarcity Multiplier.

Jika Base Mining Interval stone (j) adalah (T\_j), Protocol Reference Power adalah (M\_{ref}), Pool Difficulty adalah (D\_j), dan Scarcity Multiplier adalah (S\_j), maka ambang PoM yang diperlukan (R\_j) didefinisikan sebagai berikut:

$$
R_j = M_{ref} \times T_j \times D_j \times S_j
$$

Nilai referensi CryptoStone adalah sebagai berikut:

* Base Mining Unit = 1,000 STONX
* Protocol Reference Power = 100,000 Power
* Target Pool Power = 40,000,000 Power

Base Mining Unit adalah unit partisipasi minimum, sedangkan Protocol Reference Power adalah power referensi yang digunakan untuk mengalibrasi kecepatan mining. Dengan memisahkan kedua nilai ini, CryptoStone dapat mempertahankan unit partisipasi yang mudah diakses sekaligus kontrol supply jangka panjang.

Misalnya, jika Base Mining Interval Garnet Pool adalah 170,000 detik dan Pool Difficulty serta Scarcity Multiplier keduanya 1x, perhitungannya adalah sebagai berikut:

$$
R_{\text{Garnet}} = 100{,}000 \times 170{,}000 \times 1 \times 1
$$

$$
R_{\text{Garnet}} = 17{,}000{,}000{,}000 \text{ PoM}
$$

Ketika Mining Power pengguna (i) adalah (P\_{i,j}), estimasi waktu yang diperlukan pengguna untuk claim satu NFT dari stone (j) dapat dinyatakan sebagai berikut:

$$
E[T_{i,j}] = R_j \div P_{i,j}
$$

Misalnya, ketika pengguna stake 6,000 STONX ke Garnet Pool dengan kondisi Flexible:

$$
E[T_{i,\text{Garnet}}] = 17{,}000{,}000{,}000 \div 6{,}000
$$

$$
= 2{,}833{,}333 \text{ detik}
$$

$$
\approx 32.8 \text{ hari}
$$

Dengan kata lain, dalam kondisi awal, pengguna yang stake 6,000 STONX dapat claim sekitar satu Garnet NFT dalam kurang lebih satu bulan. Pengguna dengan stake lebih kecil mengakumulasi PoM lebih lambat, sedangkan pengguna dengan stake lebih besar dapat mencapai kondisi claim lebih cepat.
