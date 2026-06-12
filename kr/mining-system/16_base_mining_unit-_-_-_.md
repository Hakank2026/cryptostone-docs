# 16\_Base\_Mining\_Unit과\_소액\_참여\_구조

CryptoStone의 기본 참여 단위는 다음과 같이 설정한다.

**Base Mining Unit = 1,000 STONX**

Base Mining Unit은 사용자가 마이닝 풀에 참여할 수 있는 최소 기준 단위이다. 이는 과도하게 낮은 단위로 무의미한 참여가 분산되는 것을 막으면서도, 일반 사용자가 부담 가능한 규모로 Proof of Mining, PoM 누적을 시작할 수 있도록 하기 위한 사용자 참여 기준이다. Base Mining Unit은 단기 claim을 보장하는 기준은 아니다.

CryptoStone은 가능한 많은 사용자가 채굴에 참여할 수 있도록 PoM 누적 구조를 채택한다. 사용자는 1,000 STONX 단위부터 마이닝 풀에 참여할 수 있으며, 스테이킹 수량과 시간에 비례하여 PoM 값을 누적한다.

사용자는 누적 PoM 값이 해당 풀의 필요 PoM 임계값 (R\_j) 이상이 되었을 때 Gem NFT를 claim할 수 있다.

$$
PoM_{i,j}(t) \ge R_j
$$

장기 공급 속도는 Base Mining Unit 하나만으로 결정되지 않는다. CryptoStone은 1,000 STONX의 기본 참여 단위와 별도로, 풀별 Target Pool Power, Protocol Reference Power, Pool Difficulty, Scarcity Multiplier를 함께 사용하여 전체 Gem NFT 공급이 장기간에 걸쳐 점진적으로 채굴되도록 설계한다.

초기 Garnet Pool에서 Pool Difficulty와 Scarcity Multiplier가 모두 1x이고, Protocol Reference Power가 100,000 Power라고 가정하면 예상 claim 기간은 다음과 같이 해석할 수 있다.

| Active Stake  | Garnet NFT 1개 예상 claim 기간 |
| ------------- | -------------------------- |
| 1,000 STONX   | 약 197일                    |
| 4,800 STONX   | 약 41일                     |
| 6,000 STONX   | 약 32.8일                   |
| 100,000 STONX | 약 1.97일                   |

이 구조는 1,000 STONX의 기본 참여자도 PoM을 누적할 수 있게 하면서, 중간 규모 참여자에게는 월 단위의 채굴 경험을 제공하고, 고마이닝 파워 유저에게는 더 잦은 claim 기회를 제공한다. 다만 마이닝 파워는 claim 빈도에만 영향을 주며, Gem NFT의 등급이나 속성을 직접 선택하게 해주지 않는다.

필자는 이 구조가 CryptoStone의 생태계 확장에 매우 중요하다고 본다. NFT의 희소성은 총 발행량, 속성 확률, 반감기 구조로 유지하고, 사용자 참여성은 낮은 진입장벽과 PoM 누적 구조로 확대해야 하기 때문이다.
