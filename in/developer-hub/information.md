# Information

{% hint style="info" %}
**Testnet Notice**\
이 문서는 Crypto Stone Protocol Developer Hub에 추가하기 위한 한국어 초안입니다.\
현재 기준은 **Sepolia 테스트넷 / 개발 단계**입니다. 메인넷 배포 전 네트워크, ABI, 감사 여부, API Base URL, 실제 배포 주소를 최종 업데이트해야 합니다.
{% endhint %}

{% hint style="info" %}
**Contract Address Policy**\
테스트넷 컨트랙트 주소는 계속 추가 배포될 수 있으므로, 본 문서에서는 주소 칸을 의도적으로 비워둡니다.\
각 주소는 최종 확인 후 직접 입력합니다.
{% endhint %}

{% hint style="info" %}
**Naming / Symbol Policy**\
프로젝트 및 프로토콜의 공식 명칭은 **Crypto Stone Protocol**입니다.\
실제 운영 토큰 심볼은 **STONX**입니다. 기존 백서 일부에 남아 있는 `STONE` 표기는 레거시 백서 표기로 보고, Developer Hub와 신규 문서에서는 **STONX**를 기준으로 작성합니다.
{% endhint %}

### 1. 기본 정보

| 항목                       | 내용                                                                    |
| ------------------------ | --------------------------------------------------------------------- |
| Project / Protocol Name  | **Crypto Stone Protocol**                                             |
| Token Display Name       | **STONX Token**                                                       |
| Token Symbol             | **STONX**                                                             |
| Legacy Whitepaper Symbol | `STONE`                                                               |
| Total Supply             | **1,200,000,000 STONX**                                               |
| Current Network          | Sepolia Testnet                                                       |
| Token Standard           | ERC-20 compatible                                                     |
| NFT Standard             | ERC-721 compatible                                                    |
| Core Model               | STONX 기반 디지털 원석 채굴, Proof of Mining, Gem NFT Claim                    |
| Mining Structure         | 12개 Gemstone Mining Pool                                              |
| Main User Action         | STONX 보유 → Pool 선택 → Stake → Mining Power 생성 → PoM 누적 → Gem NFT Claim |
| Admin Mint Policy        | 최종 배포 후 임의 추가 발행 및 임의 NFT 발행을 제한하는 구조 지향                              |
| Core Source of Truth     | Smart Contract                                                        |
| Platform Role            | 지갑 연결, 채굴 상태 표시, NFT 탐색, API/Indexer 제공                               |

### 2. 프로젝트 명칭 정리

**Crypto Stone Protocol**은 프로젝트와 프로토콜의 공식 명칭입니다.\
토큰 자체는 프로토콜 내부에서 사용되는 유틸리티 토큰이며, 운영 심볼은 **STONX**입니다.

기존 백서 또는 과거 자료에 `STONE`이라는 표기가 남아 있을 수 있습니다. 이 표기는 초기 백서 작성 단계의 레거시 표기이며, 신규 Developer Hub 문서, 플랫폼 UI, API 응답, 컨트랙트 설명에서는 **STONX**를 기준으로 통일합니다.

권장 표기 방식은 아래와 같습니다.

```txt
Project / Protocol: Crypto Stone Protocol
Token Symbol: STONX
Legacy Whitepaper Symbol: STONE
```

### 3. 토큰 정보

Crypto Stone Protocol의 토큰은 디지털 원석 채굴 생태계에 참여하기 위한 프로토콜 유틸리티 토큰입니다.\
사용자는 STONX를 보유하고, 컨트랙트에 승인한 뒤, 원하는 Gemstone Mining Pool에 스테이킹하여 Mining Power를 생성할 수 있습니다.

| 항목                               | 내용                                            |
| -------------------------------- | --------------------------------------------- |
| Token Display Name               | **STONX Token**                               |
| Symbol                           | **STONX**                                     |
| Standard                         | ERC-20 compatible                             |
| Total Supply                     | **1,200,000,000 STONX**                       |
| Decimals                         | 18 기준                                         |
| Main Utility                     | Stake, Mining Power 생성, PoM 누적, Gem NFT Claim |
| Economic Role                    | 디지털 원석 채굴 참여 자원                               |
| Redemption Right                 | 실물 원석 상환권, 지분권, 수익청구권을 의미하지 않음                |
| Legacy Reference                 | 기존 백서 내 `STONE` 표기는 STONX로 해석                 |
| Sepolia Testnet Contract Address |                                               |
| Mainnet Contract Address         |                                               |

