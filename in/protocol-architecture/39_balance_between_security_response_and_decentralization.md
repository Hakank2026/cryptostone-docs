# 39 Keseimbangan antara respons keamanan dan desentralisasi

CryptoStone menjadikan No Admin Mint dan No Central Server sebagai prinsip inti. Namun, pada tahap pengembangan dan deployment awal, struktur administratif terbatas mungkin diperlukan untuk security audit, testing, dan respons kerentanan.

| Stage | Management Structure |
| ----- | -------------------- |
| Testnet and audit stage | Authority administratif terbatas mungkin ada |
| Before official deployment | Verifikasi parameter dan pemeriksaan keamanan |
| After official launch | Penghapusan authority perubahan penerbitan, supply, dan probabilitas inti |
| After finalization | No Admin Mint, No Supply Change, No Probability Change |

Jika fungsi emergency pause ada, fungsi tersebut hanya boleh digunakan secara terbatas untuk mencegah insiden keamanan, bukan untuk memanipulasi hasil penerbitan atau mengubah supply. Fungsi emergency juga harus dibatasi melalui metode yang dapat diverifikasi publik seperti timelock atau multisignature, dan tidak boleh menjadi alat bagi operator untuk mengubah rarity atau jumlah penerbitan secara sewenang-wenang.

Contract utama CryptoStone terdiri dari token contract, Gem NFT contract, Mining Pool Template, Pool Factory, dan struktur generasi randomness. Contract ini sebaiknya menjalani security audit sebelum dan sesudah deployment, dan hasil audit serta catatan respons kerentanan besar harus dipublikasikan.

Elemen verifikasi utama yang perlu dipublikasikan adalah sebagai berikut.

| Verification Item | Description |
| ----------------- | ----------- |
| Contract Source Verification | Publikasi dan verifikasi source code contract yang dideploy |
| Audit Report | Laporan audit untuk contract utama dan struktur randomness |
| Admin Function List | Keberadaan fungsi administratif dan rencana penghapusan |
| Finalize Event | Waktu finalisasi parameter inti dan event record |
| LP Lock / Burn Proof | Catatan penanganan LP terkait initial liquidity |
| Probability Table Hash | Verifikasi bahwa tabel probabilitas sesuai dengan nilai yang dipublikasikan sebelum deployment |
| Metadata Freeze | Apakah atribut inti immutable setelah penerbitan |

Struktur ini dimaksudkan untuk menyeimbangkan respons keamanan praktis dan karakteristik aset terdesentralisasi.
