# 11 Mining Pool Template và Factory

12 Mining Pool Contract không phải các phần phát triển riêng biệt với logic khác nhau. Tất cả pool được triển khai dựa trên cùng một Mining Pool Template đã kiểm định. Mỗi pool sử dụng cùng logic cốt lõi, chỉ khác nhau ở các tham số sau.

| Tham số | Mô tả |
| ------- | ----- |
| stoneType | Stone Type được khai thác từ pool đó |
| maxSupply | Số lượng phát hành tối đa của stone đó |
| baseMiningInterval | Chu kỳ khai thác cơ bản |
| targetPoolPower | Mining Power tham chiếu |
| scarcitySchedule | Cấu trúc halving theo từng stone |
| poolAddress | Địa chỉ phát hành được NFT contract cho phép |

Vì mục đích này, CryptoStone có thể sử dụng cấu trúc Pool Factory. Pool Factory tạo 12 pool theo từng stone dựa trên cùng một Mining Pool Template và cố định các tham số cốt lõi của từng pool sau khi triển khai.

| Lợi thế | Mô tả |
| ------- | ----- |
| Tính nhất quán mã nguồn | Tất cả 12 pool sử dụng cùng một logic. |
| Hiệu quả audit | Kiểm toán bảo mật có thể tập trung vào một Pool Template. |
| Giảm rủi ro | Giảm khả năng phát sinh lỗi ngoại lệ do mỗi pool dùng mã khác nhau. |
| Minh bạch tham số | Khác biệt giữa các pool chỉ đến từ các giá trị cố định đã công bố. |
| Khả năng mở rộng | Có thể dùng cùng cấu trúc khi thêm stone pool mới trong tương lai. |

Nhờ đó, CryptoStone duy trì cấu trúc kinh tế của “12 mỏ độc lập” trong khi tăng tính ổn định và minh bạch bằng cách sử dụng cùng một smart contract template có thể kiểm chứng.
