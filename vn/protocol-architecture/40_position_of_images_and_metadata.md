# 40 Cấu trúc Metadata

Bản chất của CryptoStone Gem NFT không phải chính hình ảnh, mà là dữ liệu thuộc tính biểu đạt viên đá.

| Attribute | Example |
| --------- | ------- |
| `stoneType` | Garnet, Ruby, Sapphire |
| `weight` | 3.42 CT |
| `color` | D, E, F, G và các cấp khác |
| `clarity` | FL, IF, VVS1 và các cấp khác |
| `cut` | 1 Star ~ 6 Star |
| `rarity` | Một trong Common, Rare, Epic, Legendary, Genesis |
| `minedAt` | Block hoặc timestamp khai thác |
| `pool` | Địa chỉ mining pool |
| `generation` | Original hoặc refinement generation |

CryptoStone có thể cung cấp metadata cơ sở của NFT thông qua HTTPS metadata API. Điều này cho phép người dùng nhanh chóng thấy name, description, attributes, grade và tokenId trong ví hoặc marketplace ngay sau khi mint.

## 40.1 Metadata Trust Model

CryptoStone tách thuộc tính cốt lõi khỏi lớp hiển thị. Các thuộc tính bản chất của viên đá được quyết định bởi contract và dữ liệu có thể kiểm chứng công khai. HTTPS metadata API cung cấp các thuộc tính đó dưới dạng JSON để ví, marketplace và frontend dễ đọc.

Mô hình tin cậy như sau.

| Layer | Role | Trust Standard |
| ----- | ---- | -------------- |
| Smart Contract | Quyết định minting, ownership, tokenId và thuộc tính cốt lõi | On-chain verification |
| HTTPS Metadata API | Cung cấp name, description, attributes và media URL bằng JSON | Phản hồi công khai và mapping thuộc tính xác định |
| Watcher Finalization | Tạo image/video, upload IPFS media và cập nhật metadata response | Log công khai và mapping theo tokenId |
| IPFS Media | Lưu trữ file image và video | Content-addressed media verification |

Image và video được tạo sau bởi quá trình watcher finalization, upload lên IPFS và phản ánh trong metadata API cùng JSON response. Quá trình này không yêu cầu thêm xác nhận ví từ người dùng. Giao dịch cốt lõi do ví xác nhận nên được giới hạn ở claim hoặc refinement execution.

Điều này có nghĩa CryptoStone Gem NFT có thể giữ cả khả năng kiểm chứng kỹ thuật và biểu đạt trực quan. Viên đá không được định nghĩa chỉ bởi hình ảnh. Hình ảnh là biểu diễn trực quan của thuộc tính on-chain và metadata, còn chính các thuộc tính mới định nghĩa giá trị sưu tầm.

Hình ảnh và video có thể thay đổi định dạng hiển thị khi hệ sinh thái phát triển, nhưng thuộc tính cốt lõi và tokenId nên không thay đổi. Ví dụ, một Garnet Gem NFT với các thuộc tính sau:

* Garnet
* 3.42 CT
* D Color
* IF Clarity
* 5 Star Cut

sẽ giữ cùng danh tính cốt lõi dù được hiển thị dưới dạng hình tĩnh, animation hay mô hình 3D.

Vì vậy, ngay cả khi IPFS upload hoặc media generation bị trễ, thuộc tính cốt lõi của Gem NFT vẫn nên hiển thị trước thông qua contract và HTTPS metadata API. Khi watcher điền dữ liệu image và video IPFS, NFT marketplace và UI ví có thể hiển thị media đã cập nhật.

Thiết kế này ngăn người dùng phải lặp lại xác nhận ví chỉ để finalization metadata. Nó cũng bảo đảm rằng ngay cả khi image server hoặc API tạm thời chậm, thuộc tính cốt lõi của CryptoStone NFT vẫn nằm trong cấu trúc dữ liệu on-chain hoặc có thể kiểm chứng công khai.
