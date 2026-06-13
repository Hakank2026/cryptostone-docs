# 23 Điều chỉnh Pool Difficulty

Nếu số người tham gia tăng và tổng Mining Power lớn lên, đá quý có thể được khai thác quá nhanh. Để ngăn điều này, mỗi pool điều chỉnh độ khó dựa trên tổng Mining Power.

Nếu tổng Mining Power của stone pool (j) là (P\_j), Target Pool Power là (P\_j^\*), và Pool Difficulty là (D\_j), thì được tính như sau:

$$
D_j = \max(1, P_j \div P_j^*)
$$

Giá trị tham chiếu của CryptoStone như sau:

$$
P_j^* = 40,000,000 \text{ Power}
$$

Ví dụ:

| Target Pool Power | Total Pool Mining Power | Calculation | Pool Difficulty |
| ----------------- | ----------------------: | ----------- | --------------: |
| 40,000,000 | 20,000,000 | 20,000,000 ÷ 40,000,000 = 0.5 → max(1, 0.5) | 1.0x |
| 40,000,000 | 40,000,000 | 40,000,000 ÷ 40,000,000 = 1.0 | 1.0x |
| 40,000,000 | 80,000,000 | 80,000,000 ÷ 40,000,000 = 2.0 | 2.0x |
| 40,000,000 | 200,000,000 | 200,000,000 ÷ 40,000,000 = 5.0 | 5.0x |

Lý do áp dụng cấu trúc `max(1, ·)` là để độ khó không giảm xuống dưới 1.0x ngay cả khi tổng Mining Power thấp hơn Target Pool Power. Nói cách khác, nó ngăn tốc độ mining trở nên nhanh quá mức so với tốc độ tham chiếu trong giai đoạn đầu khi mức tham gia còn thấp.

Ngược lại, khi tổng Mining Power vượt Target Pool Power, Pool Difficulty tăng tỷ lệ thuận. Ví dụ, nếu tổng Mining Power của một pool tăng lên 80,000,000 Power, Pool Difficulty trở thành 2.0x. Khi đó, thời gian cần để cùng một người dùng khai thác một NFT cũng xấp xỉ tăng gấp đôi.

Trong triển khai smart contract, BPS có thể được dùng để tránh phép tính thập phân.

$$
D_{j,\mathrm{BPS}} = \max(10,000, P_j \times 10,000 \div P_j^*)
$$

Ở đây, 10,000 BPS = 1.0x.

Cấu trúc này cho phép tốc độ mining toàn cục điều chỉnh tự nhiên khi mức tham gia tăng, đồng thời ngăn nguồn cung của từng stone bị khai thác cạn quá nhanh.
