# 25 Cấu trúc phi tuyến của tốc độ mining và cạn kiệt nguồn cung

## Depletion

Cấu trúc mining của CryptoStone không phải mô hình phát hành tuyến tính đơn giản. Mỗi stone có nguồn cung, chu kỳ mining, Pool Difficulty và Scarcity Multiplier độc lập; khi tiến độ mining tăng lên, tốc độ mining chậm lại do Scarcity Multiplier.

Nếu Mining Power hiệu dụng của stone pool $(j)$ là $(P\_{eff,j})$, có thể biểu diễn như sau:

$$
P_{eff,j} = \min(P_j, P_j^*)
$$

Điều này có nghĩa khi tổng Mining Power thấp hơn Target Pool Power, sức mạnh tham gia thực tế ảnh hưởng đến tốc độ mining; còn khi tổng Mining Power vượt Target Pool Power, tốc độ mining hiệu dụng bị giới hạn thông qua việc tăng độ khó.

Sản lượng mining kỳ vọng trên một đơn vị thời gian của stone pool $(j)$, $(\lambda\_j)$, có thể được biểu diễn khái niệm như sau:

$$
\lambda_j = P_{eff,j} \div (M_{ref} \times T_j \times S_j)
$$

Ở đây, $(M\_{ref})$ là Protocol Reference Power, $(T\_j)$ là Base Mining Interval của stone, và $(S\_j)$ là Scarcity Multiplier. Base Mining Unit là đơn vị tham gia tối thiểu; tốc độ mining dài hạn được hiệu chỉnh bằng Protocol Reference Power và Target Pool Power.

Thời gian cần để một stone cụ thể đạt tiến độ mining $(q)$ có thể được biểu diễn bằng mô hình phi tuyến sau:

$$
Time_j(q) = (N_j \times M_{ref} \times T_j \div P_{eff,j}) \times \int_0^q S_j(x)\,dx
$$

Công thức này cho thấy cấu trúc mining của CryptoStone không phải mô hình cạn kiệt tuyến tính, mà là mô hình mining phi tuyến trong đó tốc độ mining chậm dần khi nguồn cung còn lại của stone giảm xuống.

Vì vậy, Gem NFT có thể được khai thác tương đối tích cực ở giai đoạn đầu, nhưng sau mốc 90%, Scarcity Multiplier tăng lên và tốc độ mining của phần nguồn cung còn lại chậm đi đáng kể.
