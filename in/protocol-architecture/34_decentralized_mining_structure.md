# 34 Struktur mining terdesentralisasi

Dalam CryptoStone, mining tidak dilakukan oleh server atas nama pengguna. Pengguna stake STONX ke stone pool pilihannya; setelah nilai PoM mencapai ambang yang diperlukan dari pool tersebut seiring waktu, pengguna langsung memanggil fungsi contract seperti `claimGem()` untuk menerima Gem NFT.

1. Pengguna memegang STONX.
2. Pengguna memilih stone pool.
3. Pengguna stake STONX.
4. Mining Power dihasilkan.
5. PoM terakumulasi seiring waktu.
6. Ketika PoM mencapai ambang yang diperlukan, pengguna memanggil `claimGem()`.
7. Contract memverifikasi apakah kondisi mining terpenuhi.
8. Atribut dihasilkan menggunakan randomness yang dapat diverifikasi.
9. Gem NFT diterbitkan.
10. NFT ditransfer ke wallet pengguna.

Dalam proses ini, tidak ada server pusat yang menerbitkan batu permata atau menetapkan atribut. Kondisi dan hasil mining ditentukan oleh kode.

Smart contract tidak berjalan sendiri secara otomatis. Namun, siapa pun dapat memanggil contract, dan contract memverifikasi serta mengeksekusi hasil sesuai kondisi yang telah ditentukan. Karena itu, struktur mining CryptoStone dapat beroperasi tanpa server pusat.

Pengembang percaya bahwa poin penting dalam struktur ini bukan sekadar “tidak ada server”, tetapi bahwa “bahkan tanpa server, pengguna dapat memanggil contract secara langsung dan menerima hasil mining sesuai aturan yang telah ditentukan.”
