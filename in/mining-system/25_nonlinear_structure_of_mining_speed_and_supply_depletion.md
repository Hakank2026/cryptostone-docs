# 25 Struktur nonlinier kecepatan mining dan deplesi supply

## Depletion

Struktur mining CryptoStone bukan model penerbitan linear sederhana. Setiap stone memiliki supply, mining interval, Pool Difficulty, dan Scarcity Multiplier yang independen; ketika progres mining meningkat, kecepatan mining melambat karena Scarcity Multiplier.

Jika Mining Power efektif dari stone pool $(j)$ adalah $(P\_{eff,j})$, dapat dinyatakan sebagai berikut:

$$
P_{eff,j} = \min(P_j, P_j^*)
$$

Ini berarti ketika total Mining Power di bawah Target Pool Power, power partisipasi aktual memengaruhi kecepatan mining; ketika total Mining Power melebihi Target Pool Power, kecepatan mining efektif dibatasi melalui peningkatan difficulty.

Jumlah mining yang diharapkan per unit waktu dari stone pool $(j)$, $(\lambda\_j)$, dapat dinyatakan secara konseptual sebagai berikut:

$$
\lambda_j = P_{eff,j} \div (M_{ref} \times T_j \times S_j)
$$

Di sini, $(M\_{ref})$ adalah Protocol Reference Power, $(T\_j)$ adalah Base Mining Interval dari stone, dan $(S\_j)$ adalah Scarcity Multiplier. Base Mining Unit adalah unit partisipasi minimum, sementara kecepatan mining jangka panjang dikalibrasi oleh Protocol Reference Power dan Target Pool Power.

Waktu yang diperlukan agar stone tertentu mencapai progres mining $(q)$ dapat dinyatakan dengan model nonlinier berikut:

$$
Time_j(q) = (N_j \times M_{ref} \times T_j \div P_{eff,j}) \times \int_0^q S_j(x)\,dx
$$

Formula ini menunjukkan bahwa struktur mining CryptoStone bukan model yang habis secara linear, melainkan model mining nonlinier di mana kecepatan mining perlahan menurun seiring berkurangnya supply stone yang tersisa.

Karena itu, Gem NFT dapat ditambang relatif aktif pada tahap awal, tetapi setelah tahap 90%, Scarcity Multiplier meningkat dan kecepatan mining supply tersisa melambat secara signifikan.
