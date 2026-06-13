# 41 Mở rộng hệ sinh thái và Gem Refinement

CryptoStone có thể mở rộng utility của Gem NFT thông qua Marketplace, Arena và Gem Refinement mà không thay thế cấu trúc mining cốt lõi.

Marketplace hỗ trợ price discovery và chuyển quyền sở hữu cho Gem NFT đã khai thác. Người dùng có thể list Gem NFT mà họ đã khai thác hoặc tinh luyện, còn người mua có thể chọn đối tượng sưu tầm dựa trên stone type, grade, Rarity Score, attributes, tokenId, lịch sử giao dịch và trạng thái media. Marketplace không tự bảo đảm rarity; nó là nơi giá thị trường được hình thành dựa trên thuộc tính đã công bố và provenance on-chain.

Arena là module kiểu game mở rộng utility của Gem NFT. Người dùng có thể dùng Gem NFT như entry seed hoặc participation credential và tham gia các bàn Duel, Battle hoặc Arena thông qua entry fee bằng STONX. Arena thêm bối cảnh sử dụng vượt ra ngoài sưu tầm, nhưng không trực tiếp thay đổi xác suất mining hoặc grade của NFT.

Gem Refinement là cấu trúc utility tùy chọn sau mining, cho phép Gem NFT đã khai thác được sử dụng lại. Đây không phải hệ thống phát hành bổ sung không giới hạn. Thay vào đó, hai Gem NFT có cùng `stoneType` được kết hợp để tạo một Refined Gem NFT có cùng `stoneType`, hình thành cơ chế nén nguồn cung.

Cấu trúc refinement cơ bản:

| Input | Output | Supply Change |
| ----- | ------ | ------------- |
| 2 Gem NFT cùng stone | 1 Refined Gem NFT cùng stone | Tổng nguồn cung NFT giảm 1 |

Khi một lần refinement được thực hiện, hai Gem NFT cha bị burn hoặc trở nên không thể khôi phục, và chỉ một Refined Gem NFT mới được tạo. Vì vậy, tổng nguồn cung NFT lưu hành giảm một đơn vị.

Ví dụ:

* Garnet #102 + Garnet #481 -> Refined Garnet #9001
* Ruby #220 + Ruby #841 -> Refined Ruby #9102

Trong mô hình ban đầu, Gem Refinement nên ưu tiên chỉ cho phép refinement cùng stone. Ví dụ, hai Garnet Gem NFT có thể trở thành một Refined Garnet Gem NFT, và hai Ruby Gem NFT có thể trở thành một Refined Ruby Gem NFT. Cross-stone refinement có thể làm cấu trúc nguồn cung, khan hiếm, halving và độ khó mining trở nên quá phức tạp, nên phù hợp để loại khỏi mô hình ban đầu.

Gem Refinement có thể tạo một Gem NFT mới với:

* Rarity Score cao hơn,
* metadata thế hệ refinement,
* hồ sơ parent tokenId,
* hiệu ứng hình ảnh bổ sung,
* và nguồn cung thấp hơn.

Tuy nhiên, refinement không nên được thiết kế để bảo đảm nâng cấp thành công vô điều kiện. Tốt hơn là bao gồm kết quả dựa trên xác suất để supply compression, áp lực sưu tầm và use case cho NFT cấp thấp cùng tồn tại.

Kết quả refinement có thể dựa trên tier cao hơn trong hai Gem NFT cha.

$$
T_{base} = \max(T_1, T_2)
$$

Ở đây, (T\_1) và (T\_2) là tier của hai Gem NFT cha, còn (T\_{base}) là tier tham chiếu để xác định kết quả refinement.

Rarity tier được thống nhất thành năm cấp: Common, Rare, Epic, Legendary và Genesis.

| Tier Index | Tier |
| ---------- | ---- |
| 0 | Common |
| 1 | Rare |
| 2 | Epic |
| 3 | Legendary |
| 4 | Genesis |

Kết quả refinement nên thường xuyên giữ nguyên ở tier cơ sở. Xác suất downgrade nên thấp, và khi upgrade xảy ra, nên giới hạn ở một hoặc hai cấp. NFT tier thấp có thể có xác suất upgrade tương đối cao hơn, trong khi NFT tier cao cần có xác suất upgrade thấp hơn để bảo vệ sự khan hiếm của cấp cao.

Ví dụ mô hình xác suất ban đầu:

| Base Tier | Downgrade | Same Tier | +1 Tier | +2 Tier |
| --------- | --------: | --------: | ------: | ------: |
| Common | None | 68.0% | 27.0% | 5.0% |
| Rare | 1.0% | 76.0% | 20.0% | 3.0% |
| Epic | 1.5% | 88.0% | 10.0% | 0.5% |
| Legendary | 2.0% | 97.0% | 1.0% | None |
| Genesis | Limited | Limited | Limited | Limited |

Genesis được xem là tier sưu tầm cao nhất. Trong mô hình ban đầu, nên giới hạn việc sử dụng Genesis làm vật liệu refinement. Cấu trúc này giữ lại sự hấp dẫn của refinement trong khi ngăn việc tạo quá nhiều NFT cấp cao.

Nếu cho phép refinement giữa các parent tier khác nhau, xác suất kết quả có thể được điều chỉnh dựa trên khoảng cách tier.

$$
\Delta T = |T_1 - T_2|
$$

| Tier Gap | Adjustment Coefficient | Meaning |
| -------- | ---------------------: | ------- |
| 0 | 100% | Refinement cùng tier; áp dụng xác suất cơ sở |
| 1 | 70% | Refinement tier liền kề; xác suất upgrade giảm nhẹ |
| 2 | 40% | Khoảng cách tier lớn; xác suất upgrade giảm đáng kể |
| 3 or more | Limited | Có thể bị giới hạn trong mô hình ban đầu |

Thông qua refinement, Gem NFT cấp thấp không đơn giản bị bỏ lại. Chúng có thể hoạt động như nguyên liệu cho supply compression. Gem NFT cấp cao vẫn khan hiếm, còn NFT cấp thấp có thêm utility làm input refinement. Điều này tạo cho CryptoStone một cấu trúc lưu thông nội bộ cho Gem NFT.
