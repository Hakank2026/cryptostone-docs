# 36 Struktur lock-up, depresiasi, dan pengembalian

Ketika pengguna memilih periode lock-up dan menyetor STONX ke mining pool, sebagian STONX diburn sebagai depresiasi pada saat unstake setelah lock-up berakhir, dan sisa STONX dikembalikan.

| Lock Type | Lock Period | Mining Multiplier | Maturity Burn | Returned STONX | Cooldown |
| --------- | ----------- | ----------------- | ------------- | -------------- | -------- |
| Flexible | None | 1.00x | 0% | 100% | 7 days |
| Short Lock | 90 days | 1.05x | 2.5% | 97.5% | None |
| Medium Lock | 180 days | 1.12x | 5% | 95% | None |
| Long Lock | 365 days | 1.25x | 10% | 90% | None |

Jika jumlah STONX yang distake pengguna _i_ adalah _s_<sub>_i_</sub>, dan tingkat depresiasi menurut periode lock-up adalah _δ_<sub>_i_</sub>, maka jumlah STONX yang diburn saat maturity (_M_<sub>_i_</sub>) didefinisikan sebagai berikut.

$$
M_i = s_i \times \delta_i
$$

Jumlah STONX yang dikembalikan (_R_<sub>_i_</sub>) adalah sebagai berikut.

$$
R_i = s_i - M_i
$$

Struktur ini memberikan Mining Power lebih tinggi kepada peserta jangka panjang sekaligus mencerminkan biaya penggunaan resource mining. Dengan kata lain, pengguna dapat memilih lock-up lebih panjang untuk memperoleh kecepatan mining lebih tinggi, tetapi harus menerima depreciation burn lebih tinggi di akhir lock-up.

Lock-up jangka panjang tidak wajib. Pengguna yang tidak ingin menanggung beban burn STONX dapat memilih metode Flexible. Lock-up jangka panjang adalah struktur opsional bagi peserta yang menginginkan Mining Power lebih tinggi, dan depresiasi ditafsirkan sebagai biaya penggunaan resource mining digital yang menyertai pilihan tersebut.

Pengembang percaya struktur ini sebaiknya ditafsirkan bukan sekadar sebagai penalti, tetapi sebagai “depresiasi akibat penggunaan peralatan mining digital.” Seperti peralatan mining nyata mengalami keausan seiring waktu, STONX dalam CryptoStone menyediakan Mining Power saat disimpan di mining pool, dan sebagian diburn sesuai periode penggunaan.
