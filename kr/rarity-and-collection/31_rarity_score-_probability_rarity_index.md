# 31 Rarity Score와 Probability Rarity Index

CryptoStone은 각 보석의 희귀도를 수치화하기 위해 두 가지 지표를 사용한다.

| 지표                       | 목적                            |
| ------------------------ | ----------------------------- |
| Rarity Score             | 사용자가 직관적으로 이해할 수 있는 0\~100 점수 |
| Probability Rarity Index | 실제 발생 확률에 기반한 수학적 희귀도 지표      |

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

점수 배분은 다음과 같다.

| Attribute         | Max Score |
| ----------------- | --------- |
| Pool Supply Score | 20        |
| Weight            | 20        |
| Color             | 20        |
| Clarity           | 20        |
| Cut               | 20        |
| Total             | 100       |

Pool Supply Score는 스톤별 Max Supply를 기준으로 계산된다. 이 항목은 특정 스톤을 다른 스톤보다 자동으로 더 높은 희귀도로 평가하기 위한 보너스가 아니다. 오히려 Max Supply가 적은 풀일수록 기본 점수를 낮게 부여하여, 해당 풀에서 높은 최종 등급에 도달하기 어렵게 만드는 난이도 보정 항목이다.

$$
\text{Pool Supply Score}
=
15 + 5 \times
\frac{\text{StoneMaxSupply} - \text{MinCollectionSupply}}
{\text{MaxCollectionSupply} - \text{MinCollectionSupply}}
$$

기준값은 다음과 같다.

* MaxCollectionSupply = 220,000
* MinCollectionSupply = 110,000

Pool Supply Score는 15점에서 20점 사이의 고정값으로 사용한다.

| Stone      | Max Supply | Pool Supply Score |
| ---------- | ---------: | ----------------: |
| Diamond    |    110,000 |              15.0 |
| Emerald    |    120,000 |              15.5 |
| Ruby       |    130,000 |              15.9 |
| Sapphire   |    140,000 |              16.4 |
| Pearl      |    150,000 |              16.8 |
| Garnet     |    160,000 |              17.3 |
| Amethyst   |    170,000 |              17.7 |
| Aquamarine |    180,000 |              18.2 |
| Spinel     |    190,000 |              18.6 |
| Opal       |    200,000 |              19.1 |
| Topaz      |    210,000 |              19.5 |
| Zircon     |    220,000 |              20.0 |

예를 들어 Diamond의 Max Supply는 110,000개이므로 가장 낮은 Pool Supply Score를 가진다. Zircon의 Max Supply는 220,000개이므로 가장 높은 Pool Supply Score를 가진다. 따라서 Diamond Pool에서 Epic, Legendary, Genesis 등급을 획득하는 것은 더 어렵다. 대신 그렇게 채굴된 Diamond 고등급 Gem NFT는 낮은 공급량과 높은 등급을 동시에 만족하므로 시장에서 더 높은 수집 가치를 형성할 수 있다.

이 구조는 풀 간 우열을 단순히 점수로 고정하기 위한 것이 아니다. 각 풀의 발행량 차이를 최종 등급 난이도에 반영하기 위한 장치다. 공급량이 낮은 풀은 고등급 달성 난이도가 높고, 공급량이 높은 풀은 고등급 달성 난이도가 상대적으로 낮다.

## 31.2 Probability Rarity Index

Rarity Score가 사용자 친화적 비교 지표라면, Probability Rarity Index는 각 속성의 발생 확률을 기반으로 한 수학적 희귀도 지표다.

Gem NFT (`g`)의 속성 조합이 발생할 확률 (`P(g)`)는 다음과 같이 정의된다.

$$
P(g) = P_{\text{stone}} \times P_{\text{weight}} \times P_{\text{color}} \times P_{\text{clarity}} \times P_{\text{cut}}
$$

이를 바탕으로 확률 기반 희귀도 지표를 산정한다.

$$
\text{Probability Rarity Index} = -\log_{10}(P(g))
$$

이 지표는 특정 Gem NFT가 확률적으로 얼마나 희귀한 조합인지 보여준다.

예를 들어 다음 조합은 극히 희귀하다.

* Diamond
* 100.00 CT 이상
* D Color
* FL Clarity
* 6 Star Cut

이러한 조합은 Rarity Score상 높은 점수를 받을 뿐 아니라, Probability Rarity Index에서도 매우 높은 희귀도를 갖게 된다.

Rarity Score는 최종 등급 산정의 사용자 친화적 기준으로 사용된다. 기본 등급 구간은 다음과 같이 설정할 수 있다.

| Final Tier | Rarity Score Range | 역할 |
| ---------- | ------------------ | ---- |
| Common     | 0 \~ 34            | 가장 흔한 보석군, 제련 재료와 기본 수집층 |
| Rare       | 35 \~ 50           | 일반 채굴 결과보다 희소한 중간 수집층 |
| Epic       | 51 \~ 74           | 사용자가 의미 있는 성공으로 인식할 수 있는 고등급 구간 |
| Legendary  | 75 \~ 89           | 매우 희귀한 고가치 수집 구간 |
| Genesis    | 90 \~ 100          | 극단적 속성 조합과 최상위 점수가 반영된 최상위 구간 |

위 점수 구간은 Pool Supply Score 15\~20, Weight, Color, Clarity, Cut 점수표를 함께 적용했을 때 평균적으로 약 36개 채굴당 Epic 이상 1개가 기대되는 수준을 목표로 한다. 실제 결과는 랜덤 속성 조합과 풀별 공급 보정값에 따라 달라진다.

이 목표값은 다음과 같은 기대값 모델로 검증한다. 특정 풀 `s`에서 `n`개가 채굴될 때 Epic 이상이 기대되는 수량은, 해당 풀의 Pool Supply Score와 각 속성 확률표를 모두 곱해 합산한 값으로 표현할 수 있다.

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

여기서 `S`는 스톤 풀 집합, `π_s`는 풀별 참여 비중, `W/C/Q/U`는 Weight, Color, Clarity, Cut 속성 집합이다. 이 수식은 실제 가격을 보장하기 위한 계산이 아니라, 희귀도 분포가 지나치게 흔하거나 지나치게 닫히지 않도록 조정하기 위한 프로토콜 설계 기준이다.

CryptoStone은 Rarity Score와 Probability Rarity Index를 함께 사용함으로써 수집자가 직관적으로 이해할 수 있는 점수 체계와 데이터 기반으로 검증 가능한 희귀도 체계를 동시에 제공한다.
