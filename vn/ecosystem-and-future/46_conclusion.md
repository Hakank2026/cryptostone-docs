# 46 Kết luận

CryptoStone là giao thức triển khai khái niệm đá quý kỹ thuật số trên smart contract.

Giao thức định nghĩa STONX là tài nguyên mining và Gem NFT là kết quả mining, kết nối hai yếu tố này thông qua Proof of Mining, hay PoM. Người dùng gửi STONX vào mining pool, tích lũy Mining Power và PoM theo thời gian, rồi claim Gem NFT khi đạt ngưỡng cần thiết.

## Cấu trúc cốt lõi

| Hạng mục | Cấu trúc |
| -------- | -------- |
| Mining Resource | STONX |
| Initial Supply | 1,200,000,000 STONX |
| Mining Result | CryptoStone Gem NFT |
| Stone Types | 12 pool dựa trên birthstone |
| Attribute Generation | Weight, Color, Clarity, Cut, Rarity |
| Metadata | HTTPS metadata API + watcher finalization + IPFS media |
| Rarity Standard | Rarity Score + Probability Rarity Index |

## Cấu trúc thực thi giao thức

| Giai đoạn | Mô tả |
| --------- | ----- |
| Participation | Vào mining pool từ 1,000 STONX |
| Mining Power | Tính từ lượng stake, thời gian lock-up và tham số pool |
| PoM | Giá trị công việc mining tích lũy theo thời gian |
| Claim | Claim Gem NFT sau khi đạt ngưỡng PoM cần thiết |
| Claim Burn | 2 STONX x Scarcity Multiplier |
| Maturity Burn | Burn khấu hao dựa trên thời gian lock-up |
| Randomness | User entropy, recent multi-block entropy, `prevrandao`, claim state và giá trị riêng của contract |
| Finalization | Thuộc tính cốt lõi cố định khi claim; media được watcher cập nhật sau |
| Open Verification | Source code, audit reports, hồ sơ xử lý LP và bảng xác suất |

Mục đích của CryptoStone không phải kết nối NFT với quyền sở hữu đá quý thật. Nó tái diễn giải cấu trúc của đá quý thành mô hình tài sản digital-native: độ khó mining, sự khan hiếm, thuộc tính riêng và giá trị sưu tầm.

Whitepaper này không tuyên bố CryptoStone là một phát hiện vĩ đại hay một phát minh hoàn toàn mới. Đây là một thay đổi góc nhìn và một thử nghiệm mới. Nếu thuộc tính, sự khan hiếm và tính sưu tầm của đá quý được thị trường chấp nhận như một hệ giá trị có ý nghĩa, CryptoStone có thể phát triển thành một danh mục đá quý kỹ thuật số mới.

CryptoStone cần tiếp tục phát triển với contract minh bạch, randomness có thể kiểm chứng, dữ liệu nguồn cung công khai, cấu trúc metadata an toàn và các công cụ hướng tới người dùng giúp hệ thống dễ hiểu và dễ kiểm chứng hơn.
