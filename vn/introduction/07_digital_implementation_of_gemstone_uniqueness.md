# 07 Triển khai tính độc nhất của đá quý trong môi trường số

CryptoStone có thể cân nhắc nhiều lựa chọn kỹ thuật để biểu đạt tính độc nhất của mỗi viên đá. Cấu trúc fungible token, semi-fungible token hoặc composite token đều có thể khả thi, nhưng mục tiêu cốt lõi của CryptoStone là để mỗi viên đá có một tổ hợp thuộc tính và tokenId riêng.

Vì vậy, đá quý trong CryptoStone được biểu đạt dưới dạng Gem NFT có tokenId và tổ hợp thuộc tính độc nhất. Lựa chọn này không nhằm nhấn mạnh một tiêu chuẩn kỹ thuật cụ thể, mà là kết quả của việc triển khai các chức năng sau.

| Yêu cầu triển khai | Lý do áp dụng cấu trúc NFT |
| ------------------ | -------------------------- |
| Cần tokenId độc nhất cho từng viên đá | Cấu trúc NFT phù hợp để biểu đạt tài sản dựa trên tokenId độc nhất. |
| Lưu trữ thuộc tính khác nhau cho từng viên đá | Có thể triển khai metadata theo tokenId và cấu trúc thuộc tính on-chain. |
| Cần hồ sơ chuyển quyền sở hữu | Có thể ghi nhận chuyển nhượng và sở hữu theo chuẩn NFT. |
| Biểu đạt nhiều loại đá trong một collection | 12 loại đá có thể được phân biệt bằng thuộc tính `stoneType`. |
| Theo dõi độ hiếm và lịch sử giao dịch | Có thể theo dõi provenance và rarity của từng NFT. |

Nói cách khác, cấu trúc Gem NFT trong CryptoStone không phải phương tiện để tạo image NFT. Nó là một container kỹ thuật để biểu đạt tính độc nhất và bản chất tài sản dựa trên thuộc tính của đá quý kỹ thuật số.
