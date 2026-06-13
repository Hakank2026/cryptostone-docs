# 39 Cân bằng giữa phản ứng bảo mật và phi tập trung

CryptoStone lấy No Admin Mint và No Central Server làm nguyên tắc cốt lõi. Tuy nhiên, trong giai đoạn phát triển và triển khai ban đầu, một cấu trúc quản trị giới hạn có thể cần thiết cho security audit, testing và phản ứng lỗ hổng.

| Giai đoạn | Cấu trúc quản lý |
| --------- | ---------------- |
| Testnet và audit stage | Có thể tồn tại quyền quản trị giới hạn |
| Trước official deployment | Xác minh tham số và kiểm tra bảo mật |
| Sau official launch | Gỡ bỏ quyền thay đổi phát hành, nguồn cung và xác suất cốt lõi |
| Sau finalization | No Admin Mint, No Supply Change, No Probability Change |

Nếu có chức năng emergency pause, chức năng đó chỉ được dùng giới hạn để ngăn sự cố bảo mật, không được dùng để thao túng kết quả phát hành hoặc thay đổi nguồn cung. Chức năng khẩn cấp cũng nên bị ràng buộc bằng các phương thức có thể kiểm chứng công khai như timelock hoặc multisignature, và không được trở thành công cụ để nhà vận hành tùy ý thay đổi rarity hoặc số lượng phát hành.

Các contract chính của CryptoStone gồm token contract, Gem NFT contract, Mining Pool Template, Pool Factory và cấu trúc tạo randomness. Các contract này nên trải qua security audit trước và sau khi triển khai, đồng thời kết quả audit và hồ sơ phản ứng lỗ hổng lớn nên được công bố.

Các yếu tố kiểm chứng chính cần công bố như sau.

| Verification Item | Description |
| ----------------- | ----------- |
| Contract Source Verification | Công bố và xác minh source code contract đã triển khai |
| Audit Report | Báo cáo audit cho contract chính và cấu trúc randomness |
| Admin Function List | Sự tồn tại của chức năng quản trị và kế hoạch gỡ bỏ |
| Finalize Event | Thời điểm finalization tham số cốt lõi và event record |
| LP Lock / Burn Proof | Hồ sơ xử lý LP liên quan đến thanh khoản ban đầu |
| Probability Table Hash | Xác minh bảng xác suất khớp với giá trị công bố trước triển khai |
| Metadata Freeze | Thuộc tính cốt lõi có bất biến sau phát hành hay không |

Cấu trúc này nhằm cân bằng giữa phản ứng bảo mật thực tế và đặc tính tài sản phi tập trung.
