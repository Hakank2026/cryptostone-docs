# 36 Cấu trúc lock-up, khấu hao và hoàn trả

Khi người dùng chọn thời gian lock-up và gửi STONX vào mining pool, một phần STONX được burn dưới dạng khấu hao tại thời điểm unstake sau khi lock-up kết thúc, và phần STONX còn lại được hoàn trả.

| Lock Type | Lock Period | Mining Multiplier | Maturity Burn | Returned STONX | Cooldown |
| --------- | ----------- | ----------------- | ------------- | -------------- | -------- |
| Flexible | None | 1.00x | 0% | 100% | 7 days |
| Short Lock | 90 days | 1.05x | 2.5% | 97.5% | None |
| Medium Lock | 180 days | 1.12x | 5% | 95% | None |
| Long Lock | 365 days | 1.25x | 10% | 90% | None |

Nếu lượng STONX người dùng _i_ stake là _s_<sub>_i_</sub>, và tỷ lệ khấu hao theo thời gian lock-up là _δ_<sub>_i_</sub>, lượng STONX bị burn khi đáo hạn (_M_<sub>_i_</sub>) được định nghĩa như sau.

$$
M_i = s_i \times \delta_i
$$

Lượng STONX được hoàn trả (_R_<sub>_i_</sub>) như sau.

$$
R_i = s_i - M_i
$$

Cấu trúc này cung cấp Mining Power cao hơn cho người tham gia dài hạn, đồng thời phản ánh chi phí sử dụng tài nguyên mining. Nói cách khác, người dùng có thể chọn lock-up dài hơn để có tốc độ mining cao hơn, nhưng phải chấp nhận mức burn khấu hao cao hơn ở cuối lock-up.

Lock-up dài hạn không bắt buộc. Người dùng không muốn chịu gánh nặng burn STONX có thể chọn Flexible. Lock-up dài hạn là cấu trúc tùy chọn cho người tham gia muốn Mining Power cao hơn, và khấu hao được hiểu là chi phí sử dụng tài nguyên mining kỹ thuật số đi kèm lựa chọn đó.

Nhà phát triển cho rằng cấu trúc này nên được hiểu không đơn thuần là hình phạt, mà là “khấu hao phát sinh từ việc sử dụng thiết bị mining kỹ thuật số.” Giống như thiết bị mining thật hao mòn theo thời gian, STONX trong CryptoStone cung cấp Mining Power khi được gửi vào mining pool, và một phần bị burn theo thời gian sử dụng.
