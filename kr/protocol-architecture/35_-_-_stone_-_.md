# 35\_채굴\_비용과\_STONE\_소각\_구조

CryptoStone에서 STONE은 단순한 결제 수단이 아니라 디지털 보석 채굴에 참여하기 위한 마이닝 자원이다. 현실의 광산에서 채굴 장비와 에너지가 사용되고 시간이 지남에 따라 장비가 마모되는 것처럼, CryptoStone에서도 마이닝 풀에 투입된 STONE은 채굴 과정에서 일정한 디지털 감가상각 구조를 갖는다.

필자는 STONE의 소각 구조가 토큰 가격 상승을 보장하기 위한 장치가 아니라, 디지털 보석 채굴에 필요한 자원 소비와 희소성 구조를 표현하기 위한 장치라고 본다.

CryptoStone의 STONE 소각은 크게 두 가지 경우에 발생할 수 있다.

| 소각 유형         | 발생 시점               | 목적              |
| ------------- | ------------------- | --------------- |
| Claim Burn    | Gem NFT를 claim하는 시점 | 채굴 비용과 희소성 표현   |
| Maturity Burn | 락업 종료 후 unstake 시점  | 마이닝 자원의 감가상각 표현 |

Gem NFT를 claim할 때 발생하는 소각량 (B\_{claim,j})은 다음 공식으로 계산된다.

$$
B_{claim,j} = \beta \times S_j
$$

여기서 (\beta)는 Base Claim Burn이고, (S\_j)는 해당 스톤의 Scarcity Multiplier이다.

초기 기준값은 다음과 같이 설정한다.

| Scarcity Multiplier | Claim Burn |
| ------------------- | ---------- |
| 1x                  | 20 STONE   |
| 2x                  | 40 STONE   |
| 4x                  | 80 STONE   |
| 8x                  | 160 STONE  |
| 16x                 | 320 STONE  |
| 32x                 | 640 STONE  |

Base Claim Burn은 채굴 비용을 표현하는 최소 소비 구조이며, 전체 공급량을 급격히 축소시키기 위한 장치가 아니다. 소각된 STONE은 운영자나 재단에 지급되지 않고 영구적으로 유통량에서 제거된다. 이를 통해 STONE은 단순히 예치되는 자산이 아니라, CryptoStone 생태계 안에서 실제로 사용되고 소비되는 디지털 마이닝 자원으로 기능한다.
