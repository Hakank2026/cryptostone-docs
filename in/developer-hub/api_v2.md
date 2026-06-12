# Api\_v2

{% hint style="warning" %}
**Testnet Notice**\
이 문서는 Crypto Stone Protocol Developer Hub에 추가하기 위한 한국어 초안입니다.\
현재 기준은 **Sepolia 테스트넷 / 개발 단계**입니다. 메인넷 배포 전 네트워크, ABI, 감사 여부, API Base URL, 실제 배포 주소를 최종 업데이트해야 합니다.
{% endhint %}

{% hint style="warning" %}
**Contract Address Policy**\
테스트넷 컨트랙트 주소는 계속 추가 배포될 수 있으므로, 본 문서에서는 주소 칸을 의도적으로 비워둡니다.\
각 주소는 최종 확인 후 직접 입력합니다.
{% endhint %}

{% hint style="info" %}
**Naming / Symbol Policy**\
프로젝트 및 프로토콜의 공식 명칭은 **Crypto Stone Protocol**입니다.\
실제 운영 토큰 심볼은 **STONX**입니다. 기존 백서 일부에 남아 있는 `STONE` 표기는 레거시 백서 표기로 보고, Developer Hub와 신규 문서에서는 **STONX**를 기준으로 작성합니다.
{% endhint %}

## API

### 1. API 목적

Crypto Stone API는 Crypto Stone Protocol의 컨트랙트와 플랫폼 데이터를 외부 개발자, 파트너, Explorer, Dashboard, 게임/컬렉션 확장 모듈에서 활용할 수 있게 하는 개발자 인터페이스입니다.

API는 스마트 컨트랙트를 대체하지 않습니다.\
토큰 잔액, Pool 상태, NFT 소유권, Claim 가능 여부의 최종 기준은 항상 온체인 컨트랙트입니다.

API의 핵심 목적은 다음과 같습니다.

* STONX 토큰 정보 조회
* 사용자 지갑의 잔액 및 승인 상태 조회
* Mining Pool 목록 및 Pool별 상태 조회
* 사용자별 Mining Power, Proof of Mining, Claim 가능 상태 조회
* Gem NFT 목록, 속성, 희소도, 소유자 조회
* 플랫폼 UI용 Indexing Data 제공
* 외부 서비스가 사용할 수 있는 unsigned transaction data 생성
* ABI 및 컨트랙트 주소 Registry 제공

### 2. API 기본 원칙

| 원칙                       | 설명                                       |
| ------------------------ | ---------------------------------------- |
| Read-first               | API는 주로 온체인 데이터를 읽고 정리하는 역할              |
| No Custody               | API는 사용자 토큰, NFT, 개인키를 보관하지 않음           |
| User-signed              | 모든 Write Action은 사용자 지갑에서 직접 서명          |
| Contract Source of Truth | API 데이터는 컨트랙트 상태를 기준으로 검증                |
| Blank Address Policy     | 테스트넷 주소는 계속 추가될 수 있으므로 문서 내 주소값은 빈칸 유지   |
| Network Separation       | Testnet, Mainnet, Future Network를 명확히 분리 |
| ABI Transparency         | 공식 ABI 파일을 공개하여 직접 검증 가능하게 구성            |
| Indexer Status           | 데이터가 어느 블록까지 동기화되었는지 표시                  |

### 3. Base URL

현재 Base URL은 예시입니다. 실제 서버 배포 후 최종 도메인으로 교체합니다.

```txt
Testnet API Base URL:
https://api-testnet.cryptostone.org/v1

Mainnet API Base URL:
https://api.cryptostone.org/v1
```

### 4. Network / Contract API

#### `GET /network`

현재 API가 연결된 네트워크 정보를 조회합니다.

```bash
curl https://api-testnet.cryptostone.org/v1/network
```

Example response:

```json
{
  "project": "Crypto Stone Protocol",
  "network": "sepolia",
  "chainId": 11155111,
  "environment": "testnet",
  "latestIndexedBlock": 0,
  "status": "testing"
}
```

#### `GET /contracts`

공식 컨트랙트 주소 목록을 조회합니다.\
테스트넷 주소는 계속 추가될 수 있으므로 예시 응답의 주소값은 빈 문자열로 둡니다.

```bash
curl https://api-testnet.cryptostone.org/v1/contracts
```

Example response:

```json
{
  "project": "Crypto Stone Protocol",
  "token": {
    "name": "STONX Token",
    "symbol": "STONX",
    "address": ""
  },
  "gemNFT": {
    "name": "Crypto Stone Gem NFT",
    "standard": "ERC-721",
    "address": ""
  },
  "poolFactory": "",
  "randomnessModule": "",
  "protocolConfig": "",
  "pools": [
    {
      "stoneType": "Diamond",
      "address": ""
    },
    {
      "stoneType": "Ruby",
      "address": ""
    }
  ]
}
```

