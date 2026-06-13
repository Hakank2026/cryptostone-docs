# 22 필요 PoM 임계값

보석 1개를 채굴하기 위해 필요한 PoM 임계값은 Protocol Reference Power, 스톤별 기본 채굴 주기, 풀 난이도, 희소성 배수에 의해 결정된다.

스톤 (j)의 기본 채굴 주기를 (T\_j), Protocol Reference Power를 (M\_{ref}), 풀 난이도를 (D\_j), 희소성 배수를 (S\_j)라고 할 때, 필요 PoM 임계값 (R\_j)는 다음과 같이 정의된다.

$$
R_j = M_{ref} \times T_j \times D_j \times S_j
$$

CryptoStone의 기준값은 다음과 같다.

* Base Mining Unit = 1,000 STONX
* Protocol Reference Power = 100,000 Power
* Target Pool Power = 40,000,000 Power

Base Mining Unit은 최소 참여 단위이고, Protocol Reference Power는 채굴 속도를 보정하기 위한 기준 파워이다. 이 둘을 분리함으로써 CryptoStone은 접근 가능한 참여 단위와 장기 공급 제어를 동시에 유지한다.

예를 들어 Garnet Pool의 기본 채굴 주기가 170,000초이고, Pool Difficulty와 Scarcity Multiplier가 모두 1x라면 다음과 같다.

$$
R_{Garnet} = 100,000 \times 170,000 \times 1 \times 1
$$

$$
R_{Garnet} = 17,000,000,000 \text{ PoM}
$$

사용자 (i)의 마이닝 파워가 (P\_{i,j})일 때, 해당 사용자가 스톤 (j)의 NFT 1개를 claim하기까지 필요한 예상 시간은 다음과 같이 표현할 수 있다.

$$
E[T_{i,j}] = R_j \div P_{i,j}
$$

예를 들어 사용자가 Garnet Pool에 6,000 STONX를 Flexible 조건으로 스테이킹한 경우:

$$
E[T_{i,Garnet}] = 17,000,000,000 \div 6,000
$$

$$
= 2,833,333\text{초}
$$

$$
\approx 32.8\text{일}
$$

즉, 초기 조건에서 6,000 STONX를 스테이킹한 사용자는 약 한 달 전후로 Garnet NFT 1개를 claim할 수 있다. 더 적은 수량의 사용자는 더 느리게 PoM을 누적하고, 더 많은 수량의 사용자는 더 빠르게 claim 조건에 도달한다.
