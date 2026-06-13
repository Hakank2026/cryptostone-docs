# 30 Sinh thuộc tính và Randomness

Thuộc tính đá quý không được nhập thủ công bởi nhà vận hành. Tại thời điểm mining, mining contract xác định Weight, Color, Clarity và Cut dựa trên một giá trị ngẫu nhiên.

Điểm quan trọng là phương thức tạo randomness phải có thể kiểm chứng. Nếu nhà vận hành có thể tùy ý tạo NFT cấp cao, tính phi tập trung và sự khan hiếm của CryptoStone sẽ bị tổn hại.

CryptoStone giảm phụ thuộc vào một yếu tố randomness duy nhất bằng cách kết hợp entropy do người dùng cung cấp, entropy từ nhiều block gần đây, `prevrandao` của Ethereum, trạng thái claim và các giá trị riêng của contract.

Cấu trúc có thể được biểu diễn như sau.

$$
S = H(userEntropy, user, positionId, claimNonce, prevrandao, chainId, contract)
$$

$$
B_i = blockhash(blockNumber - 1 - (H(S,i) \bmod 30)) \quad \text{for } i \in \{0..4\}
$$

$$
R = H(userEntropy, B_0, B_1, B_2, B_3, B_4, prevrandao, claimState, contractState)
$$

Mô hình này không phụ thuộc vào một giá trị block duy nhất hoặc một giá trị người dùng duy nhất. Nó trộn entropy người dùng, nhiều tham chiếu block gần đây, entropy đồng thuận Ethereum và trạng thái claim cụ thể để giảm kết quả có thể dự đoán hoặc phụ thuộc vào nhà vận hành.

Phương thức tạo randomness của CryptoStone tuân theo các nguyên tắc sau.

| Nguyên tắc | Mô tả |
| ---------- | ----- |
| Unpredictability | Nhà vận hành và người dùng không được biết trước kết quả |
| No result selection | Nhà vận hành không được chọn kết quả có lợi hoặc từ chối kết quả bất lợi |
| Prevention of retry | Sau khi yêu cầu randomness, người dùng không được hủy hoặc thử lại trước khi kết quả được finalized |
| No Admin Reroll | Nhà vận hành không được reroll hoặc thay thế một kết quả cụ thể |
| Public verification | Quá trình tạo kết quả phải ở on-chain hoặc có thể kiểm chứng công khai |
| Fixed probability table | Bảng xác suất thuộc tính phải được công bố trước triển khai và không thể thay đổi sau finalization |
| Immutability after issuance | Thuộc tính không được thay đổi sau khi phát hành |

Sau khi yêu cầu kết quả ngẫu nhiên, người dùng không được hủy hoặc retry claim chỉ vì kết quả bất lợi. Nhà vận hành cũng không được phân bổ kết quả có lợi cho người dùng cụ thể hoặc chọn seed tạo ra tổ hợp thuộc tính mong muốn. Đây là điều kiện cốt lõi để bảo đảm đá quý hiếm được tạo bởi cấu trúc randomness có thể kiểm chứng, không phải bởi quyết định của nhà vận hành.

Sau khi phát hành, thuộc tính cốt lõi của Gem NFT phải được đóng băng. Metadata cốt lõi như Weight, Color, Clarity, Cut, stoneType, minedAt và minedFromPool không được nhà vận hành thay đổi.
