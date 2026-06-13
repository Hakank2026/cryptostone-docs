# 35 Struktur Burn STONX

Dalam CryptoStone, STONX bukan sekadar metode pembayaran. STONX adalah resource mining yang digunakan untuk berpartisipasi dalam mining batu permata digital. Seperti peralatan dan energi mining dunia nyata dikonsumsi dan peralatan mengalami depresiasi seiring waktu, STONX yang disetor ke CryptoStone mining pool memiliki struktur depresiasi digital selama proses mining.

Pengembang melihat struktur burn STONX bukan sebagai mekanisme untuk menjamin apresiasi harga token, tetapi sebagai mekanisme untuk mengekspresikan konsumsi resource dan struktur kelangkaan yang diperlukan untuk mining batu permata digital.

Struktur burn STONX dasar CryptoStone dapat terjadi dalam dua kasus utama.

| Burn Type | Waktu Terjadi | Tujuan |
| --------- | ------------- | ------ |
| Claim Burn | Saat claim Gem NFT | Ekspresi biaya mining dan kelangkaan |
| Maturity Burn | Saat unstake setelah lock-up maturity | Ekspresi depresiasi resource mining |

Dua kasus ini membentuk struktur burn dasar CryptoStone. Seiring ekosistem berkembang, mekanisme burn STONX tambahan dapat diperkenalkan. Contohnya termasuk partial burn dari biaya Marketplace, entry fee atau settlement burn di Arena atau module game lain, dan execution-cost burn dalam Gem Refinement. Setiap mekanisme burn yang diperluas harus didefinisikan melalui contract dan aturan publik terpisah tanpa merusak aturan mining inti.

Jumlah burn (B\_{claim,j}) yang terjadi saat claim Gem NFT dihitung dengan formula berikut:

$$
B_{claim,j} = \beta \times S_j
$$

Di sini, (\beta) adalah Base Claim Burn, dan (S\_j) adalah Scarcity Multiplier dari stone terkait.

Claim Burn bukan 2 STONX tetap untuk setiap pool. Nilai dasarnya adalah 2 STONX, tetapi jumlah burn aktual berubah sesuai Scarcity Multiplier setiap stone pool. Misalnya, pool pada zona 2x membakar 4 STONX per claim, sedangkan pool pada zona 4x membakar 8 STONX. Karena itu, Claim Burn adalah biaya burn dinamis yang mencerminkan progres mining dan difficulty tiap pool.

Nilai referensi awal:

| Scarcity Multiplier | Claim Burn |
| ------------------- | ---------- |
| 1x | 2 STONX |
| 2x | 4 STONX |
| 4x | 8 STONX |
| 8x | 16 STONX |
| 16x | 32 STONX |
| 32x | 64 STONX |

Base Claim Burn merepresentasikan struktur konsumsi minimum dari biaya mining. Struktur ini tidak dirancang untuk mengurangi total supply secara cepat. STONX yang diburn tidak dibayarkan kepada operator atau foundation; STONX tersebut dihapus permanen dari sirkulasi. Melalui hal ini, STONX berfungsi bukan hanya sebagai aset yang disetor, tetapi sebagai resource mining digital yang benar-benar digunakan dan dikonsumsi dalam ekosistem CryptoStone.
