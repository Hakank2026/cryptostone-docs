# 31 Rarity Score và Probability Rarity Index

CryptoStone sử dụng hai chỉ số để định lượng độ hiếm của mỗi viên đá.

| Chỉ số | Mục đích |
| ------ | -------- |
| Rarity Score | Điểm 0~100 dễ hiểu cho người dùng |
| Probability Rarity Index | Chỉ số độ hiếm toán học dựa trên xác suất xuất hiện thực tế |

## 31.1 Rarity Score

$$
\text{Rarity Score}
=
\text{Pool Supply Score}
+
\text{Weight Score}
+
\text{Color Score}
+
\text{Clarity Score}
+
\text{Cut Score}
$$

Phân bổ điểm như sau.

| Thuộc tính | Max Score |
| ---------- | --------: |
| Pool Supply Score | 20 |
| Weight | 20 |
| Color | 20 |
| Clarity | 20 |
| Cut | 20 |
| Total | 100 |

Pool Supply Score được tính dựa trên Max Supply của từng stone. Hạng mục này không phải bonus tự động khiến một stone có giá trị hơn stone khác. Ngược lại, pool có Max Supply thấp hơn sẽ nhận điểm cơ sở thấp hơn, khiến việc đạt tier cuối cao trong các pool đó khó hơn.

$$
\text{Pool Supply Score}
=
15 + 5 \times
\frac{\text{StoneMaxSupply} - \text{MinCollectionSupply}}
{\text{MaxCollectionSupply} - \text{MinCollectionSupply}}
$$

Giá trị tham chiếu:

* MaxCollectionSupply = 220,000
* MinCollectionSupply = 110,000

Pool Supply Score được dùng như một giá trị cố định trong khoảng 15 đến 20.

| Stone | Max Supply | Pool Supply Score |
| ----- | ---------: | ----------------: |
| Diamond | 110,000 | 15.0 |
| Emerald | 120,000 | 15.5 |
| Ruby | 130,000 | 15.9 |
| Sapphire | 140,000 | 16.4 |
| Pearl | 150,000 | 16.8 |
| Garnet | 160,000 | 17.3 |
| Amethyst | 170,000 | 17.7 |
| Aquamarine | 180,000 | 18.2 |
| Spinel | 190,000 | 18.6 |
| Opal | 200,000 | 19.1 |
| Topaz | 210,000 | 19.5 |
| Zircon | 220,000 | 20.0 |

Ví dụ, Diamond có Max Supply là 110,000 nên nhận Pool Supply Score thấp nhất. Zircon có Max Supply là 220,000 nên nhận Pool Supply Score cao nhất. Do đó, việc đạt Epic, Legendary hoặc Genesis trong Diamond Pool sẽ khó hơn. Tuy nhiên, một Diamond Gem NFT cấp cao như vậy đồng thời có nguồn cung thấp và tier cao, nên có thể hình thành giá trị sưu tầm mạnh hơn trên thị trường.

Cấu trúc này không nhằm xếp hạng pool bằng một điểm số đơn giản. Nó phản ánh khác biệt nguồn cung giữa các pool vào độ khó đạt tier cuối. Pool có nguồn cung thấp khiến kết quả tier cao khó xuất hiện hơn, còn pool có nguồn cung cao khiến chúng tương đối dễ hơn.

## 31.2 Probability Rarity Index

Trong khi Rarity Score là chỉ số so sánh thân thiện với người dùng, Probability Rarity Index là chỉ số độ hiếm toán học dựa trên xác suất xuất hiện của từng thuộc tính.

Xác suất (P(g)) để tổ hợp thuộc tính của Gem NFT (`g`) xuất hiện được định nghĩa như sau:

$$
P(g) = P_{\text{stone}} \times P_{\text{weight}} \times P_{\text{color}} \times P_{\text{clarity}} \times P_{\text{cut}}
$$

Dựa trên đó, chỉ số rarity theo xác suất được tính như sau.

$$
\text{Probability Rarity Index} = -\log_{10}(P(g))
$$

Chỉ số này cho thấy một tổ hợp thuộc tính Gem NFT cụ thể hiếm đến mức nào về mặt thống kê.

Ví dụ, tổ hợp sau là cực kỳ hiếm.

* Diamond
* 100.00 CT trở lên
* D Color
* FL Clarity
* 6 Star Cut

Một tổ hợp như vậy nhận Rarity Score cao và cũng có Probability Rarity Index rất cao.

Rarity Score được dùng làm cơ sở thân thiện với người dùng để tính tier cuối. Các khoảng tier cơ bản như sau:

| Final Tier | Rarity Score Range | Vai trò |
| ---------- | ------------------ | ------- |
| Common | 0 ~ 34 | Nhóm đá phổ biến nhất, collectible cơ bản và vật liệu refinement |
| Rare | 35 ~ 50 | Collectible cấp trung hiếm hơn kết quả mining thông thường |
| Epic | 51 ~ 74 | Vùng cấp cao mà người dùng có thể cảm nhận là một thành công có ý nghĩa |
| Legendary | 75 ~ 89 | Vùng collectible rất hiếm và có giá trị cao |
| Genesis | 90 ~ 100 | Vùng cao nhất phản ánh tổ hợp thuộc tính cực hiếm và điểm số tối đa |

Khi áp dụng Pool Supply Score 15~20 cùng các bảng điểm Weight, Color, Clarity và Cut, các khoảng này nhắm tới kỳ vọng trung bình khoảng một kết quả Epic trở lên trên mỗi 36 NFT được khai thác. Kết quả thực tế thay đổi tùy theo tổ hợp thuộc tính ngẫu nhiên và điều chỉnh nguồn cung theo từng pool.

Mục tiêu có thể được biểu diễn bằng mô hình kỳ vọng sau. Khi `n` NFT được khai thác từ một pool cụ thể `s`, số lượng kỳ vọng của kết quả Epic trở lên được tính bằng cách cộng tất cả xác suất thuộc tính với Pool Supply Score của pool.

$$
E_{\ge Epic}(n)
=
n \cdot
\sum_{s \in S}
\pi_s
\sum_{w \in W}
\sum_{c \in C}
\sum_{q \in Q}
\sum_{u \in U}
\mathbf{1}
\left[
Score_s + Score_w + Score_c + Score_q + Score_u \ge 51
\right]
P_s(w)P_s(c)P_s(q)P_s(u)
\approx
\frac{n}{36}
$$

Ở đây, `S` là tập hợp stone pool, `π_s` là tỷ trọng tham gia của từng pool, và `W/C/Q/U` là tập thuộc tính Weight, Color, Clarity và Cut. Công thức này không nhằm bảo đảm giá thị trường. Nó là tham chiếu thiết kế giao thức để phân phối rarity không trở nên quá phổ biến hoặc quá đóng.

Bằng cách sử dụng đồng thời Rarity Score và Probability Rarity Index, CryptoStone cung cấp cả hệ thống điểm trực quan cho collector và hệ thống rarity dựa trên dữ liệu có thể kiểm chứng bằng toán học.
