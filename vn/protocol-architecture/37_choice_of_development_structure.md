# 37 Cấu trúc phát triển

CryptoStone áp dụng cấu trúc sau.

* STONX Token
* CryptoStone Gem NFT
* 12 Mining Pool Contracts
* Pool Factory

Cấu trúc này được thiết kế để triển khai giao thức đá quý kỹ thuật số không phụ thuộc vĩnh viễn vào một chain cụ thể. Ở giai đoạn đầu, một mạng smart contract tương thích EVM được dùng làm Launch Network.

## Current Deployment Status

Bảng sau tóm tắt trạng thái triển khai testnet hiện tại và baseline của tài liệu giao thức. Nếu triển khai mainnet hoặc nâng cấp contract, địa chỉ và phiên bản sẽ được cập nhật trong tài liệu công khai riêng.

| Item | Current Status | Notes |
| ---- | -------------- | ----- |
| Launch Network | Ethereum Sepolia | Baseline vận hành testnet |
| STONX Token | `0xBd10DA40Dec511c11100dd2927dDf8c53A5248Ed` | Triển khai ERC-20 testnet |
| GEMS NFT | `0x01CE9e3Ee0fb51B6b0cE1E5B3C72A5F981A50056` | Cấu trúc HTTPS metadata V5.3 |
| Garnet Mining Pool | `0xd885D9865A1e7C9094EcD0982421bE9670Fabe16` | Pool đang live hiện tại |
| Other 11 Mining Pools | Preparing | Mục tiêu mở mainnet hoặc mở tuần tự |
| Refinery | `0xB7b55068163d6d8E4f8eD2e8B511e234520576DC` | Tính năng refinement testnet |
| Marketplace | `0x673d64550c718A3770064ee3cDdC8b20093D0913` | Tính năng giao dịch NFT testnet |
| Metadata Model | HTTPS API + watcher finalization + IPFS media | Tách thuộc tính cốt lõi khỏi lớp hiển thị media |
| Randomness Standard | User entropy + multi-block entropy + `prevrandao` | Baseline cho pool mới và upgrade |
| Mainnet Status | Preparing | Tiến hành sau khi hoàn tất security review, đồng bộ tài liệu và chính sách thanh khoản |

## Rationale

| Choice | Reason |
| ------ | ------ |
| STONX Token | Cung cấp tài nguyên mining và cấu trúc thanh khoản thống nhất |
| CryptoStone Gem NFT | Biểu đạt tính độc nhất và thuộc tính của từng viên đá |
| 12 Mining Pools | Triển khai mỏ kỹ thuật số độc lập cho từng stone |
| Pool Factory | Triển khai pool từ cùng một template có thể kiểm chứng |
| Unified NFT Contract | Tập trung nhận diện collection và dữ liệu giao dịch |
| Verifiable Randomness | Cho phép sinh thuộc tính mà không bị nhà vận hành thao túng |
| Finalize Mechanism | Ngăn thay đổi quy tắc cốt lõi |

Thứ nhất, vai trò của STONX và Gem NFT được tách biệt. STONX là token cho Mining Power, còn Gem NFT là kết quả khai thác.

Thứ hai, tính độc nhất của đá quý được bảo vệ. Mỗi Gem NFT có tokenId và tổ hợp thuộc tính riêng, và thuộc tính của nó không thể thay đổi sau khi mint.

Thứ ba, tính độc lập giữa các stone được duy trì. Mỗi mining pool có nguồn cung, chu kỳ mining và cấu trúc halving riêng, phù hợp để biểu đạt các mỏ riêng lẻ ngoài đời thực dưới dạng kỹ thuật số.

Thứ tư, NFT collection vẫn thống nhất. Điều này tập trung thương hiệu và dữ liệu thị trường của CryptoStone, giúp quản lý thống nhất giao dịch và xếp hạng rarity.

Thứ năm, cấu trúc có khả năng mở rộng cao trong tương lai. CryptoStone có thể bắt đầu trên Launch Network tương thích EVM và sau này mở rộng sang Appchain hoặc CryptoStone Mainnet độc lập.

Thứ sáu, phụ thuộc tập trung được giảm bớt. Mining và minting được thực thi bởi contract thay vì server, và bất kỳ ai cũng có thể kiểm chứng điều kiện.
