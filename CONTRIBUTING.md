# NIPs日本語訳への貢献

NIPs日本語訳への貢献に興味をお持ちいただきありがとうございます。これは、[NIPs (Nostr Implementation Possibilities)](https://github.com/nostr-protocol/nips) を日本語訳するプロジェクトへ貢献するためのガイドラインです。このテキストは常に改善の余地を含んでおり、Pull Requestによる提案を歓迎します。

## このプロジェクトの目的

このプロジェクトでは、[Nostr](https://github.com/nostr-protocol/nostr)の実装可能性について記述されたNIPsの日本語の翻訳作業を行います。NIPsの最新の記述に正しく追従した日本語訳を行うことで日本語話者の方々の理解を促進し、Nostrの日本における普及に貢献することを目的としています。

## 貢献の仕方

### 翻訳作業

1. まず作業の重複を防ぐために、mainブランチにおいて未翻訳かつ[Progress checklist](https://github.com/nostr-jp/nips-ja/issues/1)のIssueにて誰も担当していないNIP番号を選択してください。
2. そのNIPを自分が担当することを[Progress checklist](https://github.com/nostr-jp/nips-ja/issues/1)で宣言してください。
3. mainブランチをフォークして1週間以内に翻訳を完了し、Pull Requestを作成してください。
4. Pull Requestがtextlintというスタイルチェッカーによる自動チェックを通過し、メンテナによるレビューが完了するとmainブランチにマージされて翻訳完了です。

#### 翻訳ガイド

- Pull Requestを作成する前に、ローカルリポジトリで`npm install`を実行してtextlintをインストールし、`npm run lint`を実行してtextlintによる自動チェックを通過することを確認してください。
  - 自動チェックされる内容は現在詳細を検討中ですが、[About style guide](https://github.com/nostr-jp/nips-ja/issues/6)のIssueにて暫定案を示しています。
- gitで翻訳を管理する都合上、**対応する訳文は原文の行位置と厳密に対応させる**必要があります。これを守らないと、原文の変更が正しく追従できなくなります。
- 原文に登場する"MUST"、"SHOULD"、"MAY"は、[RFC2119](https://datatracker.ietf.org/doc/html/rfc2119)の規約を借用しています。これらはそれぞれ「しなければならない」「するべきである」「してもかまわない」と訳し、その後に括弧書きで元の単語を付記してください。
  - 例: `...連絡先リストを削除するべきである␣(SHOULD)␣。`
- 翻訳によってNIPのタイトルが新しく訳される、または訳が更新される場合、[README.md](./README.md)中のNIPリストの対応する項目も同時に変更してください。
- 強調などの表現は、原文の表現に合わせてください。
- コードブロックの中は以下に従って翻訳してください。
    - コメントと文字列を翻訳してください。
    - 変数名と関数名、jsonのキー部分は翻訳しないでください。
    - コードが機能する状態を保ってください。
- 括弧の両端は半角スペースを設けてください。

#### 参考

Nostrのscrapboxには、NIPsの仮翻訳やNostrについての関連情報が数多くまとめられています。ただし、情報が古い場合もあるので必ず原文をチェックしながら作業してください。

[Nostr scrapbox](https://scrapbox.io/nostr/NIP)

### 翻訳・スタイルガイドの問題点の報告

このプロジェクトの翻訳・スタイルガイドに問題点があると感じた場合は、Issueを作成したり、既存のIssueに書き込む形で報告してください。また、そのIssueに対する修正案をPull Requestとして作成していただけるとより助かります。
