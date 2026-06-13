# 26 Thuộc tính Weight

Weight sử dụng CT, tức carat, làm đơn vị chung cho tất cả stone. Giá trị trọng lượng của mỗi viên đá được tạo ngẫu nhiên.

* Minimum Weight = 0.10 CT
* Maximum Weight = 200.00 CT
* Storage Unit = 0.01 CT

Smart contract không lưu trực tiếp số thập phân. Thay vào đó, giá trị được lưu dưới dạng số nguyên theo đơn vị 0.01 CT.

| Displayed Weight | Contract Stored Value |
| ---------------- | --------------------- |
| 0.10 CT | 10 |
| 1.25 CT | 125 |
| 10.50 CT | 1050 |
| 200.00 CT | 20000 |

Weight không được tạo với xác suất bằng nhau. Giống như đá quý có carat lớn ngoài đời thực hiếm hơn, trọng lượng lớn trong CryptoStone được tạo với xác suất thấp hơn.

| Weight Range | Probability | Score |
| ------------ | ----------- | ----: |
| 0.10 ~ 1.99 CT | 75.00% | 0 |
| 2.00 ~ 4.99 CT | 15.00% | 5 |
| 5.00 ~ 9.99 CT | 6.00% | 10 |
| 10.00 ~ 49.99 CT | 3.50% | 16 |
| 50.00 ~ 200.00 CT | 0.50% | 20 |

Score trong bảng không phải tier cuối cùng trực tiếp của Gem NFT. Đây là điểm thuộc tính Weight dùng để tính Rarity Score và Probability Rarity Index. Tier cuối cùng của Gem NFT được xác định bằng cách kết hợp Pool Supply Score, Weight, Color, Clarity và Cut trong hệ thống năm cấp: Common, Rare, Epic, Legendary và Genesis.
