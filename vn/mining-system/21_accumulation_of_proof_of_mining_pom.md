# 21 Tích lũy Proof of Mining, PoM

CryptoStone sử dụng mô hình Proof of Mining, hay PoM, trừu tượng hóa khái niệm Proof-of-Work của Bitcoin vào cấu trúc khai thác đá quý kỹ thuật số, thay vì một hệ thống điểm hoặc credit đơn giản.

PoM là khối lượng công việc khai thác mà người dùng tích lũy theo thời gian khi stake STONX trong một stone pool cụ thể. PoM không phải token có thể chuyển nhượng hoặc giao dịch riêng, mà là chỉ số khối lượng công việc on-chain được contract ghi nhận dựa trên mức tham gia mining và thời gian trôi qua.

Giá trị PoM của người dùng `(i)` đối với stone pool cụ thể `(j)` tích lũy theo thời gian như sau.

$$
PoM_{i,j}(t + \Delta t) = PoM_{i,j}(t) + P_{i,j} \times \Delta t
$$

Ví dụ, Mining Power của người dùng stake 100,000 STONX vào Diamond Pool theo điều kiện Flexible là như sau.

$$
P_{i,Diamond} = 100,000 \times 1.00 = 100,000
$$

Nếu người dùng chờ 100,000 giây, PoM tích lũy như sau.

$$
PoM = 100,000 \times 100,000
$$

$$
PoM = 10,000,000,000
$$

Khi PoM tích lũy của người dùng đạt hoặc vượt ngưỡng PoM cần thiết của pool tương ứng, người dùng có thể claim Gem NFT.

$$
PoM_{i,j}(t) \ge R_j
$$

Khi Gem NFT được claim, ngưỡng cần thiết `(R_j)` được trừ khỏi giá trị PoM của người dùng trong pool đó.

$$
PoM_{i,j,new} = PoM_{i,j,old} - R_j
$$

Cấu trúc này ngăn PoM vượt ngưỡng bị mất một cách không cần thiết. Ví dụ, nếu ngưỡng PoM cần thiết là 22,000,000,000 và người dùng có 23,000,000,000 PoM khi claim Gem NFT, thì 1,000,000,000 PoM còn lại sau claim sẽ được giữ cho chu kỳ mining tiếp theo.

PoM tích lũy độc lập theo từng stone pool. PoM tích lũy trong Diamond Pool chỉ có thể dùng để claim Diamond NFT, không thể chuyển thành PoM của Ruby Pool hoặc Sapphire Pool. Cấu trúc này bảo vệ tính độc lập, sự khan hiếm và độ khó khai thác của từng stone pool.

Ngay cả khi người dùng unstake STONX khỏi một pool cụ thể, PoM đã tích lũy có thể vẫn được ghi lại trong pool đó. Tuy nhiên, sau khi unstake, Mining Power của người dùng trong pool đó trở thành 0, nên không có PoM mới được tích lũy. Nếu người dùng stake STONX lại vào cùng pool, PoM mới sẽ tích lũy tiếp trên PoM hiện có.

Nếu người dùng stake thêm STONX vào cùng pool, PoM hiện có được giữ nguyên và chỉ Mining Power sau khi stake thêm tăng lên. Ngược lại, nếu giảm lượng stake, PoM hiện có vẫn giữ nguyên nhưng tốc độ tích lũy trong tương lai giảm xuống.

PoM không thể chuyển ra ngoài, giao dịch hoặc chuyển sang stone pool khác. Điều này vì PoM không phải tài sản độc lập, mà là chỉ số khối lượng công việc do một người dùng cụ thể tích lũy thông qua tham gia mining thực tế trong một pool cụ thể.
