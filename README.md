# NIPs

NIPsは、**Nostr Implementation Possibilities**の略称である。

本文書は、[Nostr](https://github.com/nostr-protocol/nostr)互換のリレーおよびクライアントソフトウェアによって実装されうるものを文書化するために存在している。

---

<<<<<<< HEAD
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
=======
- [List](#list)
- [Event Kinds](#event-kinds)
- [Message Types](#message-types)
  - [Client to Relay](#client-to-relay)
  - [Relay to Client](#relay-to-client)
- [Common Tags](#common-tags)
- [Criteria for acceptance of NIPs](#criteria-for-acceptance-of-nips)
- [Is this repository a centralizing factor?](#is-this-repository-a-centralizing-factor)
- [How this repository works](#how-this-repository-works)
- [License](#license)
>>>>>>> upstream/master

---

## 仕様一覧

<<<<<<< HEAD
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
=======
- [NIP-01: Basic protocol flow description](01.md)
- [NIP-02: Follow List](02.md)
- [NIP-03: OpenTimestamps Attestations for Events](03.md)
- [NIP-04: Encrypted Direct Message](04.md) --- **unrecommended**: deprecated in favor of [NIP-17](17.md)
- [NIP-05: Mapping Nostr keys to DNS-based internet identifiers](05.md)
- [NIP-06: Basic key derivation from mnemonic seed phrase](06.md)
- [NIP-07: `window.nostr` capability for web browsers](07.md)
- [NIP-08: Handling Mentions](08.md) --- **unrecommended**: deprecated in favor of [NIP-27](27.md)
- [NIP-09: Event Deletion Request](09.md)
- [NIP-10: Text Notes and Threads](10.md)
- [NIP-11: Relay Information Document](11.md)
>>>>>>> upstream/master
- [NIP-13: Proof of Work](13.md)
- [NIP-14: テキストイベントにおける件名タグ](14.md)
- [NIP-15: Nostr Marketplace (for resilient marketplaces)](15.md)
<<<<<<< HEAD
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
=======
- [NIP-17: Private Direct Messages](17.md)
- [NIP-18: Reposts](18.md)
- [NIP-19: bech32-encoded entities](19.md)
- [NIP-21: `nostr:` URI scheme](21.md)
- [NIP-22: Comment](22.md)
- [NIP-23: Long-form Content](23.md)
- [NIP-24: Extra metadata fields and tags](24.md)
- [NIP-25: Reactions](25.md)
- [NIP-26: Delegated Event Signing](26.md) --- **unrecommended**: adds unnecessary burden for little gain
- [NIP-27: Text Note References](27.md)
- [NIP-28: Public Chat](28.md)
- [NIP-29: Relay-based Groups](29.md)
- [NIP-30: Custom Emoji](30.md)
- [NIP-31: Dealing with Unknown Events](31.md)
- [NIP-32: Labeling](32.md)
- [NIP-34: `git` stuff](34.md)
- [NIP-35: Torrents](35.md)
- [NIP-36: Sensitive Content](36.md)
- [NIP-37: Draft Events](37.md)
- [NIP-38: User Statuses](38.md)
- [NIP-39: External Identities in Profiles](39.md)
- [NIP-40: Expiration Timestamp](40.md)
- [NIP-42: Authentication of clients to relays](42.md)
- [NIP-43: Relay Access Metadata and Requests](43.md)
- [NIP-44: Encrypted Payloads (Versioned)](44.md)
- [NIP-45: Counting results](45.md)
- [NIP-46: Nostr Remote Signing](46.md)
- [NIP-47: Nostr Wallet Connect](47.md)
- [NIP-48: Proxy Tags](48.md)
- [NIP-49: Private Key Encryption](49.md)
- [NIP-50: Search Capability](50.md)
- [NIP-51: Lists](51.md)
- [NIP-52: Calendar Events](52.md)
- [NIP-53: Live Activities](53.md)
>>>>>>> upstream/master
- [NIP-54: Wiki](54.md)
- [NIP-55: アンドロイド署名アプリ](55.md)
- [NIP-56: 通報](56.md)
- [NIP-57: Lightning Zaps](57.md)
- [NIP-58: バッジ](58.md)
- [NIP-59: Gift Wrap](59.md)
<<<<<<< HEAD
- [NIP-60: カシューウォレット](60.md)
- [NIP-61: ナッツzaps](61.md)
- [NIP-64: チェス (PGN)](64.md)
- [NIP-65: リレーリストメタデータ](65.md)
- [NIP-68: 画像第一フィード](68.md)
- [NIP-72: Moderated Communities](72.md)
- [NIP-73: External Content IDs](73.md)
- [NIP-75: Zap Goals](75.md)
- [NIP-78: アプリケーション固有データ](78.md)
- [NIP-86: リレー管理 API](86.md)
- [NIP-84: ハイライト](84.md)
- [NIP-89: 推奨アプリケーションハンドラ](89.md)
- [NIP-90: データ自動販売機](90.md)
- [NIP-92: Media Attachments](92.md)
- [NIP-94: ファイルメタデータ](94.md)
- [NIP-96: HTTPファイルストレージインテグレーション](96.md)
- [NIP-98: HTTP認証](98.md)
- [NIP-99: Classified Listings](99.md)
- [NIP-7D: スレッド](7D.md)
- [NIP-C7: チャット](C7.md)

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
| `9`           | チャットメッセージ         | [C7](C7.md)              |
| `10`          | グループチャットスレッドリプライ  | 29 (非推奨)              |
| `11`          | スレッド               | [7D](7D.md)              |
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
=======
- [NIP-60: Cashu Wallet](60.md)
- [NIP-61: Nutzaps](61.md)
- [NIP-62: Request to Vanish](62.md)
- [NIP-64: Chess (PGN)](64.md)
- [NIP-65: Relay List Metadata](65.md)
- [NIP-66: Relay Discovery and Liveness Monitoring](66.md)
- [NIP-68: Picture-first feeds](68.md)
- [NIP-69: Peer-to-peer Order events](69.md)
- [NIP-70: Protected Events](70.md)
- [NIP-71: Video Events](71.md)
- [NIP-72: Moderated Communities](72.md)
- [NIP-73: External Content IDs](73.md)
- [NIP-75: Zap Goals](75.md)
- [NIP-77: Negentropy Syncing](77.md)
- [NIP-78: Application-specific data](78.md)
- [NIP-7D: Threads](7D.md)
- [NIP-84: Highlights](84.md)
- [NIP-86: Relay Management API](86.md)
- [NIP-87: Ecash Mint Discoverability](87.md)
- [NIP-88: Polls](88.md)
- [NIP-89: Recommended Application Handlers](89.md)
- [NIP-90: Data Vending Machines](90.md)
- [NIP-92: Media Attachments](92.md)
- [NIP-94: File Metadata](94.md)
- [NIP-96: HTTP File Storage Integration](96.md) --- **unrecommended**: replaced by blossom APIs
- [NIP-98: HTTP Auth](98.md)
- [NIP-99: Classified Listings](99.md)
- [NIP-A0: Voice Messages](A0.md)
- [NIP-A4: Public Messages](A4.md)
- [NIP-B0: Web Bookmarks](B0.md)
- [NIP-B7: Blossom](B7.md)
- [NIP-BE: Nostr BLE Communications Protocol](BE.md)
- [NIP-C0: Code Snippets](C0.md)
- [NIP-C7: Chats](C7.md)
- [NIP-EE: E2EE Messaging using MLS Protocol](EE.md) --- **unrecommended**: superseded by the [Marmot Protocol](https://github.com/marmot-protocol/marmot)

## Event Kinds
| kind          | description                     | NIP                                    |
| ------------- | ------------------------------- | -------------------------------------- |
| `0`           | User Metadata                   | [01](01.md)                            |
| `1`           | Short Text Note                 | [10](10.md)                            |
| `2`           | Recommend Relay                 | 01 (deprecated)                        |
| `3`           | Follows                         | [02](02.md)                            |
| `4`           | Encrypted Direct Messages       | [04](04.md)                            |
| `5`           | Event Deletion Request          | [09](09.md)                            |
| `6`           | Repost                          | [18](18.md)                            |
| `7`           | Reaction                        | [25](25.md)                            |
| `8`           | Badge Award                     | [58](58.md)                            |
| `9`           | Chat Message                    | [C7](C7.md)                            |
| `10`          | Group Chat Threaded Reply       | 29 (deprecated)                        |
| `11`          | Thread                          | [7D](7D.md)                            |
| `12`          | Group Thread Reply              | 29 (deprecated)                        |
| `13`          | Seal                            | [59](59.md)                            |
| `14`          | Direct Message                  | [17](17.md)                            |
| `15`          | File Message                    | [17](17.md)                            |
| `16`          | Generic Repost                  | [18](18.md)                            |
| `17`          | Reaction to a website           | [25](25.md)                            |
| `20`          | Picture                         | [68](68.md)                            |
| `21`          | Video Event                     | [71](71.md)                            |
| `22`          | Short-form Portrait Video Event | [71](71.md)                            |
| `24`          | Public Message                  | [A4](A4.md)                            |
| `30`          | internal reference              | [NKBIP-03]                             |
| `31`          | external web reference          | [NKBIP-03]                             |
| `32`          | hardcopy reference              | [NKBIP-03]                             |
| `33`          | prompt reference                | [NKBIP-03]                             |
| `40`          | Channel Creation                | [28](28.md)                            |
| `41`          | Channel Metadata                | [28](28.md)                            |
| `42`          | Channel Message                 | [28](28.md)                            |
| `43`          | Channel Hide Message            | [28](28.md)                            |
| `44`          | Channel Mute User               | [28](28.md)                            |
| `62`          | Request to Vanish               | [62](62.md)                            |
| `64`          | Chess (PGN)                     | [64](64.md)                            |
| `443`         | KeyPackage                      | [Marmot](marmot)                       |
| `444`         | Welcome Message                 | [Marmot](marmot)                       |
| `445`         | Group Event                     | [Marmot](marmot)                       |
| `818`         | Merge Requests                  | [54](54.md)                            |
| `1018`        | Poll Response                   | [88](88.md)                            |
| `1021`        | Bid                             | [15](15.md)                            |
| `1022`        | Bid confirmation                | [15](15.md)                            |
| `1040`        | OpenTimestamps                  | [03](03.md)                            |
| `1059`        | Gift Wrap                       | [59](59.md)                            |
| `1063`        | File Metadata                   | [94](94.md)                            |
| `1068`        | Poll                            | [88](88.md)                            |
| `1111`        | Comment                         | [22](22.md)                            |
| `1222`        | Voice Message                   | [A0](A0.md)                            |
| `1244`        | Voice Message Comment           | [A0](A0.md)                            |
| `1311`        | Live Chat Message               | [53](53.md)                            |
| `1337`        | Code Snippet                    | [C0](C0.md)                            |
| `1617`        | Patches                         | [34](34.md)                            |
| `1618`        | Pull Requests                   | [34](34.md)                            |
| `1619`        | Pull Request Updates            | [34](34.md)                            |
| `1621`        | Issues                          | [34](34.md)                            |
| `1622`        | Git Replies (deprecated)        | [34](34.md)                            |
| `1630`-`1633` | Status                          | [34](34.md)                            |
| `1971`        | Problem Tracker                 | [nostrocket][nostrocket]               |
| `1984`        | Reporting                       | [56](56.md)                            |
| `1985`        | Label                           | [32](32.md)                            |
| `1986`        | Relay reviews                   |                                        |
| `1987`        | AI Embeddings / Vector lists    | [NKBIP-02]                             |
| `2003`        | Torrent                         | [35](35.md)                            |
| `2004`        | Torrent Comment                 | [35](35.md)                            |
| `2022`        | Coinjoin Pool                   | [joinstr][joinstr]                     |
| `4550`        | Community Post Approval         | [72](72.md)                            |
| `5000`-`5999` | Job Request                     | [90](90.md)                            |
| `6000`-`6999` | Job Result                      | [90](90.md)                            |
| `7000`        | Job Feedback                    | [90](90.md)                            |
| `7374`        | Reserved Cashu Wallet Tokens    | [60](60.md)                            |
| `7375`        | Cashu Wallet Tokens             | [60](60.md)                            |
| `7376`        | Cashu Wallet History            | [60](60.md)                            |
| `7516`        | Geocache log                    | [geocaching][geocaching]               |
| `7517`        | Geocache proof of find          | [geocaching][geocaching]               |
| `8000`        | Add User                        | [43](43.md)                            |
| `8001`        | Remove User                     | [43](43.md)                            |
| `9000`-`9030` | Group Control Events            | [29](29.md)                            |
| `9041`        | Zap Goal                        | [75](75.md)                            |
| `9321`        | Nutzap                          | [61](61.md)                            |
| `9467`        | Tidal login                     | [Tidal-nostr]                          |
| `9734`        | Zap Request                     | [57](57.md)                            |
| `9735`        | Zap                             | [57](57.md)                            |
| `9802`        | Highlights                      | [84](84.md)                            |
| `10000`       | Mute list                       | [51](51.md)                            |
| `10001`       | Pin list                        | [51](51.md)                            |
| `10002`       | Relay List Metadata             | [65](65.md), [51](51.md)               |
| `10003`       | Bookmark list                   | [51](51.md)                            |
| `10004`       | Communities list                | [51](51.md)                            |
| `10005`       | Public chats list               | [51](51.md)                            |
| `10006`       | Blocked relays list             | [51](51.md)                            |
| `10007`       | Search relays list              | [51](51.md)                            |
| `10009`       | User groups                     | [51](51.md), [29](29.md)               |
| `10012`       | Favorite relays list            | [51](51.md)                            |
| `10013`       | Private event relay list        | [37](37.md)                            |
| `10015`       | Interests list                  | [51](51.md)                            |
| `10019`       | Nutzap Mint Recommendation      | [61](61.md)                            |
| `10020`       | Media follows                   | [51](51.md)                            |
| `10030`       | User emoji list                 | [51](51.md)                            |
| `10050`       | Relay list to receive DMs       | [51](51.md), [17](17.md)               |
| `10051`       | KeyPackage Relays List          | [Marmot](marmot)                       |
| `10063`       | User server list                | [Blossom][blossom]                     |
| `10096`       | File storage server list        | [96](96.md) (deprecated)               |
| `10166`       | Relay Monitor Announcement      | [66](66.md)                            |
| `10312`       | Room Presence                   | [53](53.md)                            |
| `10377`       | Proxy Announcement              | [Nostr Epoxy][nostr-epoxy]             |
| `11111`       | Transport Method Announcement   | [Nostr Epoxy][nostr-epoxy]             |
| `13194`       | Wallet Info                     | [47](47.md)                            |
| `13534`       | Membership Lists                | [43](43.md)                            |
| `14388`       | User Sound Effect Lists         | [Corny Chat][cornychat-usersoundlist]  |
| `17375`       | Cashu Wallet Event              | [60](60.md)                            |
| `21000`       | Lightning Pub RPC               | [Lightning.Pub][lnpub]                 |
| `22242`       | Client Authentication           | [42](42.md)                            |
| `23194`       | Wallet Request                  | [47](47.md)                            |
| `23195`       | Wallet Response                 | [47](47.md)                            |
| `24133`       | Nostr Connect                   | [46](46.md)                            |
| `24242`       | Blobs stored on mediaservers    | [Blossom][blossom]                     |
| `27235`       | HTTP Auth                       | [98](98.md)                            |
| `28934`       | Join Request                    | [43](43.md)                            |
| `28935`       | Invite Request                  | [43](43.md)                            |
| `28936`       | Leave Request                   | [43](43.md)                            |
| `30000`       | Follow sets                     | [51](51.md)                            |
| `30001`       | Generic lists                   | 51 (deprecated)                        |
| `30002`       | Relay sets                      | [51](51.md)                            |
| `30003`       | Bookmark sets                   | [51](51.md)                            |
| `30004`       | Curation sets                   | [51](51.md)                            |
| `30005`       | Video sets                      | [51](51.md)                            |
| `30006`       | Picture sets                    | [51](51.md)                            |
| `30007`       | Kind mute sets                  | [51](51.md)                            |
| `30008`       | Profile Badges                  | [58](58.md)                            |
| `30009`       | Badge Definition                | [58](58.md)                            |
| `30015`       | Interest sets                   | [51](51.md)                            |
| `30017`       | Create or update a stall        | [15](15.md)                            |
| `30018`       | Create or update a product      | [15](15.md)                            |
| `30019`       | Marketplace UI/UX               | [15](15.md)                            |
| `30020`       | Product sold as an auction      | [15](15.md)                            |
| `30023`       | Long-form Content               | [23](23.md)                            |
| `30024`       | Draft Long-form Content         | [23](23.md)                            |
| `30030`       | Emoji sets                      | [51](51.md)                            |
| `30040`       | Curated Publication Index       | [NKBIP-01]                             |
| `30041`       | Curated Publication Content     | [NKBIP-01]                             |
| `30063`       | Release artifact sets           | [51](51.md)                            |
| `30078`       | Application-specific Data       | [78](78.md)                            |
| `30166`       | Relay Discovery                 | [66](66.md)                            |
| `30267`       | App curation sets               | [51](51.md)                            |
| `30311`       | Live Event                      | [53](53.md)                            |
| `30312`       | Interactive Room                | [53](53.md)                            |
| `30313`       | Conference Event                | [53](53.md)                            |
| `30315`       | User Statuses                   | [38](38.md)                            |
>>>>>>> upstream/master
| `30388`       | Slide Set                       | [Corny Chat][cornychat-slideset]       |
| `30402`       | Classified Listing         | [99](99.md)              |
| `30403`       | Draft Classified Listing   | [99](99.md)              |
| `30617`       | Repository announcements   | [34](34.md)              |
| `30618`       | Repository state announcements  | [34](34.md)                            |
| `30818`       | Wiki article                    | [54](54.md)                            |
| `30819`       | Redirects                       | [54](54.md)                            |
| `31234`       | Draft Event                     | [37](37.md)                            |
| `31388`       | Link Set                        | [Corny Chat][cornychat-linkset]        |
| `31890`       | Feed                            | [NUD: Custom Feeds][NUD: Custom Feeds] |
<<<<<<< HEAD
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

=======
| `31922`       | Date-Based Calendar Event       | [52](52.md)                            |
| `31923`       | Time-Based Calendar Event       | [52](52.md)                            |
| `31924`       | Calendar                        | [52](52.md)                            |
| `31925`       | Calendar Event RSVP             | [52](52.md)                            |
| `31989`       | Handler recommendation          | [89](89.md)                            |
| `31990`       | Handler information             | [89](89.md)                            |
| `32267`       | Software Application            |                                        |
| `32388`       | User Room Favorites             | [Corny Chat][cornychat-roomfavorites]  |
| `33388`       | High Scores                     | [Corny Chat][cornychat-highscores]     |
| `34235`       | Addressable Video Event         | [71](71.md)                            |
| `34236`       | Addressable Short Video Event   | [71](71.md)                            |
| `34388`       | Sound Effects                   | [Corny Chat][cornychat-soundeffects]   |
| `34550`       | Community Definition            | [72](72.md)                            |
| `38172`       | Cashu Mint Announcement         | [87](87.md)                            |
| `38173`       | Fedimint Announcement           | [87](87.md)                            |
| `37516`       | Geocache listing                | [geocaching](geocaching)               |
| `38383`       | Peer-to-peer Order events       | [69](69.md)                            |
| `39000-9`     | Group metadata events           | [29](29.md)                            |
| `39089`       | Starter packs                   | [51](51.md)                            |
| `39092`       | Media starter packs             | [51](51.md)                            |
| `39701`       | Web bookmarks                   | [B0](B0.md)                            |
>>>>>>> upstream/master

[NUD: Custom Feeds]: https://wikifreedia.xyz/cip-01/
[nostrocket]: https://github.com/nostrocket/NIPS/blob/main/Problems.md
[lnpub]: https://github.com/shocknet/Lightning.Pub/blob/master/proto/autogenerated/client.md
[cornychat-usersoundlist]: https://cornychat.com/datatypes#kind14388usersoundeffectslist
[cornychat-slideset]: https://cornychat.com/datatypes#kind30388slideset
[cornychat-linkset]: https://cornychat.com/datatypes#kind31388linkset
[cornychat-roomfavorites]: https://cornychat.com/datatypes#kind32388roomfavorites
[cornychat-highscores]: https://cornychat.com/datatypes#kind33388highscores
[cornychat-soundeffects]: https://cornychat.com/datatypes#kind34388soundeffectsets
[joinstr]: https://gitlab.com/1440000bytes/joinstr/-/blob/main/NIP.md
[NKBIP-01]: https://wikistr.com/nkbip-01*fd208ee8c8f283780a9552896e4823cc9dc6bfd442063889577106940fd927c1
[NKBIP-02]: https://wikistr.com/nkbip-02*fd208ee8c8f283780a9552896e4823cc9dc6bfd442063889577106940fd927c1
[NKBIP-03]: https://wikistr.com/nkbip-03*fd208ee8c8f283780a9552896e4823cc9dc6bfd442063889577106940fd927c1
[blossom]: https://github.com/hzrd149/blossom
[Tidal-nostr]: https://wikistr.com/tidal-nostr
[geocaching]: https://nostrhub.io/naddr1qvzqqqrcvypzppscgyy746fhmrt0nq955z6xmf80pkvrat0yq0hpknqtd00z8z68qqgkwet0vdskx6rfdenj6etkv4h8guc6gs5y5
[nostr-epoxy]: https://github.com/Origami74/nostr-epoxy-reverse-proxy
[marmot]: https://github.com/marmot-protocol/marmot


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

<<<<<<< HEAD
新しいイベント種別(kind)を含むNIPsを提案する場合は、これらのリストも更新すること。

## 標準化済みタグ

| タグ名            | 値                                   | その他パラメータ      | NIP                                  |
| ----------------- | ------------------------------------ | -------------------- | ------------------------------------- |
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
| `q`               | イベントID (hex)                     | relay URL            | [18](18.md)                           |
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
| `location`        | 場所文字列                           | --                   | [52](52.md), [99](99.md)              |
| `name`            | 名前                             | --                   | [58](58.md)                           |
| `nonce`           | 乱数                                 | --                   | [13](13.md)                           |
| `preimage`        | `bolt11` インボイスのハッシュ        | --                   | [57](57.md)                           |
| `price`           | 値段                                 | currency, frequency  | [99](99.md)                           |
| `proxy`           | 外部ID                               | protocol             | [48](48.md)                           |
| `published_at`    | unix timestamp (string)              | --                   | [23](23.md)                           |
| `relay`           | リレーURL                            | --                   | [42](42.md)                           |
| `relays`          | リレーリスト                         | --                   | [57](57.md)                           |
| `server`          | ファイルストレージサーバーURL        | --                   | [96](96.md)                           |
| `subject`         | 件名                                 | --                   | [14](14.md)                           |
| `summary`         | 記事の要約                           | --                   | [23](23.md)                           |
| `thumb`           | バッジサムネイル                     | dimensions in pixels | [58](58.md)                           |
| `title`           | 記事のタイトル                       | --                   | [23](23.md)                           |
| `zap`             | 公開鍵 (hex), リレー URL             | weight               | [57](57.md)                           |
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
=======
## Common Tags

| name              | value                                | other parameters                | NIP                                                |
| ----------------- | ------------------------------------ | ------------------------------- | -------------------------------------------------- |
| `a`               | coordinates to an event              | relay URL                       | [01](01.md)                                        |
| `A`               | root address                         | relay URL                       | [22](22.md)                                        |
| `c`               | commit id                            |                                 | [34](34.md)                                       |
| `d`               | identifier                           | --                              | [01](01.md)                                        |
| `e`               | event id (hex)                       | relay URL, marker, pubkey (hex) | [01](01.md), [10](10.md)                           |
| `E`               | root event id                        | relay URL                       | [22](22.md)                                        |
| `f`               | currency code                        | --                              | [69](69.md)                                        |
| `g`               | geohash                              | --                              | [52](52.md)                                        |
| `h`               | group id                             | --                              | [29](29.md)                                        |
| `i`               | external identity                    | proof, url hint                 | [35](35.md), [39](39.md), [73](73.md)              |
| `I`               | root external identity               | --                              | [22](22.md)                                        |
| `k`               | kind                                 | --                              | [18](18.md), [25](25.md), [72](72.md), [73](73.md) |
| `K`               | root scope                           | --                              | [22](22.md)                                        |
| `l`               | label, label namespace, language name| --                              | [32](32.md), [C0](C0.md)                           |
| `L`               | label namespace                      | --                              | [32](32.md)                                        |
| `m`               | MIME type                            | --                              | [94](94.md)                                        |
| `p`               | pubkey (hex)                         | relay URL, petname              | [01](01.md), [02](02.md), [22](22.md)              |
| `P`               | pubkey (hex)                         | --                              | [22](22.md), [57](57.md)                           |
| `q`               | event id (hex)                       | relay URL, pubkey (hex)         | [18](18.md)                                        |
| `r`               | a reference (URL, etc)               | --                              | [24](24.md), [25](25.md)                           |
| `r`               | relay url                            | marker                          | [65](65.md)                                        |
| `s`               | status                               | --                              | [69](69.md)                                        |
| `t`               | hashtag                              | --                              | [24](24.md), [34](34.md), [35](35.md)              |
| `u`               | url                                  | --                              | [61](61.md), [98](98.md)                           |
| `x`               | hash                                 | --                              | [35](35.md), [56](56.md)                           |
| `y`               | platform                             | --                              | [69](69.md)                                        |
| `z`               | order number                         | --                              | [69](69.md)                                        |
| `-`               | --                                   | --                              | [70](70.md)                                        |
| `alt`             | summary                              | --                              | [31](31.md)                                        |
| `amount`          | millisatoshis, stringified           | --                              | [57](57.md)                                        |
| `bolt11`          | `bolt11` invoice                     | --                              | [57](57.md)                                        |
| `branch-name`     | branch name suggestion               | --                              | [34](34.md)                                        |
| `challenge`       | challenge string                     | --                              | [42](42.md)                                        |
| `client`          | name, address                        | relay URL                       | [89](89.md)                                        |
| `clone`           | git clone URL                        | --                              | [34](34.md)                                        |
| `content-warning` | reason                               | --                              | [36](36.md)                                        |
| `delegation`      | pubkey, conditions, delegation token | --                              | [26](26.md)                                        |
| `dep`             | Required dependency                  | --                              | [C0](C0.md)                                        |
| `description`     | description                          | --                              | [34](34.md), [57](57.md), [58](58.md), [C0](C0.md) |
| `emoji`           | shortcode, image URL                 | --                              | [30](30.md)                                        |
| `encrypted`       | --                                   | --                              | [90](90.md)                                        |
| `extension`       | File extension                       | --                              | [C0](C0.md)                                        |
| `expiration`      | unix timestamp (string)              | --                              | [40](40.md)                                        |
| `file`            | full path (string)                   | --                              | [35](35.md)                                        |
| `goal`            | event id (hex)                       | relay URL                       | [75](75.md)                                        |
| `merge-base`      | commit id                            |                                 | [34](34.md)                                        |
| `HEAD`            | `ref: refs/heads/<branch-name>`      |                                 | [34](34.md)                                        |
| `image`           | image URL                            | dimensions in pixels            | [23](23.md), [52](52.md), [58](58.md)              |
| `imeta`           | inline metadata                      | --                              | [92](92.md)                                        |
| `license`         | License of the shared content        | --                              | [C0](C0.md)                                        |
| `lnurl`           | `bech32` encoded `lnurl`             | --                              | [57](57.md)                                        |
| `location`        | location string                      | --                              | [52](52.md), [99](99.md)                           |
| `name`            | name                                 | --                              | [34](34.md), [58](58.md), [72](72.md), [C0](C0.md) |
| `nonce`           | random                               | difficulty                      | [13](13.md)                                        |
| `preimage`        | hash of `bolt11` invoice             | --                              | [57](57.md)                                        |
| `price`           | price                                | currency, frequency             | [99](99.md)                                        |
| `proxy`           | external ID                          | protocol                        | [48](48.md)                                        |
| `published_at`    | unix timestamp (string)              | --                              | [23](23.md), [B0](B0.md)                           |
| `relay`           | relay url                            | --                              | [42](42.md), [17](17.md)                           |
| `relays`          | relay list                           | --                              | [57](57.md)                                        |
| `repo`            | Reference to the origin repository   | --                              | [C0](C0.md)                                        |
| `runtime`         | Runtime or environment specification | --                              | [C0](C0.md)                                        |
| `server`          | file storage server url              | --                              | [96](96.md)                                        |
| `sound`           | shortcode, sound url, image url      | --                              | [51](51.md)                                        |
| `subject`         | subject                              | --                              | [14](14.md), [17](17.md), [34](34.md)              |
| `summary`         | summary                              | --                              | [23](23.md), [52](52.md)                           |
| `thumb`           | badge thumbnail                      | dimensions in pixels            | [58](58.md)                                        |
| `title`           | title                                | --                              | [23](23.md), [B0](B0.md)                           |
| `tracker`         | torrent tracker URL                  | --                              | [35](35.md)                                        |
| `web`             | webpage URL                          | --                              | [34](34.md)                                        |
| `zap`             | pubkey (hex), relay URL              | weight                          | [57](57.md)                                        |
>>>>>>> upstream/master


## NIPsの受け入れ基準

1. (適用可能であれば) 少なくとも2つのクライアントと1つのリレーが完全に実装しているべきである。
2. 理にかなっている必要がある。
3. 任意に実装可能であり、後方互換性を有するべきである: 実装しないことを選択したクライアントやリレーが、実装することを選択したクライアントやリレーと通信した際に動作を停止しないよう厳に注意しなければならない。
4. 同じことする方法が複数あってはならない。
5. その他のルールは必要に応じて作成する。

## このリポジトリは中央集権的な要素ではありませんか？

<<<<<<< HEAD
相互運用性を向上させるために誰もが従える標準を作成し、**後方互換性**を損なうことなく**物事を行うための1つの方法**を定義する必要がある。この目的のためには誰もが同じことに同意し、それら標準の中央集権型の目録を保持すること以外に道は無い。しかし、そのような目録があるからといってNostrの分散性が損なわれることはない。_中央の目録がプロトコルの要求を満たせない場合はいつでも異議を唱えることができ_、他の場所に移行して他の人がメンテナンスできる。

フォークされ複数に分かれることも可能で、その際あるクライアントは一方に、別のクライアントはもう一方に、あるいは競合する両方の標準に準拠するクライアントもあるだろう。それはNostrの単純さ、開放性、相互運用性を少し損なうこととなるが、それでも短期的には全て機能するだろう。
=======
To promote interoperability, we need standards that everybody can follow, and we need them to define a **single way of doing each thing** without ever hurting **backwards-compatibility**, and for that purpose there is no way around getting everybody to agree on the same thing and keep a centralized index of these standards. However the fact that such an index exists doesn't hurt the decentralization of Nostr. _At any point the central index can be challenged if it is failing to fulfill the needs of the protocol_ and it can migrate to other places and be maintained by other people.

It can even fork into multiple versions, and then some clients would go one way, others would go another way, and some clients would adhere to both competing standards. This would hurt the simplicity, openness and interoperability of Nostr a little, but everything would still work in the short term.
>>>>>>> upstream/master

このリポジトリへのコミット権を持っている著名なNostrソフトウェア開発者のリストがあるが、それはほとんど実用上の理由から存在している。私達が扱っているものの性質上、リポジトリの所有者はメンバーシップを取り消したり好きなように歴史を書き換えることができる。そして、それらの行為が不当であったり、悪事や邪悪なものと認識される場合、コミュニティは抗議の声を上げなければならない。

## このリポジトリの仕組み

標準は2つの方法で作られる。1つは誰かがなにかを始め、他の人がそれを書き写すという方法である。2つ目は、**物事を行うための1つの方法**を持つという原則と**後方互換性**を壊すことなく複数のクライアントとプロトコル全般に利益をもたらす新しい標準のアイデアを持つ誰かがそれを書いてこのリポジトリに提出し、他の利害関係者がそれを読んでフィードバックし、ほとんどの人が合理的に同意したらその機能に関心のあるクライアントとリレーの開発者が実装に取り掛かることのできるNIPに成文化するという方法である。

物事を標準化するためにこれら2つの方法がこのリポジトリでサポートされている。後者が望ましいが、このリポジトリの外で出現した標準をNIPに成文化し、後の人が参照して簡単に理解し実装できるようにする取り組みも行われる。しかし、他の人間のシステムと同様に、標準が有害であると考えられる場合に裁量が行われることは明らかである。

<<<<<<< HEAD
## 破壊的変更

[Breaking Changes](BREAKING.md)

## ライセンス
=======
## License
>>>>>>> upstream/master

全てのNIPsはパブリックドメインである。

## Contributors

<a align="center" href="https://github.com/nostr-protocol/nips/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=nostr-protocol/nips" />
</a>
