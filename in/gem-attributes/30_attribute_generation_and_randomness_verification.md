# 30 Generasi Atribut dan Randomness

Atribut batu permata tidak dimasukkan secara manual oleh operator. Pada saat mining, mining contract menentukan Weight, Color, Clarity, dan Cut berdasarkan nilai acak.

Poin pentingnya adalah metode generasi randomness harus dapat diverifikasi. Jika operator dapat menghasilkan NFT grade tinggi secara sewenang-wenang, desentralisasi dan kelangkaan CryptoStone akan rusak.

CryptoStone mengurangi ketergantungan pada satu elemen randomness dengan menggabungkan entropy yang diberikan pengguna, entropy multi-block terbaru, `prevrandao` Ethereum, claim state, dan nilai khusus contract.

Strukturnya dapat dinyatakan sebagai berikut.

$$
S = H(userEntropy, user, positionId, claimNonce, prevrandao, chainId, contract)
$$

$$
B_i = blockhash(blockNumber - 1 - (H(S,i) \bmod 30)) \quad \text{for } i \in \{0..4\}
$$

$$
R = H(userEntropy, B_0, B_1, B_2, B_3, B_4, prevrandao, claimState, contractState)
$$

Model ini tidak bergantung pada satu nilai block atau satu nilai pengguna. Model ini mencampur entropy pengguna, beberapa referensi block terbaru, entropy konsensus Ethereum, dan claim-specific state untuk mengurangi hasil yang dapat diprediksi atau bergantung pada operator.

Metode generasi randomness CryptoStone mengikuti prinsip berikut.

| Prinsip | Deskripsi |
| ------- | --------- |
| Unpredictability | Operator maupun pengguna tidak boleh mengetahui hasil di muka |
| No result selection | Operator tidak boleh memilih hasil menguntungkan atau menolak hasil tidak menguntungkan |
| Prevention of retry | Setelah permintaan randomness, pengguna tidak boleh membatalkan atau mencoba ulang sebelum hasil difinalisasi |
| No Admin Reroll | Operator tidak boleh reroll atau mengganti hasil tertentu |
| Public verification | Proses generasi hasil harus on-chain atau dapat diverifikasi publik |
| Fixed probability table | Tabel probabilitas atribut harus dipublikasikan sebelum deployment dan tidak dapat diubah setelah finalization |
| Immutability after issuance | Atribut tidak boleh diubah setelah penerbitan |

Setelah hasil acak diminta, pengguna tidak boleh membatalkan atau retry claim karena hasilnya tidak menguntungkan. Operator juga tidak boleh mengalokasikan hasil menguntungkan kepada pengguna tertentu atau memilih seed yang menghasilkan kombinasi atribut tertentu. Ini adalah syarat inti agar batu permata langka dihasilkan oleh struktur randomness yang dapat diverifikasi, bukan oleh diskresi operator.

Setelah penerbitan, atribut inti Gem NFT harus dibekukan. Metadata inti seperti Weight, Color, Clarity, Cut, stoneType, minedAt, dan minedFromPool tidak boleh dapat diubah oleh operator.
