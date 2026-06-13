# 20 Penyesuaian partisipasi jangka panjang dan Flexible Cooldown

Lock Multiplier dapat diterapkan berdasarkan periode staking untuk memberi insentif kepada peserta jangka panjang.

| Lock Type | Lock Period | Mining Multiplier (L\_i) | Maturity Burn | Returned STONX | Cooldown |
| --------- | ----------- | ------------------------ | ------------- | -------------- | -------- |
| Flexible | None | 1.00x | 0% | 100% | 7 days |
| Short Lock | 90 days | 1.05x | 2.5% | 97.5% | None |
| Medium Lock | 180 days | 1.12x | 5% | 95% | None |
| Long Lock | 365 days | 1.25x | 10% | 90% | None |

Flexible Lock tidak memiliki depreciation burn, tetapi periode cooldown 7 hari diterapkan setelah permintaan unstake untuk mencegah liquidity jangka pendek masuk dan keluar terlalu cepat.

Lock-up jangka panjang tidak wajib. Pengguna dapat memilih Flexible tanpa depreciation, dan hanya memilih lock lebih lama dengan depreciation jika menginginkan Mining Power lebih tinggi.

Struktur ini mencari keseimbangan berikut.

| Pilihan | Manfaat | Biaya |
| ------- | ------- | ----- |
| Flexible | Partisipasi bebas, tanpa depreciation | Masa tunggu pengembalian 7 hari |
| 90-day Lock | Mining Power sedikit lebih tinggi | 2.5% depreciation |
| 180-day Lock | Mining Power tingkat menengah | 5% depreciation |
| 365-day Lock | Mining Power tertinggi | 10% depreciation |

Lock-up multiplier dibatasi maksimum 1.25x. Ini dirancang untuk memberi kompensasi wajar kepada peserta jangka panjang sekaligus mencegah peserta besar tertentu memperoleh posisi yang terlalu menguntungkan.

Bahkan selama periode lock-up, pengguna dapat claim Gem NFT begitu PoM mencapai ambang yang diperlukan. Dengan kata lain, lock-up membatasi waktu STONX dapat dikembalikan, tetapi tidak melarang claim Gem NFT.
