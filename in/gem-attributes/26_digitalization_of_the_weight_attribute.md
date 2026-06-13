# 26 Atribut Weight

Weight menggunakan CT, atau carat, sebagai unit umum untuk semua stone. Nilai weight setiap batu dihasilkan secara acak.

* Minimum Weight = 0.10 CT
* Maximum Weight = 200.00 CT
* Storage Unit = 0.01 CT

Smart contract tidak menyimpan angka desimal secara langsung. Sebaliknya, nilai disimpan sebagai integer dalam unit 0.01 CT.

| Displayed Weight | Contract Stored Value |
| ---------------- | --------------------- |
| 0.10 CT | 10 |
| 1.25 CT | 125 |
| 10.50 CT | 1050 |
| 200.00 CT | 20000 |

Weight tidak dihasilkan dengan probabilitas yang sama. Karena batu permata dengan carat lebih besar lebih langka di dunia nyata, weight yang lebih besar di CryptoStone dihasilkan dengan probabilitas lebih rendah.

| Weight Range | Probability | Score |
| ------------ | ----------- | ----: |
| 0.10 ~ 1.99 CT | 75.00% | 0 |
| 2.00 ~ 4.99 CT | 15.00% | 5 |
| 5.00 ~ 9.99 CT | 6.00% | 10 |
| 10.00 ~ 49.99 CT | 3.50% | 16 |
| 50.00 ~ 200.00 CT | 0.50% | 20 |

Score dalam tabel bukan final tier Gem NFT secara langsung. Score tersebut adalah skor atribut Weight yang digunakan untuk menghitung Rarity Score dan Probability Rarity Index. Final tier Gem NFT ditentukan dengan menggabungkan Pool Supply Score, Weight, Color, Clarity, dan Cut ke dalam sistem lima tier: Common, Rare, Epic, Legendary, dan Genesis.
