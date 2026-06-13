# 10 Proof of Mining

비트코인에서 채굴자는 해시파워를 통해 블록을 생성할 확률을 얻는다. 해시파워가 높을수록 블록을 발견할 가능성은 높아지지만, 비트코인의 전체 발행 규칙이나 난이도 구조를 임의로 변경할 수는 없다. 즉, 해시파워는 네트워크 규칙을 바꾸는 권한이 아니라, 정해진 규칙 안에서 더 많은 채굴 기회를 얻기 위한 연산 자원이다.

CryptoStone은 이 개념을 디지털 보석 채굴 구조에 맞게 추상화한다. CryptoStone에서 해시파워에 대응되는 개념은 Mining Power이며, Mining Power가 시간에 따라 누적된 작업량이 Proof of Mining, PoM이다.

| Bitcoin                 | CryptoStone              |
| ----------------------- | ------------------------ |
| Hash Power              | Mining Power             |
| Proof of Work           | Proof of Mining, PoM     |
| ASIC / Mining Equipment | Staked STONX             |
| Block Reward            | Gem NFT                  |
| Network Difficulty      | Pool Difficulty          |
| Halving                 | Scarcity Multiplier      |
| BTC Issuance            | Gem NFT Minting          |
| Miner                   | STONX Staker / Gem Miner |

PoM은 별도로 전송되거나 거래되는 토큰이 아니다. PoM은 사용자의 채굴 참여와 시간 경과를 컨트랙트가 기록하는 온체인 작업량 지표이다. 또한 PoM은 네트워크 합의 알고리즘을 의미하지 않는다. CryptoStone의 PoM은 특정 스톤 풀에서 사용자가 Gem NFT를 claim할 수 있는 조건에 도달했는지를 판단하기 위한 프로토콜 내부 값이다.

사용자 (i)가 특정 스톤 풀 (j)에 스테이킹한 STONX 수량을 (s\_{i,j}), 락업 기간에 따른 배수를 (L\_i)라고 할 때, 사용자의 마이닝 파워 (P\_{i,j})는 다음과 같이 정의된다.

$$
P_{i,j} = s_{i,j} \times L_i
$$

사용자의 PoM 값은 시간에 따라 다음과 같이 누적된다.

$$
PoM_{i,j}(t + \Delta t) = PoM_{i,j}(t) + P_{i,j} \times \Delta t
$$

여기서 (PoM\_{i,j}(t))는 사용자 (i)가 스톤 풀 (j)에서 시점 (t)까지 누적한 Proof of Mining 값이다.

PoM은 스톤 풀별로 독립적으로 누적된다. 예를 들어 Diamond Pool에서 누적된 PoM은 Diamond NFT claim에만 사용할 수 있으며, Ruby Pool 또는 Sapphire Pool의 PoM으로 전환될 수 없다. 이 구조는 각 스톤 풀의 독립성, 희소성, 채굴 난이도를 보호한다.

마이닝 파워가 높은 사용자는 더 빠르게 필요한 PoM 임계값에 도달할 수 있지만, 보석의 희귀도 확률을 임의로 높이거나 특정 등급의 보석을 선택할 수 없다.