### 4. NFT 정보

Crypto Stone Protocol의 NFT는 단순 이미지 NFT가 아니라, 채굴 과정을 통해 생성되는 **디지털 원석 Gem NFT**입니다.\
각 NFT는 채굴 풀, 채굴 시점, 원석 타입, 희소도, 속성값, 메타데이터를 통해 고유성을 갖습니다.

| 항목                               | 내용                                                                         |
| -------------------------------- | -------------------------------------------------------------------------- |
| NFT Category                     | Digital Gemstone NFT                                                       |
| Suggested Collection Name        | Crypto Stone Gem NFT                                                       |
| Standard                         | ERC-721 compatible                                                         |
| Minting Method                   | Mining Pool의 Claim 로직을 통해 발행                                               |
| Pool Structure                   | 12개 Gemstone Pool 기반                                                       |
| Main Attribute Examples          | stoneType, rarity, grade, weight, color, clarity, cut, miningPool, minedAt |
| Metadata Role                    | NFT 이미지, 원석 속성, 희소도, 채굴 출처 표시                                              |
| Admin Mint Policy                | 최종 배포 후 임의 발행 제한 구조 지향                                                     |
| Transfer                         | ERC-721 표준 전송 지원                                                           |
| Sepolia Testnet Contract Address |                                                                            |
| Mainnet Contract Address         |                                                                            |

### 5. 테스트넷 컨트랙트 주소 등록표

아래 표는 GitBook Developer Hub에 그대로 올린 뒤, 배포가 완료된 주소를 직접 입력하기 위한 빈칸입니다.

| Contract / Module             | Sepolia Testnet Address | 설명                         |
| ----------------------------- | ----------------------- | -------------------------- |
| STONX Token                   |                         | STONX ERC-20 토큰 컨트랙트       |
| Crypto Stone Gem NFT          |                         | Gem NFT ERC-721 컨트랙트       |
| Mining Pool Factory           |                         | 12개 Pool 생성 또는 등록 관리       |
| Diamond Pool                  |                         | Gemstone Mining Pool       |
| Ruby Pool                     |                         | Gemstone Mining Pool       |
| Sapphire Pool                 |                         | Gemstone Mining Pool       |
| Emerald Pool                  |                         | Gemstone Mining Pool       |
| Amethyst Pool                 |                         | Gemstone Mining Pool       |
| Topaz Pool                    |                         | Gemstone Mining Pool       |
| Opal Pool                     |                         | Gemstone Mining Pool       |
| Aquamarine Pool               |                         | Gemstone Mining Pool       |
| Garnet Pool                   |                         | Gemstone Mining Pool       |
| Peridot Pool                  |                         | Gemstone Mining Pool       |
| Citrine Pool                  |                         | Gemstone Mining Pool       |
| Turquoise Pool                |                         | Gemstone Mining Pool       |
| Randomness / Attribute Module |                         | NFT 속성 생성 또는 랜덤성 처리 모듈     |
| Protocol Config               |                         | 확률표, 파라미터, 공개 설정 저장용 선택 모듈 |
| API / Indexer                 |                         | 오프체인 조회 및 플랫폼 데이터 인덱싱      |

### 6. 사용자 관점 요약

1. 사용자는 지갑을 연결합니다.
2. STONX를 보유합니다.
3. 원하는 Gemstone Pool을 선택합니다.
4. STONX를 Pool 컨트랙트에 승인합니다.
5. STONX를 스테이킹합니다.
6. 스테이킹 수량과 기간에 따라 Mining Power와 Proof of Mining이 누적됩니다.
7. 조건을 충족하면 Gem NFT를 Claim합니다.
8. 발행된 Gem NFT는 지갑과 플랫폼의 NFT Explorer에서 확인할 수 있습니다.
