# 23 Penyesuaian Pool Difficulty

Jika jumlah peserta meningkat dan total Mining Power bertambah, batu permata dapat ditambang terlalu cepat. Untuk mencegah hal ini, setiap pool menyesuaikan difficulty berdasarkan total Mining Power.

Jika total Mining Power dari stone pool (j) adalah (P\_j), Target Pool Power adalah (P\_j^\*), dan Pool Difficulty adalah (D\_j), maka dihitung sebagai berikut:

$$
D_j = \max(1, P_j \div P_j^*)
$$

Nilai referensi CryptoStone adalah sebagai berikut:

$$
P_j^* = 40,000,000 \text{ Power}
$$

Contoh:

| Target Pool Power | Total Pool Mining Power | Calculation | Pool Difficulty |
| ----------------- | ----------------------: | ----------- | --------------: |
| 40,000,000 | 20,000,000 | 20,000,000 ÷ 40,000,000 = 0.5 → max(1, 0.5) | 1.0x |
| 40,000,000 | 40,000,000 | 40,000,000 ÷ 40,000,000 = 1.0 | 1.0x |
| 40,000,000 | 80,000,000 | 80,000,000 ÷ 40,000,000 = 2.0 | 2.0x |
| 40,000,000 | 200,000,000 | 200,000,000 ÷ 40,000,000 = 5.0 | 5.0x |

Alasan menerapkan struktur `max(1, ·)` adalah mencegah difficulty turun di bawah 1.0x meskipun total Mining Power lebih rendah dari Target Pool Power. Dengan kata lain, struktur ini mencegah kecepatan mining menjadi terlalu cepat dibandingkan kecepatan referensi pada tahap awal ketika partisipasi masih rendah.

Sebaliknya, ketika total Mining Power melebihi Target Pool Power, Pool Difficulty meningkat secara proporsional. Misalnya, jika total Mining Power suatu pool naik menjadi 80,000,000 Power, Pool Difficulty menjadi 2.0x. Dalam kondisi ini, waktu yang diperlukan pengguna yang sama untuk menambang satu NFT juga kira-kira menjadi dua kali lipat.

Dalam implementasi smart contract, BPS dapat digunakan untuk menghindari operasi desimal.

$$
D_{j,\mathrm{BPS}} = \max(10,000, P_j \times 10,000 \div P_j^*)
$$

Di sini, 10,000 BPS = 1.0x.

Struktur ini memungkinkan kecepatan mining keseluruhan menyesuaikan secara alami seiring meningkatnya partisipasi, serta mencegah supply tiap stone habis terlalu cepat.
