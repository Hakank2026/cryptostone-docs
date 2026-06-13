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
\text{Stone Scarcity Score}
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

| Attribute      | Max Score |
| -------------- | --------- |
| Stone Scarcity | 20        |
| Weight         | 20        |
| Color          | 20        |
| Clarity        | 20        |
| Cut            | 20        |
| Total          | 100       |

Stone Scarcity Score는 스톤별 총 발행량을 기준으로 계산된다.

$$
\text{Stone Scarcity Score}
=
20 \times
\frac{\text{MaxCollectionSupply} - \text{StoneMaxSupply}}
{\text{MaxCollectionSupply} - \text{MinCollectionSupply}}
$$

기준값은 다음과 같다.

* MaxCollectionSupply = 220,000
* MinCollectionSupply = 110,000

예를 들어 Diamond의 Max Supply는 110,000개이므로 가장 높은 Stone Scarcity Score를 가진다. Zircon의 Max Supply는 220,000개이므로 가장 낮은 Stone Scarcity Score를 가진다.

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
| Common     | 0 \~ 39            | 가장 흔한 보석군, 제련 재료와 기본 수집층 |
| Rare       | 40 \~ 59           | 일반 채굴 결과보다 희소한 중간 수집층 |
| Epic       | 60 \~ 79           | 연간 채굴 경험에서 의미 있는 성공 구간 |
| Legendary  | 80 \~ 94           | 매우 희귀한 고가치 수집 구간 |
| Genesis    | 95 \~ 100          | 극단적 조합 또는 초기 채굴 고유성이 반영된 최상위 구간 |

CryptoStone은 Rarity Score와 Probability Rarity Index를 함께 사용함으로써 수집자가 직관적으로 이해할 수 있는 점수 체계와 데이터 기반으로 검증 가능한 희귀도 체계를 동시에 제공한다.
