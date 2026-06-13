# 11 Mining Pool Template dan Factory

12 Mining Pool Contract bukan pengembangan terpisah dengan logika berbeda. Semua pool dideploy berdasarkan Mining Pool Template yang sama dan telah diaudit. Setiap pool menggunakan logika inti yang sama, sementara hanya parameter berikut yang berbeda.

| Parameter | Deskripsi |
| --------- | --------- |
| stoneType | Stone Type yang ditambang dari pool tersebut |
| maxSupply | Jumlah penerbitan maksimum stone tersebut |
| baseMiningInterval | Interval mining dasar |
| targetPoolPower | Mining Power referensi |
| scarcitySchedule | Struktur halving berdasarkan stone |
| poolAddress | Alamat penerbitan yang diizinkan oleh NFT contract |

Untuk tujuan ini, CryptoStone dapat menggunakan struktur Pool Factory. Pool Factory membuat 12 pool khusus stone berdasarkan Mining Pool Template yang sama dan mengunci parameter inti setiap pool setelah deployment.

| Keunggulan | Deskripsi |
| ---------- | --------- |
| Konsistensi kode | Semua 12 pool menggunakan logika yang sama. |
| Efisiensi audit | Audit keamanan dapat fokus pada satu Pool Template. |
| Pengurangan risiko | Mengurangi kemungkinan bug pengecualian akibat kode berbeda pada tiap pool. |
| Transparansi parameter | Perbedaan antarpool hanya berasal dari nilai tetap yang dipublikasikan. |
| Skalabilitas | Struktur yang sama dapat digunakan saat menambah stone pool baru di masa depan. |

Dengan demikian, CryptoStone mempertahankan struktur ekonomi “12 tambang independen” sambil meningkatkan stabilitas dan transparansi melalui smart contract template yang sama dan dapat diverifikasi.
