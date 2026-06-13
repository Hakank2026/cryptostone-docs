# 35 Cấu trúc burn STONX

Trong CryptoStone, STONX không chỉ là phương tiện thanh toán. Nó là tài nguyên khai thác dùng để tham gia mining đá quý kỹ thuật số. Giống như thiết bị và năng lượng khai thác ngoài đời thực bị tiêu hao, đồng thời thiết bị giảm giá trị theo thời gian, STONX gửi vào CryptoStone mining pool có cấu trúc khấu hao kỹ thuật số trong quá trình mining.

Nhà phát triển xem cấu trúc burn STONX không phải là cơ chế bảo đảm tăng giá token, mà là cơ chế biểu đạt mức tiêu thụ tài nguyên và cấu trúc khan hiếm cần thiết cho mining đá quý kỹ thuật số.

Cấu trúc burn STONX cơ bản của CryptoStone có thể xảy ra trong hai trường hợp chính.

| Burn Type | Thời điểm phát sinh | Mục đích |
| --------- | ------------------- | -------- |
| Claim Burn | Khi claim Gem NFT | Biểu đạt chi phí mining và khan hiếm |
| Maturity Burn | Khi unstake sau khi lock-up đáo hạn | Biểu đạt khấu hao tài nguyên mining |

Hai trường hợp này tạo thành cấu trúc burn cơ bản của CryptoStone. Khi hệ sinh thái mở rộng, cơ chế burn STONX bổ sung có thể được giới thiệu. Ví dụ gồm burn một phần từ phí Marketplace, entry fee hoặc settlement burn trong Arena hay các game module khác, và execution-cost burn trong Gem Refinement. Mọi cơ chế burn mở rộng phải được định nghĩa bằng contract và quy tắc công khai riêng mà không làm tổn hại các quy tắc mining cốt lõi.

Lượng burn (B\_{claim,j}) phát sinh khi claim Gem NFT được tính bằng công thức sau:

$$
B_{claim,j} = \beta \times S_j
$$

Ở đây, (\beta) là Base Claim Burn, và (S\_j) là Scarcity Multiplier của stone tương ứng.

Claim Burn không phải cố định 2 STONX cho mọi pool. Giá trị cơ sở là 2 STONX, nhưng lượng burn thực tế thay đổi theo Scarcity Multiplier của từng stone pool. Ví dụ, pool ở vùng 2x burn 4 STONX mỗi claim, còn pool ở vùng 4x burn 8 STONX. Vì vậy, Claim Burn là chi phí burn động phản ánh tiến độ mining và độ khó của từng pool.

Giá trị tham chiếu ban đầu:

| Scarcity Multiplier | Claim Burn |
| ------------------- | ---------- |
| 1x | 2 STONX |
| 2x | 4 STONX |
| 4x | 8 STONX |
| 8x | 16 STONX |
| 16x | 32 STONX |
| 32x | 64 STONX |

Base Claim Burn biểu thị cấu trúc tiêu thụ tối thiểu của chi phí mining. Nó không được thiết kế để làm giảm mạnh tổng nguồn cung. STONX bị burn không được trả cho nhà vận hành hay foundation; nó bị loại bỏ vĩnh viễn khỏi lưu thông. Nhờ đó, STONX không chỉ là tài sản được gửi vào, mà còn là tài nguyên mining kỹ thuật số thực sự được sử dụng và tiêu hao trong hệ sinh thái CryptoStone.
