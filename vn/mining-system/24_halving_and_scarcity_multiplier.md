# 24 Halving và Scarcity Multiplier

Cấu trúc halving của CryptoStone được áp dụng độc lập cho từng stone, không áp dụng theo toàn bộ collection.

Nếu nguồn cung tối đa của stone (j) là (N\_j), số lượng đã khai thác là (n\_j), và tỷ lệ tiến độ khai thác là (q\_j), thì được tính như sau:

$$
q_j = n_j \div N_j
$$

Ví dụ, nếu nguồn cung tối đa của Diamond là 110,000 và đã khai thác 55,000:

$$
q_{\text{Diamond}} = 55,000 \div 110,000 = 0.5
$$

Điều này có nghĩa Diamond Pool đã đạt giai đoạn khai thác 50%.

Scarcity Multiplier (S\_j) của từng stone tăng theo tỷ lệ tiến độ khai thác (q\_j).

| Mined Supply Ratio | Remaining Supply | Scarcity Multiplier |
| ------------------ | ---------------- | ------------------- |
| 0% \~ 50% | 100% \~ 50% | 1x |
| 50% \~ 75% | 50% \~ 25% | 2x |
| 75% \~ 87.5% | 25% \~ 12.5% | 4x |
| 87.5% \~ 93.75% | 12.5% \~ 6.25% | 8x |
| 93.75% \~ 96.875% | 6.25% \~ 3.125% | 16x |
| 96.875% or more | 3.125% or less | 32x |

Có thể tổng quát hóa như sau:

$$
S_j(q_j) = 2^{\min\left(5, \lfloor \log_2 \left( 1 \div (1 - q_j) \right) \rfloor \right)}
$$

Tuy nhiên, khi (q\_j) thuộc vùng ban đầu, (S\_j(q\_j)) được giữ tối thiểu ở 1x. Trong triển khai smart contract thực tế, thay vì tính trực tiếp công thức trên, có thể triển khai dựa trên bảng khoảng giá trị đã công bố trước.

Công thức này biểu đạt cấu trúc trong đó độ khó mining tăng theo cấp số nhân khi nguồn cung còn lại của từng stone giảm xuống. Nó đưa cấu trúc ngoài đời thực, nơi chi phí và độ khó khai thác tăng khi trữ lượng mỏ giảm, vào môi trường kỹ thuật số.
