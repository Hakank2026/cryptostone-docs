# 16\_Base\_Mining\_Unit과\_소액\_참여\_구조

CryptoStone의 기준 마이닝 단위는 다음과 같이 설정한다.

**Base Mining Unit = 100,000 STONE**

다만 이는 최소 참여 수량이 아니다. Base Mining Unit은 채굴 속도와 난이도를 계산하기 위한 기준 단위이다.

CryptoStone은 가능한 많은 사용자가 채굴에 참여할 수 있도록 PoM 누적 구조를 채택한다. 사용자는 100,000 STONE 미만의 수량으로도 마이닝 풀에 참여할 수 있으며, 스테이킹 수량과 시간에 비례하여 PoM 값을 누적한다.

사용자는 누적 PoM 값이 해당 풀의 필요 PoM 임계값 (R\_j) 이상이 되었을 때 Gem NFT를 claim할 수 있다.

$$
PoM_{i,j}(t) \ge R_j
$$

예를 들어 Diamond Pool의 초기 조건에서 Pool Difficulty와 Scarcity Multiplier가 모두 1x라고 가정하면 다음과 같다.

| Active Stake  | Diamond NFT 1개 예상 채굴 시간 |
| ------------- | ----------------------- |
| 100,000 STONE | 약 2.55일                 |
| 10,000 STONE  | 약 25.5일                 |
| 5,000 STONE   | 약 51일                   |
| 1,000 STONE   | 약 255일                  |
| 100 STONE     | 약 6.98년                 |

이 구조는 고마이닝 파워 유저에게는 빠른 채굴 기회를 제공하면서도, 소액 참여자도 장기적으로 PoM 값을 누적하여 Gem NFT를 claim할 수 있도록 한다.

필자는 이 구조가 CryptoStone의 생태계 확장에 매우 중요하다고 본다. NFT의 희소성은 총 발행량, 속성 확률, 반감기 구조로 유지하고, 사용자 참여성은 낮은 진입장벽과 PoM 누적 구조로 확대해야 하기 때문이다.
