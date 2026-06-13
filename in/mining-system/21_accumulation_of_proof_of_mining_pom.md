# 21 Akumulasi Proof of Mining, PoM

CryptoStone menggunakan model Proof of Mining, atau PoM, yang mengabstraksikan konsep Proof-of-Work Bitcoin ke dalam struktur mining batu permata digital, bukan sistem poin atau kredit sederhana.

PoM mengacu pada jumlah kerja mining yang terakumulasi seiring waktu oleh pengguna yang stake STONX pada stone pool tertentu. PoM bukan token terpisah yang dapat ditransfer atau diperdagangkan, melainkan indikator jumlah kerja on-chain yang dicatat contract berdasarkan partisipasi mining pengguna dan berjalannya waktu.

Nilai PoM pengguna `(i)` untuk stone pool tertentu `(j)` terakumulasi seiring waktu sebagai berikut.

$$
PoM_{i,j}(t + \Delta t) = PoM_{i,j}(t) + P_{i,j} \times \Delta t
$$

Misalnya, Mining Power pengguna yang stake 100,000 STONX ke Diamond Pool dengan kondisi Flexible adalah sebagai berikut.

$$
P_{i,Diamond} = 100,000 \times 1.00 = 100,000
$$

Jika pengguna menunggu selama 100,000 detik, PoM yang terakumulasi adalah sebagai berikut.

$$
PoM = 100,000 \times 100,000
$$

$$
PoM = 10,000,000,000
$$

Ketika PoM terakumulasi pengguna mencapai atau melebihi ambang PoM yang diperlukan dari pool terkait, pengguna dapat claim Gem NFT.

$$
PoM_{i,j}(t) \ge R_j
$$

Saat Gem NFT diclaim, ambang yang diperlukan `(R_j)` dikurangkan dari nilai PoM pengguna di pool tersebut.

$$
PoM_{i,j,new} = PoM_{i,j,old} - R_j
$$

Struktur ini mencegah PoM berlebih di atas ambang hilang secara tidak perlu. Misalnya, jika ambang PoM yang diperlukan adalah 22,000,000,000 dan pengguna memiliki 23,000,000,000 PoM saat claim Gem NFT, maka 1,000,000,000 PoM tersisa setelah claim dan disimpan untuk siklus mining berikutnya.

PoM terakumulasi secara independen untuk setiap stone pool. PoM yang terakumulasi di Diamond Pool hanya dapat digunakan untuk claim Diamond NFT dan tidak dapat dikonversi menjadi PoM untuk Ruby Pool atau Sapphire Pool. Struktur ini melindungi independensi, kelangkaan, dan difficulty mining setiap stone pool.

Walaupun pengguna unstake STONX dari pool tertentu, PoM yang telah terakumulasi dapat tetap tercatat di pool tersebut. Namun, setelah unstake, Mining Power pengguna di pool itu menjadi 0, sehingga tidak ada PoM tambahan yang terakumulasi. Jika pengguna stake STONX lagi di pool yang sama, PoM baru terakumulasi di atas PoM yang sudah ada.

Jika pengguna menambah stake STONX di pool yang sama, PoM yang ada tetap dipertahankan dan hanya Mining Power setelah penambahan stake yang meningkat. Sebaliknya, jika jumlah stake dikurangi, PoM yang ada tetap, tetapi kecepatan akumulasi masa depan menurun.

PoM tidak dapat ditransfer keluar atau diperdagangkan, dan tidak dapat dipindahkan ke stone pool lain. Ini karena PoM bukan aset itu sendiri, melainkan indikator jumlah kerja yang dikumpulkan oleh pengguna tertentu melalui partisipasi mining nyata di pool tertentu.
