# 22 Ngưỡng PoM cần thiết

Ngưỡng PoM cần thiết để khai thác một viên đá được quyết định bởi Protocol Reference Power, Base Mining Interval của từng stone, Pool Difficulty và Scarcity Multiplier.

Nếu Base Mining Interval của stone (j) là (T\_j), Protocol Reference Power là (M\_{ref}), Pool Difficulty là (D\_j), và Scarcity Multiplier là (S\_j), thì ngưỡng PoM cần thiết (R\_j) được định nghĩa như sau:

$$
R_j = M_{ref} \times T_j \times D_j \times S_j
$$

Các giá trị tham chiếu của CryptoStone như sau:

* Base Mining Unit = 1,000 STONX
* Protocol Reference Power = 100,000 Power
* Target Pool Power = 40,000,000 Power

Base Mining Unit là đơn vị tham gia tối thiểu, còn Protocol Reference Power là power tham chiếu dùng để hiệu chỉnh tốc độ mining. Bằng cách tách hai giá trị này, CryptoStone có thể duy trì cả đơn vị tham gia dễ tiếp cận và khả năng kiểm soát nguồn cung dài hạn.

Ví dụ, nếu Base Mining Interval của Garnet Pool là 170,000 giây và Pool Difficulty cùng Scarcity Multiplier đều là 1x, phép tính như sau:

$$
R_{\text{Garnet}} = 100{,}000 \times 170{,}000 \times 1 \times 1
$$

$$
R_{\text{Garnet}} = 17{,}000{,}000{,}000 \text{ PoM}
$$

Khi Mining Power của người dùng (i) là (P\_{i,j}), thời gian dự kiến để người dùng đó claim một NFT của stone (j) có thể được biểu diễn như sau:

$$
E[T_{i,j}] = R_j \div P_{i,j}
$$

Ví dụ, khi người dùng stake 6,000 STONX vào Garnet Pool theo điều kiện Flexible:

$$
E[T_{i,\text{Garnet}}] = 17{,}000{,}000{,}000 \div 6{,}000
$$

$$
= 2{,}833{,}333 \text{ giây}
$$

$$
\approx 32.8 \text{ ngày}
$$

Nói cách khác, trong điều kiện ban đầu, người dùng stake 6,000 STONX có thể claim khoảng một Garnet NFT trong vòng xấp xỉ một tháng. Người dùng stake ít hơn sẽ tích lũy PoM chậm hơn, còn người dùng stake nhiều hơn sẽ đạt điều kiện claim nhanh hơn.
