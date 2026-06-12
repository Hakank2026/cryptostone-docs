# 41\_생태계\_확장\_모듈과\_Gem\_Refinement

CryptoStone의 핵심 프로토콜은 STONX, 12개의 스톤별 마이닝 풀, Proof of Mining, 그리고 Gem NFT로 구성된다. CryptoStone 생태계는 이 핵심 채굴 구조 위에 Marketplace, Arena, Ranking System, Collection Quest, Gem Refinement 같은 확장 모듈을 결합하여 디지털 보석의 사용성과 거래성을 넓힌다.

Marketplace는 채굴된 Gem NFT의 가격 발견과 소유권 이전을 지원한다. 사용자는 자신이 채굴하거나 제련한 Gem NFT를 공개 시장에 등록할 수 있고, 구매자는 스톤 종류, 등급, Rarity Score, 속성, tokenId, 거래 이력, 미디어 상태를 기준으로 수집 대상을 선택할 수 있다. Marketplace는 희귀도 자체를 보장하는 장치가 아니라, 공개된 속성과 온체인 provenance를 기반으로 시장 가격이 형성되는 장소다.

Arena는 Gem NFT의 유틸리티를 확장하는 게임형 모듈이다. 사용자는 자신이 보유한 Gem NFT를 입장 seed 또는 참여 자격으로 사용하고, STONX 기반 entry fee를 통해 Duel, Battle, Arena 같은 테이블에 참여할 수 있다. Arena는 Gem NFT에 수집 외 사용 맥락을 부여하지만, 채굴 확률이나 NFT 등급을 직접 변경하지 않는다.

Gem Refinement, 즉 보석 제련은 채굴된 Gem NFT를 다시 활용할 수 있도록 설계된 선택형 사후 유틸리티 구조이다. Gem Refinement는 추가적인 무제한 NFT 발행 구조가 아니라, 동일한 `stoneType`을 가진 Gem NFT 2개를 결합하여 동일한 `stoneType`의 Refined Gem NFT 1개를 생성하는 공급 압축 메커니즘이다.

Gem NFT 2개

* 소량의 STONX 사용 또는 소각\
  → Parent Gem NFTs Burned\
  → Refined Gem NFT 1개 Minted

제련이 1회 실행될 때마다 부모 Gem NFT 2개는 소각되거나 회수 불가능한 방식으로 처리되고, 새로운 Refined Gem NFT 1개만 생성된다. 따라서 전체 유통 NFT 수량은 1개 감소한다.

2 Gem NFTs Burned → 1 Refined Gem NFT Minted\
Net Circulating NFT Supply = -1

초기 Gem Refinement는 동일 스톤 기반 제련만 허용하는 것이 바람직하다. 예를 들어 Garnet Gem NFT 2개는 Refined Garnet Gem NFT 1개로, Ruby Gem NFT 2개는 Refined Ruby Gem NFT 1개로 제련될 수 있다. 서로 다른 스톤 간 제련은 스톤별 공급량, 희소성, 반감기, 채굴 난이도 구조를 복잡하게 만들 수 있으므로 초기 모델에서는 제외하는 것이 적절하다.

| 항목         | 원칙                                  |
| ---------- | ----------------------------------- |
| 필요 재료      | 동일한 `stoneType`의 Gem NFT 2개         |
| 추가 비용      | 소량의 STONX 사용 또는 소각                  |
| 부모 NFT 처리  | 부모 Gem NFT 2개 소각 또는 회수 불가능 처리       |
| 결과물        | 동일한 `stoneType`의 Refined Gem NFT 1개 |
| 세대 정보      | Gen1 또는 Refined Generation으로 기록     |
| 공급 효과      | 전체 유통 NFT 수량 감소                     |
| 민팅 권한      | Refining Contract에 한정               |
| Admin Mint | 없음                                  |
| 랜덤성        | 검증 가능한 랜덤 구조 사용                     |

Refined Gem NFT의 기준 등급은 두 부모 Gem NFT 중 더 높은 등급을 기준으로 산정할 수 있다.

$$
T_{base} = \max(T_1, T_2)
$$