#### `GET /abi/:contractName`

공식 ABI를 조회합니다.

```bash
curl https://api-testnet.cryptostone.org/v1/abi/STONXToken
curl https://api-testnet.cryptostone.org/v1/abi/CryptoStoneGemNFT
curl https://api-testnet.cryptostone.org/v1/abi/MiningPool
```

### 5. Token API

#### `GET /token`

STONX 토큰의 기본 정보를 조회합니다.

```bash
curl https://api-testnet.cryptostone.org/v1/token
```

Example response:

```json
{
  "project": "Crypto Stone Protocol",
  "name": "STONX Token",
  "symbol": "STONX",
  "legacyWhitepaperSymbol": "STONE",
  "standard": "ERC-20",
  "decimals": 18,
  "totalSupply": "1200000000000000000000000000",
  "displayTotalSupply": "1,200,000,000 STONX",
  "contractAddress": ""
}
```

#### `GET /token/balance/:walletAddress`

특정 지갑의 STONX 잔액을 조회합니다.

```bash
curl https://api-testnet.cryptostone.org/v1/token/balance/0xUserWallet
```

Example response:

```json
{
  "wallet": "0xUserWallet",
  "symbol": "STONX",
  "balance": "0",
  "displayBalance": "0 STONX"
}
```

#### `GET /token/allowance/:walletAddress/:spenderAddress`

특정 지갑이 Pool 또는 컨트랙트에 승인한 STONX 수량을 조회합니다.

```bash
curl https://api-testnet.cryptostone.org/v1/token/allowance/0xUserWallet/0xPoolAddress
```

Example response:

```json
{
  "wallet": "0xUserWallet",
  "spender": "0xPoolAddress",
  "symbol": "STONX",
  "allowance": "0",
  "displayAllowance": "0 STONX"
}
```

### 6. Mining Pool API

#### `GET /pools`

공식 Gemstone Mining Pool 목록을 조회합니다.

```bash
curl https://api-testnet.cryptostone.org/v1/pools
```

Example response:

```json
{
  "pools": [
    {
      "poolId": 1,
      "stoneType": "Diamond",
      "poolAddress": "",
      "totalStaked": "0",
      "displayTotalStaked": "0 STONX",
      "difficulty": "0",
      "remainingGemSupply": "0",
      "status": "testing"
    }
  ]
}
```

#### `GET /pools/:stoneType`

특정 원석 Pool의 상세 정보를 조회합니다.

```bash
curl https://api-testnet.cryptostone.org/v1/pools/Diamond
```

Example response:

```json
{
  "stoneType": "Diamond",
  "poolAddress": "",
  "tokenSymbol": "STONX",
  "totalStaked": "0",
  "miningDifficulty": "0",
  "scarcityMultiplier": "0",
  "claimRule": "testnet",
  "remainingGemSupply": "0"
}
```

#### `GET /pools/:stoneType/stakers/:walletAddress`

사용자가 특정 Pool에 스테이킹한 상태를 조회합니다.

```bash
curl https://api-testnet.cryptostone.org/v1/pools/Diamond/stakers/0xUserWallet
```

Example response:

```json
{
  "wallet": "0xUserWallet",
  "stoneType": "Diamond",
  "stakedAmount": "0",
  "displayStakedAmount": "0 STONX",
  "miningPower": "0",
  "proofOfMining": "0",
  "claimable": false
}
```

### 7. Wallet / Mining Status API

#### `GET /wallet/:walletAddress`

사용자 지갑의 Crypto Stone Protocol 요약 상태를 조회합니다.

```bash
curl https://api-testnet.cryptostone.org/v1/wallet/0xUserWallet
```

Example response:

```json
{
  "wallet": "0xUserWallet",
  "stonxBalance": "0",
  "totalStaked": "0",
  "totalMiningPower": "0",
  "totalProofOfMining": "0",
  "gemNFTBalance": 0
}
```

#### `GET /wallet/:walletAddress/mining-power`

사용자 지갑의 전체 Mining Power를 조회합니다.

```bash
curl https://api-testnet.cryptostone.org/v1/wallet/0xUserWallet/mining-power
```

#### `GET /wallet/:walletAddress/proof-of-mining`

사용자 지갑의 Proof of Mining 누적값을 조회합니다.

```bash
curl https://api-testnet.cryptostone.org/v1/wallet/0xUserWallet/proof-of-mining
```

#### `GET /wallet/:walletAddress/claimable`

사용자 지갑이 Claim 가능한 Gem NFT 목록을 조회합니다.

```bash
curl https://api-testnet.cryptostone.org/v1/wallet/0xUserWallet/claimable
```

Example response:

```json
{
  "wallet": "0xUserWallet",
  "claimable": [
    {
      "stoneType": "Diamond",
      "poolAddress": "",
      "requiredProofOfMining": "0",
      "currentProofOfMining": "0",
      "canClaim": false
    }
  ]
}
```

