# 26 Weight 속성의 디지털화

무게는 모든 스톤이 공통적으로 CT, 즉 캐럿 단위를 사용한다. 그러나 각 보석의 무게 값은 랜덤으로 생성된다.

* Minimum Weight = 0.10 CT
* Maximum Weight = 200.00 CT
* Storage Unit = 0.01 CT

스마트컨트랙트에서는 소수점을 직접 저장하지 않고, 0.01 CT 단위의 정수로 저장한다.

| 표시 무게     | 컨트랙트 저장값 |
| --------- | -------- |
| 0.10 CT   | 10       |
| 1.25 CT   | 125      |
| 10.50 CT  | 1050     |
| 200.00 CT | 20000    |

무게는 균등 확률로 생성되지 않는다. 현실 보석에서 큰 캐럿일수록 희귀한 것처럼, CryptoStone에서도 큰 무게일수록 낮은 확률로 생성된다.

| Weight Range       | Probability | Attribute Tier | Score |
| ------------------ | ----------- | -------------- | ----: |
| 0.10 \~ 1.99 CT    | 75.00%      | Common         |     0 |
| 2.00 \~ 4.99 CT    | 15.00%      | Rare           |     5 |
| 5.00 \~ 9.99 CT    | 6.00%       | Epic           |    10 |
| 10.00 \~ 49.99 CT  | 3.50%       | Legendary      |    16 |
| 50.00 \~ 200.00 CT | 0.50%       | Genesis        |    20 |

위 표의 Attribute Tier는 최종 Gem NFT 등급을 직접 확정하는 값이 아니라, Rarity Score와 Probability Rarity Index를 계산하기 위한 무게 속성의 희귀도 구간이다. 최종 Gem NFT 등급은 Pool Supply Score, Weight, Color, Clarity, Cut의 조합을 종합하여 Common, Rare, Epic, Legendary, Genesis의 5개 등급으로 산정한다.
