# 38 Nguyên tắc cố định giao thức

Để CryptoStone hướng tới đặc tính tài sản phi tập trung tương tự Bitcoin, các quy tắc cốt lõi không được thay đổi tùy ý sau khi triển khai.

| Fixed Item | Description |
| ---------- | ----------- |
| Total STONX supply | 1,200,000,000 STONX |
| STONX circulation structure | Open Market Allocation |
| Max Supply by stone | Số lượng phát hành NFT tối đa theo từng stone |
| Base Mining Interval by stone | Chu kỳ mining cơ bản |
| Target Pool Power | Giá trị tham chiếu ban đầu 40,000,000 Power |
| Base Mining Unit | 1,000 STONX |
| Weight probability table | Xác suất sinh Weight |
| Color probability table | Xác suất sinh Color grade |
| Clarity probability table | Xác suất sinh Clarity grade |
| Cut probability table | Xác suất sinh Cut grade |
| Scarcity Multiplier | Hệ số độ khó dựa trên halving |
| Claim Burn formula | Công thức burn khi claim |
| Mining Power formula | Công thức Mining Power dựa trên staking |
| PoM formula | Tích lũy Proof of Mining và điều kiện claim |
| Lock Multiplier | Hệ số mining theo thời gian lock-up |
| Maturity Burn formula | Công thức burn khấu hao khi lock-up đáo hạn |

Sau khi thiết lập ban đầu hoàn tất, giao thức cần được finalized. Sau thời điểm đó, nhà vận hành không được tùy ý tăng nguồn cung, thay đổi xác suất rarity hoặc phát hành thủ công NFT cho người dùng cụ thể.

Các contract cốt lõi của CryptoStone cần được công khai và xác minh source code sau khi triển khai; nguồn cung token, nguồn cung NFT, bảng xác suất, công thức mining và cấu trúc tính ngưỡng PoM không được thay đổi sau finalization.

Nếu trước finalization cần có chức năng quản trị giới hạn, danh sách, mục đích, thời điểm gỡ bỏ và phương thức kiểm soát của các chức năng đó phải được công bố rõ ràng. Sau finalization, quyền quản trị liên quan đến số lượng phát hành cốt lõi, bảng xác suất, quyền phát hành và phương thức tính PoM cần được gỡ bỏ hoặc vô hiệu hóa.

Phi tập trung không hoàn tất chỉ vì một hệ thống được triển khai trên blockchain. Phi tập trung được hình thành từ các quy tắc mà nhà vận hành không thể thay đổi, mã nguồn mà bất kỳ ai cũng có thể kiểm chứng, và cấu trúc mà bất kỳ ai cũng có thể tham gia.
