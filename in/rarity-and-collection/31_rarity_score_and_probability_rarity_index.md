# 31 Rarity Score dan Probability Rarity Index

CryptoStone menggunakan dua indikator untuk mengukur kelangkaan setiap batu.

| Indikator | Tujuan |
| --------- | ------ |
| Rarity Score | Skor 0~100 yang mudah dipahami pengguna |
| Probability Rarity Index | Indikator kelangkaan matematis berdasarkan probabilitas kemunculan aktual |

## 31.1 Rarity Score

$$
\text{Rarity Score}
=
\text{Pool Supply Score}
+
\text{Weight Score}
+
\text{Color Score}
+
\text{Clarity Score}
+
\text{Cut Score}
$$

Alokasi skor adalah sebagai berikut.

| Atribut | Max Score |
| ------- | --------: |
| Pool Supply Score | 20 |
| Weight | 20 |
| Color | 20 |
| Clarity | 20 |
| Cut | 20 |
| Total | 100 |

Pool Supply Score dihitung berdasarkan Max Supply tiap stone. Item ini bukan bonus yang otomatis membuat satu stone lebih bernilai dari stone lain. Sebaliknya, pool dengan Max Supply lebih rendah menerima skor dasar lebih rendah, sehingga lebih sulit mencapai final tier tinggi dalam pool tersebut.

$$
\text{Pool Supply Score}
=
15 + 5 \times
\frac{\text{StoneMaxSupply} - \text{MinCollectionSupply}}
{\text{MaxCollectionSupply} - \text{MinCollectionSupply}}
$$

Nilai referensi:

* MaxCollectionSupply = 220,000
* MinCollectionSupply = 110,000

Pool Supply Score digunakan sebagai nilai tetap antara 15 dan 20.

| Stone | Max Supply | Pool Supply Score |
| ----- | ---------: | ----------------: |
| Diamond | 110,000 | 15.0 |
| Emerald | 120,000 | 15.5 |
| Ruby | 130,000 | 15.9 |
| Sapphire | 140,000 | 16.4 |
| Pearl | 150,000 | 16.8 |
| Garnet | 160,000 | 17.3 |
| Amethyst | 170,000 | 17.7 |
| Aquamarine | 180,000 | 18.2 |
| Spinel | 190,000 | 18.6 |
| Opal | 200,000 | 19.1 |
| Topaz | 210,000 | 19.5 |
| Zircon | 220,000 | 20.0 |

Misalnya, Diamond memiliki Max Supply 110,000 sehingga menerima Pool Supply Score terendah. Zircon memiliki Max Supply 220,000 sehingga menerima Pool Supply Score tertinggi. Akibatnya, memperoleh Epic, Legendary, atau Genesis di Diamond Pool lebih sulit. Namun, Diamond Gem NFT grade tinggi tersebut memenuhi dua kondisi sekaligus, yaitu supply rendah dan grade tinggi, sehingga dapat membentuk nilai koleksi yang lebih kuat di pasar.

Struktur ini tidak dimaksudkan untuk memberi peringkat pool dengan skor sederhana. Struktur ini mencerminkan perbedaan supply antarpool dalam difficulty final tier. Pool dengan supply rendah membuat hasil tier tinggi lebih sulit, sedangkan pool dengan supply tinggi membuatnya relatif lebih mudah.

## 31.2 Probability Rarity Index

Sementara Rarity Score adalah indikator perbandingan yang ramah pengguna, Probability Rarity Index adalah indikator kelangkaan matematis berdasarkan probabilitas kemunculan setiap atribut.

Probabilitas (P(g)) bahwa kombinasi atribut Gem NFT (`g`) muncul didefinisikan sebagai berikut:

$$
P(g) = P_{\text{stone}} \times P_{\text{weight}} \times P_{\text{color}} \times P_{\text{clarity}} \times P_{\text{cut}}
$$

Berdasarkan ini, indikator rarity berbasis probabilitas dihitung.

$$
\text{Probability Rarity Index} = -\log_{10}(P(g))
$$

Indikator ini menunjukkan seberapa langka kombinasi atribut Gem NFT tertentu secara statistik.

Misalnya, kombinasi berikut sangat langka.

* Diamond
* 100.00 CT atau lebih
* D Color
* FL Clarity
* 6 Star Cut

Kombinasi seperti ini menerima Rarity Score tinggi dan juga memiliki Probability Rarity Index yang sangat tinggi.

Rarity Score digunakan sebagai dasar final tier yang ramah pengguna. Rentang tier dasar adalah:

| Final Tier | Rarity Score Range | Peran |
| ---------- | ------------------ | ----- |
| Common | 0 ~ 34 | Kelompok batu paling umum, collectible dasar dan material refinement |
| Rare | 35 ~ 50 | Collectible tingkat menengah yang lebih langka dari hasil mining biasa |
| Epic | 51 ~ 74 | Rentang high-tier yang dapat dirasakan pengguna sebagai keberhasilan berarti |
| Legendary | 75 ~ 89 | Rentang collectible sangat langka dan bernilai tinggi |
| Genesis | 90 ~ 100 | Rentang tertinggi yang mencerminkan kombinasi atribut ekstrem dan skor tertinggi |

Ketika Pool Supply Score 15~20 dan tabel skor Weight, Color, Clarity, dan Cut diterapkan bersama, rentang ini menargetkan ekspektasi rata-rata sekitar satu hasil Epic atau lebih tinggi per 36 NFT yang ditambang. Hasil aktual bervariasi tergantung kombinasi atribut acak dan penyesuaian supply berdasarkan pool.

Target tersebut dapat dinyatakan dengan model ekspektasi berikut. Ketika `n` NFT ditambang dari pool tertentu `s`, jumlah ekspektasi hasil Epic atau lebih tinggi dihitung dengan menjumlahkan semua probabilitas atribut bersama Pool Supply Score pool tersebut.

$$
E_{\ge Epic}(n)
=
n \cdot
\sum_{s \in S}
\pi_s
\sum_{w \in W}
\sum_{c \in C}
\sum_{q \in Q}
\sum_{u \in U}
\mathbf{1}
\left[
Score_s + Score_w + Score_c + Score_q + Score_u \ge 51
\right]
P_s(w)P_s(c)P_s(q)P_s(u)
\approx
\frac{n}{36}
$$

Di sini, `S` adalah himpunan stone pool, `π_s` adalah porsi partisipasi setiap pool, dan `W/C/Q/U` adalah himpunan atribut Weight, Color, Clarity, dan Cut. Formula ini tidak dimaksudkan untuk menjamin harga pasar. Formula ini adalah referensi desain protokol agar distribusi rarity tidak menjadi terlalu umum atau terlalu tertutup.

Dengan menggunakan Rarity Score dan Probability Rarity Index bersama-sama, CryptoStone menyediakan sistem skor intuitif bagi collector sekaligus sistem rarity berbasis data yang dapat diverifikasi secara matematis.
