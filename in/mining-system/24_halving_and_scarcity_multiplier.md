# 24 Halving dan Scarcity Multiplier

Struktur halving CryptoStone diterapkan secara independen untuk setiap stone, bukan untuk seluruh collection sekaligus.

Jika supply maksimum stone (j) adalah (N\_j), jumlah yang telah ditambang adalah (n\_j), dan rasio progres mining adalah (q\_j), maka dihitung sebagai berikut:

$$
q_j = n_j \div N_j
$$

Misalnya, jika supply maksimum Diamond adalah 110,000 dan sejauh ini 55,000 telah ditambang:

$$
q_{\text{Diamond}} = 55,000 \div 110,000 = 0.5
$$

Ini berarti Diamond Pool telah mencapai tahap mining 50%.

Scarcity Multiplier (S\_j) setiap stone meningkat sesuai rasio progres mining (q\_j).

| Mined Supply Ratio | Remaining Supply | Scarcity Multiplier |
| ------------------ | ---------------- | ------------------- |
| 0% \~ 50% | 100% \~ 50% | 1x |
| 50% \~ 75% | 50% \~ 25% | 2x |
| 75% \~ 87.5% | 25% \~ 12.5% | 4x |
| 87.5% \~ 93.75% | 12.5% \~ 6.25% | 8x |
| 93.75% \~ 96.875% | 6.25% \~ 3.125% | 16x |
| 96.875% or more | 3.125% or less | 32x |

Ini dapat digeneralisasi sebagai berikut:

$$
S_j(q_j) = 2^{\min\left(5, \lfloor \log_2 \left( 1 \div (1 - q_j) \right) \rfloor \right)}
$$

Namun, ketika (q\_j) berada pada rentang awal, (S\_j(q\_j)) tetap minimum 1x. Dalam implementasi smart contract nyata, alih-alih menghitung formula ini secara langsung, struktur dapat diterapkan berdasarkan tabel rentang yang telah dipublikasikan sebelumnya.

Formula ini mengekspresikan struktur di mana difficulty mining meningkat secara geometris ketika supply tersisa dari setiap stone berkurang. Ini membawa struktur dunia nyata, di mana biaya dan kesulitan mining meningkat saat cadangan tambang menurun, ke lingkungan digital.
