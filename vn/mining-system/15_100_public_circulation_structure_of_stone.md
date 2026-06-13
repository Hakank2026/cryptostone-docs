# 15 Cấu trúc phân bổ STONX

Trong CryptoStone, STONX là tài nguyên khai thác duy nhất dùng để tham gia khai thác đá quý kỹ thuật số. Nhà phát triển cho rằng việc phân phối STONX nên theo cấu trúc thị trường mở có thể tiếp cận dưới các quy tắc minh bạch, thay vì cấu trúc trao quyền phân bổ đặc biệt cho một nhóm nội bộ cụ thể.

Theo đó, STONX được thiết kế như một mô hình phân bổ hướng ra thị trường, không có team allocation, founder reserve hay hidden insider allocation. Tổng nguồn cung được phân bổ cho DEX liquidity, direct sale, strategic ecosystem partners và listing hoặc liquidity preparation.

| Hạng mục | Cấu trúc |
| -------- | -------- |
| Total Supply | 1,200,000,000 STONX |
| Team Allocation | None |
| Founder Reserve | None |
| Hidden Insider Allocation | None |
| Additional Mint | None |
| Primary Utility | Tham gia mining pool để khai thác Gem NFT |
| Mechanism | Acquire STONX -> Stake -> Generate Mining Power -> Accumulate PoM -> Claim Gem NFT |
| Supply Trust | Nguồn cung, cấu trúc pool, bảng xác suất và điều kiện claim có thể kiểm chứng qua contract và dữ liệu công khai |

## 15.1 Allocation

| Allocation | Ratio | TGE Unlock | Lock / Vesting | Rationale |
| ---------- | ----: | ---------- | -------------- | --------- |
| DEX Liquidity Reserve | 50% | Cung cấp theo từng giai đoạn trong phạm vi cần thiết cho thanh khoản ban đầu | LP lock hoặc burn dài hạn; phần còn lại dùng dần cho mở rộng thanh khoản | Bảo đảm lối vào on-chain công khai lớn nhất |
| Direct Sale Pool | 20% | Bán công khai trong giới hạn sale contract | Lượng chưa bán vẫn nằm trong pool và được giải phóng dần | Tạo lối lấy STONX trực tiếp để tham gia mining |
| Strategic / VC Allocation | 10% | 0% hoặc mở khóa ban đầu giới hạn | 6-month cliff + 24-month linear vesting | Dành cho sàn giao dịch, hạ tầng và đối tác chiến lược hệ sinh thái |
| Listing / Liquidity Reserve | 20% | Chỉ dùng khi cần cho listing preparation và market making | Quản lý ví công khai, dùng đúng mục đích, thực hiện theo giai đoạn | Hỗ trợ thanh khoản sàn tập trung, chiến dịch và ổn định thị trường |

DEX Liquidity Reserve nhận tỷ trọng lớn nhất vì STONX cần được tiếp cận chủ yếu qua thị trường công khai. Direct Sale Pool giúp người dùng mới có thể lấy STONX cần thiết cho mining mà không phải đi qua quy trình giao dịch phức tạp. Strategic / VC Allocation được giới hạn cho đối tác mở rộng hệ sinh thái, và vesting dài hạn giúp giảm áp lực bán ngắn hạn. Listing / Liquidity Reserve là quỹ dự trữ có mục đích rõ ràng cho listing, market making, chiến dịch và ổn định thị trường.

Người dùng có thể lấy STONX qua thị trường công khai hoặc direct sale rồi gửi vào stone mining pool họ chọn. Sau đó họ tạo Mining Power từ STONX đã stake và tích lũy Proof of Mining, PoM, theo thời gian. Khi PoM tích lũy đạt ngưỡng cần thiết của pool tương ứng, người dùng có thể claim Gem NFT.

Trong cấu trúc này, DEX và Direct Sale là lối vào công khai để lấy STONX, còn mining pool là use case thực sự của STONX. Nói cách khác, STONX không chỉ được thiết kế để nắm giữ hoặc lưu thông đầu cơ; nó hoạt động như một tài nguyên giao thức để tham gia khai thác đá quý kỹ thuật số.

Để cấu trúc phân bổ mở này có được niềm tin, phương thức cung cấp thanh khoản ban đầu, cách xử lý LP, quyền contract, tính không thể phát hành thêm và các ví dự trữ chính cần được công bố rõ ràng. LP token ban đầu nên được lock dài hạn hoặc burn. Điều này giảm lo ngại về rút thanh khoản và củng cố niềm tin vào mô hình tiếp cận thị trường mở của STONX.

Niềm tin của CryptoStone không hình thành từ phân bổ đặc quyền cho một bên cụ thể, mà từ tổng nguồn cung cố định, không có team allocation, quy tắc mining bất biến, cấu trúc PoM có thể kiểm chứng và minh bạch on-chain.
