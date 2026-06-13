# 20 Điều chỉnh tham gia dài hạn và Flexible Cooldown

Lock Multiplier có thể được áp dụng theo thời gian staking để thưởng cho người tham gia dài hạn.

| Lock Type | Lock Period | Mining Multiplier (L\_i) | Maturity Burn | Returned STONX | Cooldown |
| --------- | ----------- | ------------------------ | ------------- | -------------- | -------- |
| Flexible | None | 1.00x | 0% | 100% | 7 days |
| Short Lock | 90 days | 1.05x | 2.5% | 97.5% | None |
| Medium Lock | 180 days | 1.12x | 5% | 95% | None |
| Long Lock | 365 days | 1.25x | 10% | 90% | None |

Flexible Lock không có depreciation burn, nhưng áp dụng thời gian cooldown 7 ngày sau yêu cầu unstake để ngăn thanh khoản ngắn hạn vào ra quá nhanh.

Lock-up dài hạn không bắt buộc. Người dùng có thể chọn Flexible nếu không muốn chịu depreciation, và chỉ chọn lock dài hơn với depreciation nếu muốn có Mining Power cao hơn.

Cấu trúc này tìm kiếm sự cân bằng sau.

| Lựa chọn | Lợi ích | Chi phí |
| -------- | ------- | ------- |
| Flexible | Tham gia tự do, không depreciation | Chờ hoàn trả 7 ngày |
| 90-day Lock | Mining Power cao hơn nhẹ | 2.5% depreciation |
| 180-day Lock | Mining Power mức trung bình | 5% depreciation |
| 365-day Lock | Mining Power cao nhất | 10% depreciation |

Lock-up multiplier được giới hạn tối đa ở 1.25x. Điều này nhằm cung cấp phần bù hợp lý cho người tham gia dài hạn, đồng thời ngăn một người tham gia lớn cụ thể có vị thế quá thuận lợi.

Ngay cả trong thời gian lock-up, người dùng vẫn có thể claim Gem NFT khi PoM đạt ngưỡng cần thiết. Nói cách khác, lock-up giới hạn thời điểm STONX có thể được hoàn trả, nhưng không cấm việc claim Gem NFT.
