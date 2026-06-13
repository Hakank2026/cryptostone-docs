# 38 Prinsip finalisasi protokol

Agar CryptoStone dapat mengarah pada karakteristik aset terdesentralisasi seperti Bitcoin, aturan intinya tidak boleh diubah secara sewenang-wenang setelah deployment.

| Fixed Item | Description |
| ---------- | ----------- |
| Total STONX supply | 1,200,000,000 STONX |
| STONX circulation structure | Open Market Allocation |
| Max Supply by stone | Jumlah penerbitan NFT maksimum tiap stone |
| Base Mining Interval by stone | Interval mining dasar |
| Target Pool Power | Nilai referensi awal 40,000,000 Power |
| Base Mining Unit | 1,000 STONX |
| Weight probability table | Probabilitas generasi Weight |
| Color probability table | Probabilitas generasi Color grade |
| Clarity probability table | Probabilitas generasi Clarity grade |
| Cut probability table | Probabilitas generasi Cut grade |
| Scarcity Multiplier | Difficulty multiplier berbasis halving |
| Claim Burn formula | Formula burn saat claim |
| Mining Power formula | Formula Mining Power berbasis staking |
| PoM formula | Akumulasi Proof of Mining dan kondisi claim |
| Lock Multiplier | Mining multiplier berdasarkan periode lock-up |
| Maturity Burn formula | Formula depreciation burn saat lock-up maturity |

Setelah pengaturan awal selesai, protokol harus difinalisasi. Setelah itu, operator tidak boleh dapat menaikkan supply secara sewenang-wenang, mengubah probabilitas rarity, atau menerbitkan NFT secara manual kepada pengguna tertentu.

Core contract CryptoStone harus memiliki source code yang diverifikasi publik setelah deployment, dan supply token, supply NFT, tabel probabilitas, formula mining, serta struktur perhitungan ambang PoM tidak boleh dapat diubah setelah finalization.

Jika fungsi administratif terbatas diperlukan sebelum finalization, daftar, tujuan, waktu penghapusan, dan metode kontrol fungsi tersebut harus dipublikasikan dengan jelas. Setelah finalization, authority administratif yang terkait dengan jumlah penerbitan inti, tabel probabilitas, hak penerbitan, dan metode perhitungan PoM harus dihapus atau dinonaktifkan.

Desentralisasi tidak selesai hanya karena sesuatu dideploy di blockchain. Desentralisasi terbentuk melalui aturan yang tidak dapat diubah operator, kode yang dapat diverifikasi siapa pun, dan struktur yang dapat diikuti siapa pun.
