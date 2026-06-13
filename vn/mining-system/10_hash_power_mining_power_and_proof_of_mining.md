# 10 Hash Power, Mining Power và Proof of Mining

Trong Bitcoin, miner có xác suất tạo block thông qua hash power. Hash power càng cao thì khả năng tìm được block càng lớn. Tuy nhiên, hash power không thể tùy ý thay đổi quy tắc phát hành hay cấu trúc độ khó của Bitcoin. Nói cách khác, hash power không phải quyền lực để thay đổi quy tắc mạng lưới, mà là tài nguyên tính toán để có thêm cơ hội khai thác trong các quy tắc cố định.

CryptoStone trừu tượng hóa khái niệm này thành cấu trúc khai thác đá quý kỹ thuật số. Trong CryptoStone, khái niệm tương ứng với hash power là **Mining Power**, và khối lượng công việc tích lũy theo thời gian bởi Mining Power là **Proof of Mining**, hay **PoM**.

| Bitcoin | CryptoStone |
| ------- | ----------- |
| Hash Power | Mining Power |
| Proof of Work | Proof of Mining, PoM |
| ASIC / Mining Equipment | STONX đã stake |
| Block Reward | Gem NFT |
| Network Difficulty | Pool Difficulty |
| Halving | Scarcity Multiplier |
| BTC Issuance | Gem NFT Issuance |
| Miner | STONX Staker / Gem Miner |

PoM không phải token có thể chuyển nhượng hoặc giao dịch riêng. PoM là chỉ số khối lượng công việc on-chain được contract ghi nhận dựa trên mức tham gia khai thác và thời gian trôi qua của người dùng. PoM cũng không phải thuật toán đồng thuận mạng lưới. Trong CryptoStone, PoM là giá trị nội bộ của giao thức dùng để xác định liệu người dùng đã đạt điều kiện claim Gem NFT từ một stone pool cụ thể hay chưa.

Khi người dùng (i) stake lượng STONX ((s\_{i,j})) vào stone pool ((j)), và lock-up multiplier là ((L\_i)), Mining Power của người dùng ((P\_{i,j})) được định nghĩa như sau.

$$
P_{i,j} = s_{i,j} \times L_i
$$

Giá trị PoM của người dùng tích lũy theo thời gian như sau.

$$
PoM_{i,j}(t + \Delta t) = PoM_{i,j}(t) + P_{i,j} \times \Delta t
$$

Ở đây, (PoM\_{i,j}(t)) là giá trị Proof of Mining mà người dùng ((i)) đã tích lũy trong stone pool ((j)) cho đến thời điểm ((t)).

PoM tích lũy độc lập theo từng stone pool. Ví dụ, PoM tích lũy trong Diamond Pool chỉ có thể dùng để claim Diamond NFT, không thể chuyển thành PoM của Ruby Pool hoặc Sapphire Pool. Cấu trúc này bảo vệ tính độc lập, sự khan hiếm và độ khó khai thác của từng stone pool.

Người dùng có Mining Power cao hơn có thể đạt ngưỡng PoM cần thiết nhanh hơn, nhưng không thể tùy ý tăng xác suất nhận đá quý hiếm hơn hoặc chọn một cấp độ đá cụ thể.