여기서 (T\_1), (T\_2)는 두 부모 Gem NFT의 등급이며, (T\_{base})는 제련 결과 산정의 기준 등급이다.

희귀도 등급은 Common, Rare, Epic, Legendary, Genesis의 5개 등급으로 통일한다.

| Tier Level | Tier      |
| ---------- | --------- |
| 0          | Common    |
| 1          | Rare      |
| 2          | Epic      |
| 3          | Legendary |
| 4          | Genesis   |

제련 결과는 기준 등급과 동일한 등급이 나올 확률을 가장 높게 설정한다. 한 단계 낮은 등급이 나올 확률은 낮게 두며, 상향 결과가 발생하더라도 최대 1~2단계 상승으로 제한한다. 또한 낮은 등급일수록 상향 가능성을 상대적으로 높게 두고, 높은 등급일수록 상향 가능성을 낮게 설정함으로써 고등급 Gem NFT의 희소성을 보호한다.

0부터 9,999까지의 랜덤값 (U)를 사용하는 BPS 방식의 기본 임계값 예시는 다음과 같다.

$$
U \in [0, 9,999]
$$

10,000 BPS = 100%

| Base Tier | -1 Tier | Same Tier | +1 Tier | +2 Tier |
| --------- | ------: | --------: | ------: | ------: |
| Common    |      없음 |     68.0% |   27.0% |    5.0% |
| Rare      |    1.0% |     76.0% |   20.0% |    3.0% |
| Epic      |    1.5% |     88.0% |   10.0% |    0.5% |
| Legendary |    2.0% |     97.0% |    1.0% |      없음 |
| Genesis   |      제한 |        제한 |      제한 |      제한 |

Genesis는 최상위 수집 구간으로 취급되며, 초기 모델에서는 제련 재료로 사용하는 것을 제한하는 편이 바람직하다. 이 구조는 제련의 기대감을 유지하면서도, 고등급 NFT가 과도하게 생성되는 것을 방지하기 위한 것이다.

두 부모 Gem NFT 간 등급 차이가 클 경우, 상향 확률은 추가로 조정될 수 있다. 등급 차이 (G)는 다음과 같이 정의한다.

$$
G = |T_1 - T_2|
$$

| Tier Gap (G) | Upgrade Modifier | 처리 원칙 |
| ------------ | ----------------: | -------- |
| 0            |              100% | 동일 등급 제련. 기본 확률 적용 |
| 1            |               70% | 인접 등급 제련. 상향 확률 일부 감소 |
| 2            |               35% | 큰 등급 차이. 상향 확률 크게 감소 |
| 3 이상         |                제한 | 초기 모델에서는 제련 제한 가능 |

상향 확률은 다음과 같이 조정할 수 있다.

$$
\text{Adjusted Upgrade Probability}
= \text{Base Upgrade Probability} \times \text{Upgrade Modifier}
$$

조정으로 감소한 상향 확률은 동일 등급 유지 확률에 더해진다. 이를 통해 높은 등급 Gem NFT 1개에 낮은 등급 Gem NFT를 반복적으로 결합하여 상위 등급 생성을 시도하는 행위를 제한할 수 있다.

Refining Contract는 소유권 검증, 동일 스톤 검증, 등급 차이 검증, STONX 사용 또는 소각, 부모 NFT 소각, 랜덤값 요청, Refined Gem NFT 발행 요청을 수행한다. Refined Gem NFT는 운영자의 임의 발행으로 생성되어서는 안 되며, 오직 Refining Contract가 사전에 정의된 조건을 검증한 경우에만 생성되어야 한다.

Gem Refinement는 CryptoStone의 기본 채굴 구조를 대체하는 기능이 아니다. 이는 채굴 이후 Gem NFT의 활용성, 수집성, 거래 수요를 확장하기 위한 선택형 모듈이다. Marketplace, Arena, Gem Refinement는 모두 핵심 채굴 구조를 보완하는 모듈이며, Gem NFT의 희소성과 PoM 기반 채굴 원칙을 훼손하지 않아야 한다.
