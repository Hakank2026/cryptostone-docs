# 08 Sự cùng tồn tại của một collection và 12 loại đá

CryptoStone không tách 12 loại đá thành các NFT collection riêng biệt. Tất cả đá quý được phát hành từ một Gem NFT contract duy nhất.

Tuy nhiên, mỗi NFT được phân biệt bằng thuộc tính `stoneType`.

| Token ID | Stone Type | Weight | Color | Clarity | Cut |
| -------- | ---------- | ------ | ----- | ------- | --- |
| #10291 | Diamond | 3.42 CT | D | VVS1 | 6 Star |
| #58102 | Ruby | 8.13 CT | G | VS2 | 4 Star |
| #77410 | Sapphire | 1.25 CT | E | IF | 5 Star |

Cấu trúc này có các lợi thế sau.

| Lợi thế | Mô tả |
| ------- | ----- |
| Collection thống nhất | Duy trì nhận diện một collection duy nhất của CryptoStone. |
| Dữ liệu giao dịch tập trung | Ngăn giá trị collection và dữ liệu giao dịch bị phân mảnh trên nhiều marketplace. |
| Quản lý rarity dễ hơn | Cho phép so sánh tất cả đá quý trong một hệ thống xếp hạng rarity. |
| Bảo toàn cá tính từng stone | Biểu đạt sự độc lập của từng loại đá thông qua thuộc tính `stoneType`. |
| Giới hạn nguồn cung | NFT contract có thể kiểm chứng nguồn cung tối đa theo từng stone. |

NFT contract quản lý riêng số lượng phát hành theo từng stone.

```
maxSupplyByStone[Diamond] = 110,000
mintedByStone[Diamond] < maxSupplyByStone[Diamond]
```

Do đó, ngay cả khi yêu cầu phát hành đến từ Diamond Pool, Diamond NFT cũng không thể được phát hành thêm khi nguồn cung tối đa của Diamond đã đạt giới hạn.
