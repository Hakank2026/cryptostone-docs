# 40 メタデータ構造

CryptoStone Gem NFTの本質は画像そのものではなく、宝石を表現する属性データにある。

| Attribute | Example |
| --------- | ------- |
| `stoneType` | Garnet, Ruby, Sapphire |
| `weight` | 3.42 CT |
| `color` | D, E, F, Gなど |
| `clarity` | FL, IF, VVS1など |
| `cut` | 1 Star ~ 6 Star |
| `rarity` | Common, Rare, Epic, Legendary, Genesisのいずれか |
| `minedAt` | 採掘ブロックまたは時刻 |
| `pool` | Mining pool address |
| `generation` | 原本または精錬世代 |

CryptoStoneは、NFTの基本メタデータをHTTPS metadata APIを通じて提供できる。この方式により、ミント直後でもユーザーはウォレットやマーケットプレイスで名前、説明、属性、等級、tokenIdを素早く確認できる。

## 40.1 Metadata Trust Model

CryptoStoneのメタデータ構造は、核心属性と表示レイヤーを分離する。宝石の本質的属性はコントラクトと公開検証可能なデータによって決定され、HTTPS metadata APIはそれをウォレット、マーケットプレイス、フロントエンドが読みやすいJSON形式で提供する。

| レイヤー | 役割 | 信頼基準 |
| -------- | ---- | -------- |
| Smart Contract | mint、所有権、tokenId、核心属性を決定 | オンチェーン検証 |
| HTTPS Metadata API | name、description、attributes、media URLをJSONで提供 | 公開レスポンスと決定論的属性マッピング |
| Watcher Finalization | 画像・動画生成、IPFSアップロード、メタデータ応答更新 | 公開ログとtokenId基準マッピング |
| IPFS Media | 画像・動画ファイル保存 | コンテンツアドレス型メディア検証 |

画像と動画はwatcher finalizationプロセスが後続で生成し、IPFSにアップロードした後、メタデータAPIとJSON応答を更新する。この過程はユーザーの追加ウォレット確認を必要としない。ユーザーがウォレットで承認すべき核心トランザクションはclaimまたはrefinement実行段階に限定される。

このため、CryptoStone Gem NFTは技術的検証可能性と視覚的表現を同時に維持できる。宝石は画像だけで定義されない。画像はオンチェーンおよびメタデータ属性の視覚的表現であり、属性そのものが収集価値を定義する。

IPFSアップロードやメディア生成が遅延しても、Gem NFTの核心属性はコントラクトとHTTPS metadata APIを通じて先に確認できる必要がある。その後watcherがIPFS image/video dataを補完すると、NFTマーケットプレイスとウォレットUIは更新されたメディアを表示できる。

この設計は、ユーザーがメタデータ最終化のために追加ウォレット確認を繰り返さないようにするためのものである。また、画像サーバーやAPIが一時的に遅延しても、CryptoStone NFTの核心属性はオンチェーンまたは公開検証可能なデータ構造に残るべきである。
