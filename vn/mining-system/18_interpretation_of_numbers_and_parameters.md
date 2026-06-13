# 18 Diễn giải các con số và tham số

Nguồn cung theo từng stone, Base Mining Interval, công thức Mining Power, ngưỡng PoM, hệ số halving, bảng xác suất Weight·Color·Clarity·Cut và công thức Rarity Score trong whitepaper này không phải tiêu chuẩn tuyệt đối tái hiện hoàn hảo hệ sinh thái đá quý thật.

Các con số này là tham số tham chiếu ban đầu được thiết kế cho các mục đích sau.

| Mục đích | Mô tả |
| -------- | ----- |
| Biểu đạt khan hiếm số | Biểu đạt sự khan hiếm của đá quý trong môi trường on-chain |
| Triển khai độ khó khai thác | Triển khai độ khó khai thác và giới hạn nguồn cung bằng smart contract |
| Phân biệt khan hiếm tương đối | Thiết kế khác biệt khan hiếm so sánh giữa các Stone Type |
| Phân biệt giá trị sưu tầm | Tăng khả năng hiểu giá trị sưu tầm qua rarity và tier |
| Kiểm soát nguồn cung dài hạn | Quản lý tốc độ cung thông qua halving và tăng độ khó |
| Khả năng mở rộng tham gia | Hỗ trợ cả người tham gia nhỏ và người tham gia quy mô lớn |

Vì vậy, các giá trị trong whitepaper này không thể được xem là phản ánh hoàn hảo mọi yếu tố hình thành giá, tiêu chuẩn thẩm định, cấu trúc phân phối, cung cầu, giá trị văn hóa, chi phí lưu trữ vật lý hoặc mô hình đánh giá của tổ chức thẩm định trong thị trường đá quý thật.

CryptoStone không tìm cách sao chép nguyên trạng thị trường đá quý thật. Đây là dự án nhằm triển khai các đặc tính cốt lõi của đá quý - khan hiếm, phân hạng, khả năng khai thác và tính sưu tầm - trong một môi trường kỹ thuật số phi tập trung.

Nhà phát triển xem các giá trị trong whitepaper này không phải là con số tùy ý, mà là giá trị tham chiếu ban đầu để giải thích và thử nghiệm khái niệm đá quý kỹ thuật số phi tập trung. Chúng có thể phát triển thành mô hình tinh chỉnh hơn thông qua nghiên cứu tương lai, phản ứng thị trường, đánh giá cộng đồng, kiểm chứng kỹ thuật và rà soát pháp lý. Tuy nhiên, sau khi giao thức được triển khai chính thức và các quy tắc cốt lõi được finalized, các giá trị cốt lõi đã xác định trước không được nhà vận hành thay đổi tùy ý.
