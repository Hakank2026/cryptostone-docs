# 37 Struktur pengembangan

CryptoStone mengadopsi struktur berikut.

* STONX Token
* CryptoStone Gem NFT
* 12 Mining Pool Contracts
* Pool Factory

Struktur ini dirancang untuk menerapkan protokol batu permata digital yang tidak bergantung secara permanen pada chain tertentu. Pada tahap awal, jaringan smart contract yang kompatibel dengan EVM digunakan sebagai Launch Network.

## Current Deployment Status

Tabel berikut merangkum status deployment testnet saat ini dan baseline dokumen protokol. Jika mainnet deployment atau contract upgrade dilakukan, alamat dan versi akan diperbarui dalam dokumentasi publik terpisah.

| Item | Current Status | Notes |
| ---- | -------------- | ----- |
| Launch Network | Ethereum Sepolia | Baseline operasi testnet |
| STONX Token | `0xBd10DA40Dec511c11100dd2927dDf8c53A5248Ed` | Deployment ERC-20 testnet |
| GEMS NFT | `0x01CE9e3Ee0fb51B6b0cE1E5B3C72A5F981A50056` | Struktur HTTPS metadata V5.3 |
| Garnet Mining Pool | `0xd885D9865A1e7C9094EcD0982421bE9670Fabe16` | Pool live saat ini |
| Other 11 Mining Pools | Preparing | Target mainnet atau pembukaan bertahap |
| Refinery | `0xB7b55068163d6d8E4f8eD2e8B511e234520576DC` | Fitur refinement testnet |
| Marketplace | `0x673d64550c718A3770064ee3cDdC8b20093D0913` | Fitur perdagangan NFT testnet |
| Metadata Model | HTTPS API + watcher finalization + IPFS media | Memisahkan atribut inti dari layer tampilan media |
| Randomness Standard | User entropy + multi-block entropy + `prevrandao` | Baseline pool baru dan upgrade |
| Mainnet Status | Preparing | Dilanjutkan setelah security review, penyelarasan dokumentasi, dan finalisasi kebijakan liquidity |

## Rationale

| Choice | Reason |
| ------ | ------ |
| STONX Token | Menyediakan resource mining dan struktur liquidity terpadu |
| CryptoStone Gem NFT | Merepresentasikan keunikan dan atribut setiap batu |
| 12 Mining Pools | Menerapkan tambang digital independen untuk setiap stone |
| Pool Factory | Mendeploy pool dari template terverifikasi yang sama |
| Unified NFT Contract | Mengonsentrasikan identitas collection dan data trading |
| Verifiable Randomness | Memungkinkan generasi atribut tanpa manipulasi operator |
| Finalize Mechanism | Mencegah perubahan aturan inti |

Pertama, peran STONX dan Gem NFT dipisahkan. STONX adalah token untuk Mining Power, sedangkan Gem NFT adalah hasil mining.

Kedua, keunikan batu permata dilindungi. Setiap Gem NFT memiliki tokenId dan kombinasi atribut, dan atributnya tidak dapat diubah setelah minting.

Ketiga, independensi antarstone dipertahankan. Setiap mining pool memiliki supply, mining interval, dan struktur halving sendiri, sehingga cocok untuk merepresentasikan tambang individual dunia nyata dalam bentuk digital.

Keempat, NFT collection tetap terpadu. Ini mengonsentrasikan brand dan data pasar CryptoStone, memungkinkan pengelolaan trading dan ranking rarity secara terpadu.

Kelima, struktur ini memiliki ekstensibilitas masa depan yang kuat. CryptoStone dapat mulai pada Launch Network kompatibel EVM dan kemudian berkembang menjadi Appchain atau CryptoStone Mainnet independen.

Keenam, ketergantungan terpusat dikurangi. Mining dan minting dieksekusi oleh contract, bukan server, dan siapa pun dapat memverifikasi kondisinya.
