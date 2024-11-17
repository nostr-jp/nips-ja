# NIPs

NIPsは、**Nostr Implementation Possibilities**の略称である。

本文書は、[Nostr](https://github.com/nostr-protocol/nostr)互換のリレーおよびクライアントソフトウェアによって実装されうるものを文書化するために存在している。

---

- [仕様一覧](#仕様一覧)
- [イベント種別(kind)](#イベント種別kind)
- [メッセージ型](#メッセージ型)
  - [クライアントからリレーへ](#クライアントからリレーへ)
  - [リレーからクライアントへ](#リレーからクライアントへ)
- [標準化済みタグ](#標準化済みタグ)
- [NIPsの受け入れ基準](#NIPsの受け入れ基準)
- [このリポジトリは中央集権的な要素ではありませんか？](#このリポジトリは中央集権的な要素ではありませんか)
- [このリポジトリの仕組み](#このリポジトリの仕組み)
- [破壊的変更](#破壊的変更)
- [ライセンス](#ライセンス)

---

## 仕様一覧

- [NIP-01: 基本的なプロトコルフローの説明](01.md)
- [NIP-02: フォローリスト](02.md)
- [NIP-03: イベントに対するOpenTimestamps認証](03.md)
- [NIP-04: 暗号化されたダイレクトメッセージ](04.md) --- **非推奨**: [NIP-17](17.md)で代替されたため廃止
- [NIP-05: Nostr鍵をDNSベースのインターネット識別子に結びつける](05.md)
- [NIP-06: ニーモニックシードフレーズからの基本的な鍵導出](06.md)
- [NIP-07: Webブラウザ向け`window.nostr`機能](07.md)
- [NIP-08: メンションへの対応](08.md) --- **非推奨**: [NIP-27](27.md)で代替されたため廃止
- [NIP-09: イベント(の)削除リクエスト](09.md)
- [NIP-10: テキストイベントにおいて`e`タグおよび`p`タグを使用する際の規約](10.md)
- [NIP-11: リレー情報ドキュメント](11.md)
- [NIP-13: Proof of Work](13.md)
- [NIP-14: テキストイベントにおける件名タグ](14.md)
- [NIP-15: Nostr Marketplace (for resilient marketplaces)](15.md)
- [NIP-17: プライベートダイレクトメッセージ](17.md)
- [NIP-18: リポスト](18.md)
- [NIP-19: bech32でエンコードされた情報](19.md)
- [NIP-21: `nostr:` URIスキーム](21.md)
- [NIP-22: コメント](22.md)
- [NIP-23: 長文投稿](23.md)
- [NIP-24: 追加のメタデータフィールドとタグ](24.md)
- [NIP-25: リアクション](25.md)
- [NIP-26: イベント署名の委任](26.md)
- [NIP-27: テキストノートへの参照](27.md)
- [NIP-28: パブリックチャット](28.md)
- [NIP-29: リレーに基づくグループ](29.md)
- [NIP-30: カスタム絵文字](30.md)
- [NIP-31: 未知のイベントに対する対処法](31.md)
- [NIP-32: ラベル付け](32.md)
- [NIP-34: `git` のもの](34.md)
- [NIP-35: Torrents](35.md)
- [NIP-36: センシティブコンテンツ / コンテンツの警告](36.md)
- [NIP-38: ユーザーステータス](38.md)
- [NIP-39: プロフィールにおける外部アイデンティティ](39.md)
- [NIP-40: 有効期限タイムスタンプ](40.md)
- [NIP-42: リレーに対するクライアントの認証](42.md)
- [NIP-44: バージョンつき暗号化](44.md)
- [NIP-45: イベント計数](45.md)
- [NIP-46: Nostrコネクト](46.md)
- [NIP-47: Wallet Connect](47.md)
- [NIP-48: プロキシタグ](48.md)
- [NIP-49: 秘密鍵暗号化](49.md)
- [NIP-50: 検索機能](50.md)
- [NIP-51: リスト](51.md)
- [NIP-52: カレンダーイベント](52.md)
- [NIP-53: ライブアクティビティ](53.md)
- [NIP-54: Wiki](54.md)
- [NIP-55: アンドロイド署名アプリ](55.md)
- [NIP-56: 通報](56.md)
- [NIP-57: Lightning Zaps](57.md)
- [NIP-58: バッジ](58.md)
- [NIP-59: Gift Wrap](59.md)
- [NIP-60: カシューウォレット](60.md)
- [NIP-61: ナッツzaps](61.md)
- [NIP-64: チェス (PGN)](64.md)
- [NIP-65: リレーリストメタデータ](65.md)
- [NIP-72: Moderated Communities](72.md)
- [NIP-73: External Content IDs](73.md)
- [NIP-75: Zap Goals](75.md)
- [NIP-78: アプリケーション固有データ](78.md)
- [NIP-84: ハイライト](84.md)
- [NIP-89: 推奨アプリケーションハンドラ](89.md)
- [NIP-90: データ自動販売機](90.md)
- [NIP-92: Media Attachments](92.md)
- [NIP-94: ファイルメタデータ](94.md)
- [NIP-96: HTTPファイルストレージインテグレーション](96.md)
- [NIP-98: HTTP認証](98.md)
- [NIP-99: Classified Listings](99.md)

## Event Kinds

| kind          | description                | NIP                      |
| ------------- | -------------------------- | ------------------------ |
| `0`           | ユーザーメタデータ                   | [01](01.md)              |
| `1`           | 短文ノート            | [01](01.md)              |
| `2`           | 推奨リレー            | 01 (非推奨)          |
| `3`           | フォロー                    | [02](02.md)              |
| `4`           | 暗号化されたダイレクトメッセージ  | [04](04.md)              |
| `5`           | 削除イベント             | [09](09.md)              |
| `6`           | リポスト                     | [18](18.md)              |
| `7`           | リアクション                   | [25](25.md)              |
| `8`           | バッジ・表彰                | [58](58.md)              |
| `9`           | グループチャットメッセージ         | [29](29.md)              |
| `10`          | グループチャットスレッドリプライ  | 29 (非推奨)              |
| `11`          | グループスレッド               | [29](29.md)              |
| `12`          | グループスレッドリプライ         | 29 (非推奨)              |
| `13`          | 封緘                       | [59](59.md)              |
| `14`          | ダイレクトメッセージ | [17](17.md) |
| `16`          | 汎用リポスト             | [18](18.md)              |
| `17`          | webサイトへのリアクション | [25](25.md)
| `40`          | チャンネル作成           | [28](28.md)              |
| `41`          | チャンネルメタデータ           | [28](28.md)              |
| `42`          | チャンネルメッセージ            | [28](28.md)              |
| `43`          | チャンネル投稿ミュート       | [28](28.md)              |
| `44`          | チャンネルユーザミュート          | [28](28.md)              |
| `64`          | チェス (PGN) | [64](64.md) |
| `818`         | マージリクエスト  | [54](54.md) |
| `1021`        | Bid                        | [15](15.md)              |
| `1022`        | Bid confirmation           | [15](15.md)              |
| `1040`        | OpenTimestamps             | [03](03.md)              |
| `1059`        | Gift Wrap                  | [59](59.md)              |
| `1063`        | ファイルメタデータ              | [94](94.md)              |
| `1111`        | コメント                  | [22](22.md)  |
| `1311`        | ライブチャットメッセージ          | [53](53.md)              |
| `1617`        | Patches                    | [34](34.md)              |
| `1621`        | Issues                     | [34](34.md)              |
| `1622`        | Replies                    | [34](34.md)              |
| `1630`-`1633` | ステータス    |[34](34.md)
| `1971`        | 問題トラッカー            | [nostrocket][nostrocket] |
| `1984`        | 通報                  | [56](56.md)              |
| `1985`        | ラベル                      | [32](32.md)              |
| `1986`        | リレーレビュー    |
| `1987`        | AI埋め込み / ベクターリスト | [NKBIP-02] |
| `2003`        | Torrent                         | [35](35.md) |
| `2004`        | Torrentコメント | [35](35.md) |
| `2022`        | コインジョインプール | [joinstr][joinstr] |
| `4550`        | コミュニティ投稿の承認    | [72](72.md)              |
| `5000`-`5999` | ジョブ要求                | [90](90.md)              |
| `6000`-`6999` | ジョブ結果                 | [90](90.md)              |
| `7000`        | ジョブフィードバック               | [90](90.md)              |
| `7374`        | 逆カシューウォレットトークン | [60](60.md) |
| `7375`        | カシューウォレットトークン | [60](60.md) |
| `7376`        |カシューウォレットヒストリー | [60](60.md) |
| `9000`-`9030` | Group Control Events       | [29](29.md)              |
| `9041`        | Zap Goal                   | [75](75.md)              |
| `9321`        | ナッツzap | [61](61.md) |
| `9467`        | Tidal login | [Tidal-nostr] |
| `9734`        | Zap要求                | [57](57.md)              |
| `9735`        | Zap                        | [57](57.md)              |
| `9802`        | ハイライト                 | [84](84.md)              |
| `10000`       | ミュートリスト                  | [51](51.md)              |
| `10001`       | ピン留めリスト                   | [51](51.md)              |
| `10002`       | リレーリストメタデータ        | [65](65.md)              |
| `10003`       | ブックマークリスト              | [51](51.md)              |
| `10004`       | コミュニティリスト           | [51](51.md)              |
| `10005`       | パブリックチャットリスト          | [51](51.md)              |
| `10006`       | ブロック済みリレーリスト        | [51](51.md)              |
| `10007`       | 検索リレーリスト         | [51](51.md)              |
| `10009`       | User groups                | [51](51.md), [29](29.md) |
| `10015`       | 興味・関心リスト             | [51](51.md)              |
| `10019`       | ナッツザップおすすめミント | [61](61.md)
| `10030`       | ユーザー絵文字リスト            | [51](51.md)              |
| `10050`       | DM受信のためのリレーリスト  | [51](51.md) |
| `10063`       | ユーザーサーバーリスト | [Blossom][blossom]  |
| `10096`       | ファイルストレージサーバーリスト   | [96](96.md)              |
| `13194`       | ウォレット情報                | [47](47.md)              |
| `21000`       | Lightning Pub RPC          | [Lightning.Pub][lnpub]   |
| `22242`       | クライアント認証      | [42](42.md)              |
| `23194`       | ウォレット要求             | [47](47.md)              |
| `23195`       | ウォレット応答            | [47](47.md)              |
| `24133`       | Nostr Connect              | [46](46.md)              |
| `24242`       | メディアサーバーに保持されるブロブ |  [Blossom][blossom] |
| `27235`       | HTTP認証                  | [98](98.md)              |
| `30000`       | フォローセット                | [51](51.md)              |
| `30001`       | 汎用リスト              | [51](51.md)              |
| `30002`       | リレーセット                 | [51](51.md)              |
| `30003`       | ブックマークセット              | [51](51.md)              |
| `30004`       | キュレーションセット              | [51](51.md)              |
| `30005`       | ビデオセット |    [51](51.md) |
| `30007`       | kindミュートセット        | [51](51.md) |
| `30008`       | プロフィールバッジ             | [58](58.md)              |
| `30009`       | バッジ定義           | [58](58.md)              |
| `30015`       | 興味・関心セット              | [51](51.md)              |
| `30017`       | Create or update a stall   | [15](15.md)              |
| `30018`       | Create or update a product | [15](15.md)              |
| `30019`       | Marketplace UI/UX          | [15](15.md)              |
| `30020`       | Product sold as an auction | [15](15.md)              |
| `30023`       | 長文投稿          | [23](23.md)              |
| `30024`       | 長文投稿の下書き    | [23](23.md)              |
| `30030`       | 絵文字セット                 | [51](51.md)              |
| `30040`       | Modular Article Header          | [NKBIP-01]                             |
| `30041`       | Modular Article Content         | [NKBIP-01]                             |
| `30063`       | Release artifact sets      | [51](51.md)              |
| `30078`       | アプリケーション固有データ  | [78](78.md)              |
| `30311`       | ライブイベント                 | [53](53.md)              |
| `30315`       | ユーザーステータス              | [38](38.md)              |
| `30388`       | Slide Set                       | [Corny Chat][cornychat-slideset]       |
| `30402`       | Classified Listing         | [99](99.md)              |
| `30403`       | Draft Classified Listing   | [99](99.md)              |
| `30617`       | Repository announcements   | [34](34.md)              |
| `30618`       | Repository state announcements  | [34](34.md)                            |
| `30818`       | Wiki article                    | [54](54.md)                            |
| `30819`       | Redirects                       | [54](54.md)                            |
| `31388`       | Link Set                        | [Corny Chat][cornychat-linkset]        |
| `31890`       | Feed                            | [NUD: Custom Feeds][NUD: Custom Feeds] |
| `31922`       | 日付指定のカレンダーイベント  | [52](52.md)              |
| `31923`       | 時刻指定のカレンダーイベント  | [52](52.md)              |
| `31924`       | カレンダー                   | [52](52.md)              |
| `31925`       | 要返信のカレンダーイベント        | [52](52.md)              |
| `31989`       | 推奨ハンドラ     | [89](89.md)              |
| `31990`       | ハンドラ情報        | [89](89.md)              |
| `34235`       | Video Event                     | [71](71.md)                            |
| `34236`       | Short-form Portrait Video Event | [71](71.md)                            |
| `34550`       | Community Definition       | [72](72.md)              |
| `37375`       | Cashu Wallet Event              | [60](60.md)                            |
| `38383`       | Peer-to-peer Order events       | [69](69.md)                            |
| `39000-9`     | Group metadata events      | [29](29.md)              |


[NUD: Custom Feeds]: https://wikifreedia.xyz/cip-01/
[nostrocket]: https://github.com/nostrocket/NIPS/blob/main/Problems.md
[lnpub]: https://github.com/shocknet/Lightning.Pub/blob/master/proto/autogenerated/client.md
[cornychat-slideset]: https://cornychat.com/datatypes#kind30388slideset
[cornychat-linkset]: https://cornychat.com/datatypes#kind31388linkset
[joinstr]: https://gitlab.com/1440000bytes/joinstr/-/blob/main/NIP.md
[NKBIP-01]: https://wikistr.com/nkbip-01
[NKBIP-02]: https://wikistr.com/nkbip-02
[blossom]: https://github.com/hzrd149/blossom
[Tidal-nostr]: https://wikistr.com/tidal-nostr

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
| `p`               | 公開鍵 (hex)                         | relay URL, petname   | [01](01.md), [02](02.md)              |
| `a`               | coordinates to an event              | relay URL            | [01](01.md)                           |
| `A`               | ルートアドレス                         | relay URL                       | [22](22.md)                                        | 
| `d`               | 識別子                               | --                   | [01](01.md)                           |
| `e`               | イベントID (hex)                     | relay URL, marker    | [01](01.md), [10](10.md)              |
| `E`               | ルートイベントID                         | relay URL                       | [22](22.md)                                        |
| `f`               | 通貨コード                        | --                              | [69](69.md)                                        |
| `-`               | --                                   | --                              | [70](70.md)                                        |
| `g`               | ジオハッシュ                         | --                   | [52](52.md)                           |
| `h`               | グループID                             | --                              | [29](29.md)                                        |
| `i`               | 外部アイデンティティ                     | proof, url hint                | [35](35.md), [39](39.md) , [73](73.md)                          |
| `I`               | ルート外部アイデンティティ               | --                              | [22](22.md)                                        |
| `k`               | 種別(kind)              | --                   | [18](18.md), [25](25.md), [72](72.md), [73](73.md) |
| `K`               | ルートスコープ                           | --                              | [22](22.md)                                        |
| `l`               | ラベル, ラベル名前空間               | annotations          | [32](32.md)                           |
| `L`               | ラベル名前空間                       | --                   | [32](32.md)                           |
| `m`               | MIME type                            | --                   | [94](94.md)                           |
| `p`               | 公開鍵 (hex)                         | relay URL, petname   | [01](01.md), [02](02.md)              |
| `q`               | イベントID (hex)                       | relay URL    | [18](18.md)                           |
| `r`               | 参照 (URL, etc)               | petname              |                                       |
| `r`               | リレーURL                            | marker               | [65](65.md)                           |
| `s`               | ステータス                               | --                              | [69](69.md)                                        |
| `t`               | ハッシュタグ                              | --                   |                                       |
| `u`               | url                                  | --                              | [61](61.md), [98](98.md)                           |
| `x`               | インフォハッシュ                             | --                              | [35](35.md)                                        |
| `y`               | プラットフォーム                            | --                              | [69](69.md)                                        |
| `z`               | 順番                         | --                              | [69](69.md)                                        |
| `-`               | --                                   | --                              | [70](70.md)                                        |
| `alt`             | 概要                              | --                   | [31](31.md)                           |
| `amount`          | 文字列化されたミリサトシ           | --                   | [57](57.md)                           |
| `bolt11`          | `bolt11` invoice                     | --                   | [57](57.md)                           |
| `challenge`       | チャレンジ文字列                     | --                   | [42](42.md)                           |
| `client`          | 名前, アドレス                        | relay URL            | [89](89.md)                           |
| `clone`           | git clone URL                        | --                   | [34](34.md)                           |
| `content-warning` | 理由                               | --                   | [36](36.md)                           |
| `delegation`      | 公開鍵, 条件, 委任トークン | --                   | [26](26.md)                           |
| `description`     | インボイス/バッジの説明                          | --                   | [34](34.md), [57](57.md), [58](58.md) |
| `emoji`           | ショートコード, 画像 URL                 | --                   | [30](30.md)                           |
| `encrypted`       | --                                   | --                   | [90](90.md)                           |
| `expiration`      | unix timestamp (string)              | --                   | [40](40.md)                           |
| `file`            | フルパス (文字列)                   | --                              | [35](35.md)                                        |
| `goal`            | イベントID (hex)                     | relay URL            | [75](75.md)                           |
| `image`           | 画像URL               　             | dimensions in pixels | [23](23.md), [58](58.md)              |
| `imeta`           | インラインメタデータ                      | --                   | [92](92.md)                           |
| `lnurl`           | `bech32` encoded `lnurl`             | --                   | [57](57.md)                           |
| `location`        | 場所文字列                      | --                   | [52](52.md), [99](99.md)              |
| `name`            | 名前                                 | --                   | [34](34.md), [58](58.md)              |
| `nonce`           | 乱数                               | --                   | [13](13.md)                           |
| `preimage`        | `bolt11` インボイスのハッシュ             | --                   | [57](57.md)                           |
| `price`           | 値段                                | currency, frequency  | [99](99.md)                           |
| `proxy`           | 外部ID                          | protocol             | [48](48.md)                           |
| `published_at`    | unix timestamp (string)              | --                   | [23](23.md)                           |
| `relay`           | リレーURL                            | --                   | [42](42.md)                           |
| `relays`          | リレーリスト                           | --                   | [57](57.md)                           |
| `server`          | ファイルストレージサーバーURL              | --                   | [96](96.md)                           |
| `subject`         | 件名                              | --                   | [14](14.md)                           |
| `summary`         | 記事の要約                      | --                   | [23](23.md)                           |
| `thumb`           | バッジサムネイル                      | dimensions in pixels | [58](58.md)                           |
| `title`           | 記事のタイトル                        | --                   | [23](23.md)                           |
| `tracker`         | torrentトラッカーURL                  | --                              | [35](35.md)                                        |
| `web`             | webpage URL                          | --                   | [34](34.md)                           |
| `zap`             | 公開鍵 (hex), リレー URL              | weight               | [57](57.md)                           |


## NIPsの受け入れ基準

1. (適用可能であれば) 少なくとも2つのクライアントと1つのリレーが完全に実装しているべきである。
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

## 破壊的変更

[Breaking Changes](BREAKING.md)

## ライセンス

All NIPs are public domain.

## Contributors

<a align="center" href="https://github.com/nostr-protocol/nips/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=nostr-protocol/nips" />
</a>
