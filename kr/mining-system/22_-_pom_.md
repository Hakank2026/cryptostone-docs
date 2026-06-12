# 22\_필요\_PoM\_임계값

보석 1개를 채굴하기 위해 필요한 PoM 임계값은 Base Mining Unit, 스톤별 기본 채굴 주기, 풀 난이도, 희소성 배수에 의해 결정된다.

스톤 (j)의 기본 채굴 주기를 (T\_j), Base Mining Unit을 (B), 풀 난이도를 (D\_j), 희소성 배수를 (S\_j)라고 할 때, 필요 PoM 임계값 (R\_j)는 다음과 같이 정의된다.

$$
R_j = B \times T_j \times D_j \times S_j
$$

CryptoStone의 기준값은 다음과 같다.

* (B = 100,000) STONE
* Target Pool Power = 40,000,000 Power

예를 들어 Diamond Pool의 기본 채굴 주기가 220,000초이고, Pool Difficulty와 Scarcity Multiplier가 모두 1x라면 다음과 같다.

$$
R_{Diamond} = 100,000 \times 220,000 \times 1 \times 1
$$

$$
R_{Diamond} = 22,000,000,000 \text{ PoM}
$$

사용자 (i)의 마이닝 파워가 (P\_{i,j})일 때, 해당 사용자가 스톤 (j)의 NFT 1개를 claim하기까지 필요한 예상 시간은 다음과 같이 표현할 수 있다.

$$
E[T_{i,j}] = R_j \div P_{i,j}
$$

예를 들어 사용자가 Diamond Pool에 100,000 STONE을 Flexible 조건으로 스테이킹한 경우:

$$
E[T_{i,Diamond}] = 22,000,000,000 \div 100,000
$$

$$
= 220,000\text{초}
$$

$$
\approx 2.55\text{일}
$$

즉, 초기 조건에서 100,000 STONE을 스테이킹한 사용자는 약 2.55일마다 Diamond NFT 1개를 claim할 수 있다.
