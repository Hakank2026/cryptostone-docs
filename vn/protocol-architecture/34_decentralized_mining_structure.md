# 34 Cấu trúc khai thác phi tập trung

Trong CryptoStone, mining không được máy chủ thực hiện thay cho người dùng. Người dùng stake STONX vào stone pool họ chọn; khi giá trị PoM đạt ngưỡng cần thiết của pool đó theo thời gian, người dùng trực tiếp gọi một hàm contract như `claimGem()` để nhận Gem NFT.

1. Người dùng nắm giữ STONX.
2. Người dùng chọn một stone pool.
3. Người dùng stake STONX.
4. Mining Power được tạo.
5. PoM tích lũy theo thời gian.
6. Khi PoM đạt ngưỡng cần thiết, người dùng gọi `claimGem()`.
7. Contract kiểm tra điều kiện mining.
8. Thuộc tính được tạo bằng randomness có thể kiểm chứng.
9. Gem NFT được phát hành.
10. NFT được chuyển vào ví người dùng.

Trong quá trình này, không có máy chủ trung tâm phát hành đá quý hoặc gán thuộc tính. Điều kiện và kết quả mining được quyết định bởi code.

Smart contract không tự động thực thi một mình. Tuy nhiên, bất kỳ ai cũng có thể gọi contract, và contract sẽ kiểm chứng rồi thực hiện kết quả theo điều kiện đã xác định trước. Vì vậy, cấu trúc mining của CryptoStone có thể vận hành mà không cần máy chủ trung tâm.

Nhà phát triển cho rằng điểm quan trọng trong cấu trúc này không chỉ là “không có server”, mà là “ngay cả khi không có server, người dùng vẫn có thể trực tiếp gọi contract và nhận kết quả mining theo quy tắc đã định trước.”
