# 10 Hash Power, Mining Power, dan Proof of Mining

Dalam Bitcoin, miner memperoleh probabilitas membuat block melalui hash power. Semakin tinggi hash power, semakin besar kemungkinan menemukan block. Namun, hash power tidak dapat secara sewenang-wenang mengubah aturan penerbitan atau struktur difficulty Bitcoin. Dengan kata lain, hash power bukan otoritas untuk mengubah aturan jaringan, melainkan resource komputasi untuk memperoleh lebih banyak peluang mining dalam aturan tetap.

CryptoStone mengabstraksikan konsep ini ke dalam struktur mining batu permata digital. Dalam CryptoStone, konsep yang setara dengan hash power adalah **Mining Power**, dan jumlah kerja yang terakumulasi oleh Mining Power seiring waktu adalah **Proof of Mining**, atau **PoM**.

| Bitcoin | CryptoStone |
| ------- | ----------- |
| Hash Power | Mining Power |
| Proof of Work | Proof of Mining, PoM |
| ASIC / Mining Equipment | STONX yang distake |
| Block Reward | Gem NFT |
| Network Difficulty | Pool Difficulty |
| Halving | Scarcity Multiplier |
| BTC Issuance | Gem NFT Issuance |
| Miner | STONX Staker / Gem Miner |

PoM bukan token terpisah yang dapat ditransfer atau diperdagangkan. PoM adalah indikator jumlah kerja on-chain yang dicatat contract berdasarkan partisipasi mining pengguna dan berjalannya waktu. PoM juga bukan algoritma konsensus jaringan. Dalam CryptoStone, PoM adalah nilai internal protokol untuk menentukan apakah pengguna telah mencapai kondisi claim Gem NFT dari stone pool tertentu.

Ketika pengguna (i) stake sejumlah STONX ((s\_{i,j})) ke stone pool ((j)), dan lock-up multiplier adalah ((L\_i)), Mining Power pengguna ((P\_{i,j})) didefinisikan sebagai berikut.

$$
P_{i,j} = s_{i,j} \times L_i
$$

Nilai PoM pengguna terakumulasi seiring waktu sebagai berikut.

$$
PoM_{i,j}(t + \Delta t) = PoM_{i,j}(t) + P_{i,j} \times \Delta t
$$

Di sini, (PoM\_{i,j}(t)) adalah nilai Proof of Mining yang terakumulasi oleh pengguna ((i)) dalam stone pool ((j)) hingga waktu ((t)).

PoM terakumulasi secara independen untuk setiap stone pool. Misalnya, PoM yang terakumulasi di Diamond Pool hanya dapat digunakan untuk claim Diamond NFT dan tidak dapat dikonversi menjadi PoM untuk Ruby Pool atau Sapphire Pool. Struktur ini melindungi independensi, kelangkaan, dan difficulty mining tiap stone pool.

Pengguna dengan Mining Power lebih tinggi dapat mencapai ambang PoM yang diperlukan lebih cepat, tetapi tidak dapat menaikkan probabilitas memperoleh batu yang lebih langka atau memilih grade batu tertentu secara sewenang-wenang.