### 8. Gem NFT API

#### `GET /nfts/:tokenId`

특정 Gem NFT의 상세 정보를 조회합니다.

```bash
curl https://api-testnet.cryptostone.org/v1/nfts/1
```

Example response:

```json
{
  "tokenId": "1",
  "owner": "0xOwnerWallet",
  "stoneType": "Diamond",
  "rarity": "Legendary",
  "grade": "",
  "weight": "",
  "color": "",
  "clarity": "",
  "cut": "",
  "miningPool": "",
  "minedAtBlock": 0,
  "metadataURI": ""
}
```

#### `GET /nfts/owner/:walletAddress`

특정 지갑이 보유한 Gem NFT 목록을 조회합니다.

```bash
curl https://api-testnet.cryptostone.org/v1/nfts/owner/0xUserWallet
```

#### `GET /nfts/:tokenId/rarity`

특정 Gem NFT의 희소도 정보를 조회합니다.

```bash
curl https://api-testnet.cryptostone.org/v1/nfts/1/rarity
```

#### `GET /nfts/:tokenId/history`

특정 Gem NFT의 채굴, 전송, 소유권 변경 이력을 조회합니다.

```bash
curl https://api-testnet.cryptostone.org/v1/nfts/1/history
```

### 9. Transaction Builder API

아래 API는 실제 트랜잭션을 서버에서 실행하지 않습니다.\
사용자 지갑이 서명할 수 있는 unsigned transaction data를 생성하는 용도입니다.

#### `POST /tx/approve`

STONX를 Pool 컨트랙트에 승인하기 위한 트랜잭션 데이터를 생성합니다.

```bash
curl -X POST https://api-testnet.cryptostone.org/v1/tx/approve \
  -H "Content-Type: application/json" \
  -d '{"spender":"","amount":"1000000000000000000"}'
```

#### `POST /tx/stake`

Mining Pool에 STONX를 스테이킹하기 위한 트랜잭션 데이터를 생성합니다.

```bash
curl -X POST https://api-testnet.cryptostone.org/v1/tx/stake \
  -H "Content-Type: application/json" \
  -d '{"stoneType":"Diamond","amount":"1000000000000000000"}'
```

#### `POST /tx/unstake`

스테이킹된 STONX를 언스테이킹하기 위한 트랜잭션 데이터를 생성합니다.

```bash
curl -X POST https://api-testnet.cryptostone.org/v1/tx/unstake \
  -H "Content-Type: application/json" \
  -d '{"stoneType":"Diamond","amount":"1000000000000000000"}'
```

#### `POST /tx/claim-gem`

Claim 가능한 Gem NFT를 발행하기 위한 트랜잭션 데이터를 생성합니다.

```bash
curl -X POST https://api-testnet.cryptostone.org/v1/tx/claim-gem \
  -H "Content-Type: application/json" \
  -d '{"stoneType":"Diamond","wallet":"0xUserWallet"}'
```

#### `POST /tx/transfer-nft`

Gem NFT를 다른 지갑으로 전송하기 위한 트랜잭션 데이터를 생성합니다.

```bash
curl -X POST https://api-testnet.cryptostone.org/v1/tx/transfer-nft \
  -H "Content-Type: application/json" \
  -d '{"tokenId":"1","from":"0xUserWallet","to":"0xReceiverWallet"}'
```

### 10. Events / Indexer API

#### `GET /events`

컨트랙트 이벤트 로그를 조회합니다.

```bash
curl "https://api-testnet.cryptostone.org/v1/events?contract=MiningPool&event=Staked&fromBlock=0&toBlock=latest"
```

#### `GET /indexer/status`

Indexer 동기화 상태를 조회합니다.

```bash
curl https://api-testnet.cryptostone.org/v1/indexer/status
```

Example response:

```json
{
  "network": "sepolia",
  "latestIndexedBlock": 0,
  "latestChainBlock": 0,
  "synced": false,
  "status": "testing"
}
```

### 11. 외부 확장 예시

Crypto Stone API를 통해 외부 서비스는 다음 기능을 만들 수 있습니다.

| 확장 서비스                  | 활용 API                                                              |
| ----------------------- | ------------------------------------------------------------------- |
| Wallet Dashboard        | `/wallet/:walletAddress`, `/token/balance/:walletAddress`           |
| Mining Dashboard        | `/pools`, `/pools/:stoneType/stakers/:walletAddress`                |
| Gem NFT Explorer        | `/nfts/:tokenId`, `/nfts/owner/:walletAddress`                      |
| Rarity Ranking          | `/nfts/:tokenId/rarity`, `/events`                                  |
| Game Module             | `/wallet/:walletAddress/mining-power`, `/nfts/owner/:walletAddress` |
| Marketplace Integration | `/nfts/:tokenId`, `/nfts/:tokenId/history`                          |
| Partner App             | `/contracts`, `/abi/:contractName`, `/tx/*`                         |
