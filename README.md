# NIPs

NIPsは、**Nostr Implementation Possibilities**の略称である。

本文書は、[Nostr](https://github.com/nostr-protocol/nostr)互換のリレーおよびクライアントソフトウェアによって実装されうるものを文書化するために存在している。

---

- [仕様一覧](#list)
- [イベント種別(kind)](#event-kinds)
- [メッセージ型](#message-types)
  - [クライアントからリレーへ](#client-to-relay)
  - [リレーからクライアントへ](#relay-to-client)
- [標準化済みタグ](#standardized-tags)
- [NIPsの受け入れ基準](#criteria-for-acceptance-of-nips)
- [このリポジトリは中央集権的な要素ではありませんか？](#is-this-repository-a-centralizing-factor)
- [このリポジトリの仕組み](#how-this-repository-works)
- [License](#license)

---

## 仕様一覧

- [NIP-01: 基本的なプロトコルフローの説明](01.md)
- [NIP-02: フォローリスト](02.md)
- [NIP-03: イベントに対するOpenTimestamps認証](03.md)
- [NIP-04: 暗号化されたダイレクトメッセージ](04.md)
- [NIP-05: Nostr鍵をDNSベースのインターネット識別子に結びつける](05.md)
- [NIP-06: ニーモニックシードフレーズからの基本的な鍵導出](06.md)
- [NIP-07: Web ブラウザ向け`window.nostr`機能](07.md)
- [NIP-08: メンションへの対応](08.md) --- **非推奨**: [NIP-27](27.md)で代替されたため廃止
- [NIP-09: イベント削除](09.md)
- [NIP-10: テキストイベントにおいて`e`タグおよび`p`タグを使用する際の規約](10.md)
- [NIP-11: リレー情報ドキュメント](11.md)
- [NIP-13: Proof of Work](13.md)
- [NIP-14: テキストイベントにおける件名タグ](14.md)
- [NIP-15: Nostr Marketplace (for resilient marketplaces)](15.md)
- [NIP-18: リポスト](18.md)
- [NIP-19: bech32でエンコードされた情報](19.md)
- [NIP-21: `nostr:` URI scheme](21.md)
- [NIP-23: 長文投稿](23.md)
- [NIP-24: 追加のメタデータフィールドとタグ](24.md)
- [NIP-25: リアクション](25.md)
- [NIP-26: イベント署名の委任](26.md)
- [NIP-27: テキストノートへの参照](27.md)
- [NIP-28: パブリックチャット](28.md)
- [NIP-30: カスタム絵文字](30.md)
- [NIP-31: 未知のイベントに対する対処法](31.md)
- [NIP-32: ラベル付け](32.md)
- [NIP-36: センシティブコンテンツ / コンテンツの警告](36.md)
- [NIP-38: ユーザーステータス](38.md)
- [NIP-39: プロフィールにおける外部アイデンティティ](39.md)
- [NIP-40: 有効期限タイムスタンプ](40.md)
- [NIP-42: リレーに対するクライアントの認証](42.md)
- [NIP-45: イベント計数](45.md)
- [NIP-46: Nostrコネクト](46.md)
- [NIP-47: Wallet Connect](47.md)
- [NIP-48: プロキシタグ](48.md)
- [NIP-50: 検索機能](50.md)
- [NIP-51: リスト](51.md)
- [NIP-52: カレンダーイベント](52.md)
- [NIP-53: ライブアクティビティ](53.md)
- [NIP-56: 通報](56.md)
- [NIP-57: Lightning Zaps](57.md)
- [NIP-58: バッジ](58.md)
- [NIP-65: リレーリストメタデータ](65.md)
- [NIP-72: Moderated Communities](72.md)
- [NIP-75: Zap Goals](75.md)
- [NIP-78: アプリケーション固有データ](78.md)
- [NIP-84: ハイライト](84.md)
- [NIP-89: 推奨アプリケーションハンドラ](89.md)
- [NIP-90: データ自動販売機](90.md)
- [NIP-94: ファイルメタデータ](94.md)
- [NIP-98: HTTP認証](98.md)
- [NIP-99: Classified Listings](99.md)

## イベント種別(kind)
| kind          | 説明                            | NIP                      |
| ------------- | ------------------------------- | -----------              |
| `0`           | メタデータ                      | [1](01.md)               |
| `1`           | 短文ノート                      | [1](01.md)               |
| `2`           | 推奨リレー                      |                          |
| `3`           | フォロー                        | [2](02.md)               |
| `4`           | 暗号化されたダイレクトメッセージ| [4](04.md)               |
| `5`           | 削除イベント                    | [9](09.md)               |
| `6`           | リポスト                        | [18](18.md)              |
| `7`           | リアクション                    | [25](25.md)              |
| `8`           | バッジ・表彰                    | [58](58.md)              |
| `16`          | 汎用リポスト                    | [18](18.md)              |
| `40`          | チャンネル作成                  | [28](28.md)              |
| `41`          | チャンネルメタデータ            | [28](28.md)              |
| `42`          | チャンネルメッセージ            | [28](28.md)              |
| `43`          | チャンネル投稿ミュート          | [28](28.md)              |
| `44`          | チャンネルユーザミュート        | [28](28.md)              |
| `1040`        | OpenTimestamps                  | [03](03.md)              |
| `1063`        | ファイルメタデータ              | [94](94.md)              |
| `1311`        | ライブチャットメッセージ        | [53](53.md)              |
| `1971`        | 問題トラッカー                  | [nostrocket][nostrocket] |
| `1984`        | 通報                            | [56](56.md)              |
| `1985`        | ラベル                          | [32](32.md)              |
| `4550`        | コミュニティ投稿の承認          | [72](72.md)              |
| `5000`-`5999` | ジョブ要求                      | [90](90.md)              |
| `6000`-`6999` | ジョブ結果                      | [90](90.md)              |
| `7000`        | ジョブフィードバック            | [90](90.md)              |
| `9041`        | Zap Goal                        | [75](75.md)              |
| `9734`        | Zap 要求                        | [57](57.md)              |
| `9735`        | Zap                             | [57](57.md)              |
| `9802`        | ハイライト                      | [84](84.md)              |
| `10000`       | ミュートリスト                  | [51](51.md)              |
| `10001`       | ピン留めリスト                  | [51](51.md)              |
| `10002`       | リレーリストメタデータ          | [65](65.md)              |
| `10003`       | ブックマークリスト              | [51](51.md)              |
| `10004`       | コミュニティリスト              | [51](51.md)              |
| `10005`       | パブリックチャットリスト        | [51](51.md)              |
| `10006`       | ブロック済みリレーリスト        | [51](51.md)              |
| `10007`       | 検索リレーリスト                | [51](51.md)              |
| `10015`       | 興味・関心リスト                | [51](51.md)              |
| `10030`       | ユーザー絵文字リスト            | [51](51.md)              |
| `13194`       | ウォレット 情報                 | [47](47.md)              |
| `21000`       | Lightning Pub RPC               | [Lightning.Pub][lnpub]   |
| `22242`       | クライアント認証                | [42](42.md)              |
| `23194`       | ウォレット 要求                 | [47](47.md)              |
| `23195`       | ウォレット 応答                 | [47](47.md)              |
| `24133`       | Nostr Connect                   | [46](46.md)              |
| `27235`       | HTTP 認証                       | [98](98.md)              |
| `30000`       | フォローセット                  | [51](51.md)              |
| `30001`       | 汎用リスト                      | [51](51.md)              |
| `30002`       | リレーセット                    | [51](51.md)              |
| `30003`       | ブックマークセット              | [51](51.md)              |
| `30004`       | キュレーションセット            | [51](51.md)              |
| `30008`       | プロフィールバッジ              | [58](58.md)              |
| `30009`       | バッジ定義                      | [58](58.md)              |
| `30015`       | 興味・関心セット                | [51](51.md)              |
| `30017`       | Create or update a stall        | [15](15.md)              |
| `30018`       | Create or update a product      | [15](15.md)              |
| `30023`       | 長文投稿                        | [23](23.md)              |
| `30024`       | 長文投稿の下書き                | [23](23.md)              |
| `30030`       | 絵文字セット                    | [51](51.md)              |
| `30078`       | アプリケーション固有データ      | [78](78.md)              |
| `30311`       | ライブイベント                  | [53](53.md)              |
| `30315`       | ユーザーステータス              | [38](38.md)              |
| `30402`       | Classified Listing              | [99](99.md)              |
| `30403`       | Classified Listing              | [99](99.md)              |
| `31922`       | 日付指定のカレンダーイベント    | [52](52.md)              |
| `31923`       | 時刻指定のカレンダーイベント    | [52](52.md)              |
| `31924`       | カレンダー                      | [52](52.md)              |
| `31925`       | 要返信のカレンダーイベント      | [52](52.md)              |
| `31989`       | 推奨ハンドラ                    | [89](89.md)              |
| `31990`       | ハンドラ情報                    | [89](89.md)              |
| `34550`       | Community Definition            | [72](72.md)              |

[nostrocket]: https://github.com/nostrocket/NIPS/blob/main/Problems.md
[lnpub]: https://github.com/shocknet/Lightning.Pub/blob/master/proto/autogenerated/client.md

## メッセージ型

### クライアントからリレーへ

| type    | 説明                                                | NIP         |
| ------- | --------------------------------------------------- | ----------- |
| `EVENT` | イベントの配信                                      | [01](01.md) |
| `REQ`   | イベントの要求と新規更新の購読                      | [01](01.md) |
| `CLOSE` | 既存の購読の中止                                    | [01](01.md) |
| `AUTH`  | 認証イベント                                        | [42](42.md) |
| `COUNT` | イベント計数要求                                    | [45](45.md) |

### リレーからクライアントへ

| type     | description                                             | NIP         |
| -------- | ------------------------------------------------------- | ----------- |
| `EOSE`   | クライアントへのすべての保存済みイベントの送信完了通知  | [01](01.md) |
| `EVENT`  | クライアントから要求されたイベントの送信                | [01](01.md) |
| `NOTICE` | クライアントへの人間可読なメッセージ                    | [01](01.md) |
| `OK`     | クライアントへのイベント配信成功通知                    | [01](01.md) |
| `CLOSED` | クライアントへの購読終了とその理由の通知                | [01](01.md) |
| `AUTH`   | 認証チャレンジの送信                                    | [42](42.md) |
| `COUNT`  | 要求されたイベントの計数結果                            | [45](45.md) |

新しいイベント種別(kind)を含むNIPsを提案する場合は、これらのリストも更新すること。

## 標準化済みタグ

| タグ名            | 値                                   | その他パラメータ      | NIP                                  |
| ----------------- | ------------------------------------ | -------------------- | ------------------------------------- |
| `e`               | イベントID (hex)                     | relay URL, marker    | [01](01.md), [10](10.md)              |
| `p`               | 公開鍵 (hex)                         | relay URL, petname   | [01](01.md), [02](02.md)              |
| `a`               | coordinates to an event              | relay URL            | [01](01.md)                           |
| `d`               | 識別子                               | --                   | [01](01.md)                           |
| `g`               | ジオハッシュ                         | --                   | [52](52.md)                           |
| `i`               | アイデンティティ                     | proof                | [39](39.md)                           |
| `k`               | 種別(kind)番号 (string)              | --                   | [18](18.md), [25](25.md), [72](72.md) |
| `l`               | ラベル, ラベル名前空間               | annotations          | [32](32.md)                           |
| `L`               | ラベル名前空間                       | --                   | [32](32.md)                           |
| `m`               | MIME type                            | --                   | [94](94.md)                           |
| `r`               | 参照 (URL, etc)                      | petname              |                                       |
| `r`               | リレーURL                            | marker               | [65](65.md)                           |
| `t`               | ハッシュタグ                         | --                   |                                       |
| `alt`             | 概要                                 | --                   | [31](31.md)                           |
| `amount`          | 文字列化されたミリサトシ             | --                   | [57](57.md)                           |
| `bolt11`          | `bolt11` インボイス                  | --                   | [57](57.md)                           |
| `challenge`       | チャレンジ文字列                     | --                   | [42](42.md)                           |
| `client`          | 名前, アドレス                       | relay URL            | [89](89.md)                           |
| `content-warning` | 理由                                 | --                   | [36](36.md)                           |
| `delegation`      | 公開鍵, 条件, 委任トークン           | --                   | [26](26.md)                           |
| `description`     | インボイス/バッジの説明              | --                   | [57](57.md), [58](58.md)              |
| `emoji`           | ショートコード, 画像 URL             | --                   | [30](30.md)                           |
| `encrypted`       | --                                   | --                   | [90](90.md)                           |
| `expiration`      | unix timestamp (string)              | --                   | [40](40.md)                           |
| `goal`            | イベントID (hex)                     | relay URL            | [75](75.md)                           |
| `image`           | 画像 URL                             | dimensions in pixels | [23](23.md), [58](58.md)              |
| `lnurl`           | `bech32` encoded `lnurl`             | --                   | [57](57.md)                           |
| `location`        | 場所文字列                           | --                   | [52](52.md), [99](99.md)              |
| `name`            | バッジの名前                         | --                   | [58](58.md)                           |
| `nonce`           | 乱数                                 | --                   | [13](13.md)                           |
| `preimage`        | `bolt11` インボイスのハッシュ        | --                   | [57](57.md)                           |
| `price`           | 値段                                 | currency, frequency  | [99](99.md)                           |
| `proxy`           | 外部ID                               | protocol             | [48](48.md)                           |
| `published_at`    | unix timestamp (string)              | --                   | [23](23.md)                           |
| `relay`           | リレーURL                            | --                   | [42](42.md)                           |
| `relays`          | リレーリスト                         | --                   | [57](57.md)                           |
| `subject`         | 件名                                 | --                   | [14](14.md)                           |
| `summary`         | 記事の要約                           | --                   | [23](23.md)                           |
| `thumb`           | バッジサムネイル                     | dimensions in pixels | [58](58.md)                           |
| `title`           | 記事のタイトル                       | --                   | [23](23.md)                           |
| `zap`             | 公開鍵 (hex), リレー URL             | weight               | [57](57.md)                           |

## NIPsの受け入れ基準

1. (適用可能であれば)少なくとも2つのクライアントと1つのリレーが実装しているべきである。
2. 理にかなっている必要がある。
3. 任意に実装可能であり、後方互換性を有するべきである: 実装しないことを選択したクライアントやリレーが、実装することを選択したクライアントやリレーと通信した際に動作を停止しないよう厳に注意しなければならない。
4. 同じことする方法が複数あってはならない。
5. その他のルールは必要に応じて作成する。

## このリポジトリは中央集権的な要素ではありませんか？

To promote interoperability, we standards that everybody can follow, and we need them to define a **single way of doing each thing** without ever hurting **backwards-compatibility**, and for that purpose there is no way around getting everybody to agree on the same thing and keep a centralized index of these standards. However the fact that such index exists doesn't hurt the decentralization of Nostr. _At any point the central index can be challenged if it is failing to fulfill the needs of the protocol_ and it can migrate to other places and be maintained by other people.

It can even fork into multiple and then some clients would go one way, others would go another way, and some clients would adhere to both competing standards. This would hurt the simplicity, openness and interoperability of Nostr a little, but everything would still work in the short term.

There is a list of notable Nostr software developers who have commit access to this repository, but that exists mostly for practical reasons, as by the nature of the thing we're dealing with the repository owner can revoke membership and rewrite history as they want -- and if these actions are unjustified or perceived as bad or evil the community must react.

## このリポジトリの仕組み

Standards may emerge in two ways: the first way is that someone starts doing something, then others copy it; the second way is that someone has an idea of a new standard that could benefit multiple clients and the protocol in general without breaking **backwards-compatibility** and the principle of having **a single way of doing things**, then they write that idea and submit it to this repository, other interested parties read it and give their feedback, then once most people reasonably agree we codify that in a NIP which client and relay developers that are interested in the feature can proceed to implement.

These two ways of standardizing things are supported by this repository. Although the second is preferred, an effort will be made to codify standards emerged outside this repository into NIPs that can be later referenced and easily understood and implemented by others -- but obviously as in any human system discretion may be applied when standards are considered harmful.

## License

All NIPs are public domain.

## Contributors

<a align="center" href="https://github.com/nostr-protocol/nips/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=nostr-protocol/nips" />
</a>
