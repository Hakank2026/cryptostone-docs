# 16 Base Mining Unit

CryptoStone đặt đơn vị tham gia cơ bản như sau.

**Base Mining Unit = 1,000 STONX**

Base Mining Unit là đơn vị tham chiếu tối thiểu để người dùng tham gia mining pool. Nó ngăn việc chia nhỏ tham gia quá mức thành các khoản không có ý nghĩa, đồng thời cho phép người dùng phổ thông bắt đầu tích lũy Proof of Mining, hay PoM, ở quy mô có thể tiếp cận. Base Mining Unit không phải là cam kết rằng người dùng sẽ claim được trong ngắn hạn.

CryptoStone áp dụng mô hình tích lũy PoM để nhiều người dùng có thể tham gia mining. Người dùng có thể vào mining pool từ 1,000 STONX và tích lũy PoM theo tỷ lệ với lượng stake và thời gian.

Người dùng có thể claim Gem NFT khi PoM tích lũy đạt hoặc vượt ngưỡng cần thiết (R\_j) của pool tương ứng.

$$
PoM_{i,j}(t) \ge R_j
$$

Tốc độ cung dài hạn không được quyết định chỉ bởi Base Mining Unit. CryptoStone kết hợp đơn vị tham gia 1,000 STONX với Target Pool Power, Protocol Reference Power, Pool Difficulty và Scarcity Multiplier để tổng nguồn cung Gem NFT được khai thác dần trong thời gian dài.

Trong mô hình tham chiếu ban đầu của Garnet Pool, nếu Pool Difficulty và Scarcity Multiplier đều là 1x và Protocol Reference Power là 100,000 Power, thời gian claim dự kiến có thể được hiểu như sau.

| Active Stake | Thời gian claim dự kiến cho 1 Garnet NFT |
| ------------ | ---------------------------------------- |
| 1,000 STONX | Khoảng 197 ngày |
| 4,800 STONX | Khoảng 41 ngày |
| 6,000 STONX | Khoảng 32.8 ngày |
| 100,000 STONX | Khoảng 1.97 ngày |

Cấu trúc này cho phép người tham gia cơ bản với 1,000 STONX vẫn tích lũy PoM, mang lại trải nghiệm mining theo chu kỳ tháng cho người tham gia quy mô trung bình, và tạo nhiều cơ hội claim hơn cho người có Mining Power cao. Mining Power chỉ ảnh hưởng đến tần suất claim; nó không cho phép người dùng chọn trực tiếp cấp độ hoặc thuộc tính của Gem NFT.

Nhà phát triển xem cấu trúc này là yếu tố rất quan trọng cho việc mở rộng hệ sinh thái CryptoStone. Sự khan hiếm của NFT cần được giữ bằng tổng nguồn cung, xác suất thuộc tính và cấu trúc halving, trong khi khả năng tham gia của người dùng cần được mở rộng bằng rào cản gia nhập thấp và mô hình tích lũy PoM.
