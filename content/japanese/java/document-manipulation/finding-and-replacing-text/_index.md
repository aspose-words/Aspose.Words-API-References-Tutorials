---
title: Aspose.Words for Java でのテキストの検索と置換
linktitle: テキストの検索と置換
second_title: Aspose.Words Java ドキュメント処理 API
description: Aspose.Words for Java を使用して Word 文書内のテキストを検索して置換する方法を学びます。コード例を含むステップバイステップのガイド。 Java ドキュメント操作スキルを強化します。
type: docs
weight: 15
url: /ja/java/document-manipulation/finding-and-replacing-text/
---

## Aspose.Words for Java でのテキストの検索と置換の概要

Aspose.Words for Java は、Word ドキュメントをプログラムで操作できるようにする強力な Java API です。 Word 文書を扱うときの一般的なタスクの 1 つは、テキストを検索して置換することです。テンプレート内のプレースホルダーを更新する必要がある場合でも、より複雑なテキスト操作を実行する必要がある場合でも、Aspose.Words for Java は目標を効率的に達成するのに役立ちます。

## 前提条件

テキストの検索と置換の詳細に入る前に、次の前提条件が満たされていることを確認してください。

- Java開発環境
- Aspose.Words for Java ライブラリ
- 使用するサンプル Word 文書

 Aspose.Words for Java ライブラリは、次からダウンロードできます。[ここ](https://releases.aspose.com/words/java/).

## 単純なテキストの検索と置換

```java
//ドキュメントをロードする
Document doc = new Document("your-document.docx");

//DocumentBuilder を作成する
DocumentBuilder builder = new DocumentBuilder(doc);

//テキストの検索と置換
builder.getRange().replace("old-text", "new-text", new FindReplaceOptions());

//変更したドキュメントを保存する
doc.save("modified-document.docx");
```

この例では、Word 文書をロードし、`DocumentBuilder`を使用し、`replace`ドキュメント内の「古いテキスト」を検索して「新しいテキスト」に置き換えるメソッド。

## 正規表現の使用

正規表現は、テキストの検索と置換のための強力なパターン マッチング機能を提供します。 Aspose.Words for Java は、より高度な検索および置換操作のための正規表現をサポートしています。

```java
//ドキュメントをロードする
Document doc = new Document("your-document.docx");

//DocumentBuilder を作成する
DocumentBuilder builder = new DocumentBuilder(doc);

//正規表現を使用してテキストを検索および置換する
Pattern regex = Pattern.compile("your-pattern");
builder.getRange().replace(regex, "replacement-text", new FindReplaceOptions());

//変更したドキュメントを保存する
doc.save("modified-document.docx");
```

この例では、正規表現パターンを使用して、ドキュメント内のテキストを検索して置換します。

## フィールド内のテキストの無視

検索および置換操作を実行するときにフィールド内のテキストを無視するように Aspose.Words を構成できます。

```java
//ドキュメントをロードする
Document doc = new Document("your-document.docx");

// FindReplaceOptions インスタンスを作成し、IgnoreFields を true に設定します。
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreFields(true);

//テキストを置換するときにオプションを使用する
doc.getRange().replace("text-to-replace", "new-text", options);

//変更したドキュメントを保存する
doc.save("modified-document.docx");
```

これは、差し込みフィールドなどのフィールド内のテキストを置換から除外する場合に便利です。

## リビジョンの削除内のテキストを無視する

検索および置換操作中に削除リビジョン内のテキストを無視するように Aspose.Words を構成できます。

```java
//ドキュメントをロードする
Document doc = new Document("your-document.docx");

// FindReplaceOptions インスタンスを作成し、IgnoreDeleted を true に設定します。
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreDeleted(true);

//テキストを置換するときにオプションを使用する
doc.getRange().replace("text-to-replace", "new-text", options);

//変更したドキュメントを保存する
doc.save("modified-document.docx");
```

これにより、追跡された変更で削除対象としてマークされたテキストを置換から除外できます。

## リビジョンの挿入内のテキストを無視する

検索および置換操作中に挿入リビジョン内のテキストを無視するように Aspose.Words を構成できます。

```java
//ドキュメントをロードする
Document doc = new Document("your-document.docx");

// FindReplaceOptions インスタンスを作成し、IgnoreInserted を true に設定します。
FindReplaceOptions options = new FindReplaceOptions();
options.setIgnoreInserted(true);

//テキストを置換するときにオプションを使用する
doc.getRange().replace("text-to-replace", "new-text", options);

//変更したドキュメントを保存する
doc.save("modified-document.docx");
```

これにより、追跡された変更に挿入されたものとしてマークされているテキストを置換から除外できます。

## テキストを HTML に置き換える

Aspose.Words for Java を使用して、テキストを HTML コンテンツに置き換えることができます。

```java
//ドキュメントをロードする
Document doc = new Document("your-document.docx");

//カスタム置換コールバックを使用して FindReplaceOptions インスタンスを作成する
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceWithHtmlEvaluator(options));

//テキストを置換するときにオプションを使用する
doc.getRange().replace("text-to-replace", "new-html-content", options);

//変更したドキュメントを保存する
doc.save("modified-document.docx");
```

この例では、カスタムの`ReplaceWithHtmlEvaluator`テキストを HTML コンテンツに置き換えます。

## ヘッダーとフッターのテキストを置換する

Word 文書のヘッダーとフッター内のテキストを検索して置換できます。

```java
//ドキュメントをロードする
Document doc = new Document("your-document.docx");

//ヘッダーとフッターのコレクションを取得する
HeaderFooterCollection headersFooters = doc.getFirstSection().getHeadersFooters();

//テキストを置換するヘッダーまたはフッターのタイプを選択します (例: HeaderFooterType.FOOTER_PRIMARY)
HeaderFooter footer = headersFooters.getByHeaderFooterType(HeaderFooterType.FOOTER_PRIMARY);

// FindReplaceOptions インスタンスを作成し、フッターの範囲に適用します。
FindReplaceOptions options = new FindReplaceOptions();
footer.getRange().replace("text-to-replace", "new-text", options);

//変更したドキュメントを保存する
doc.save("modified-document.docx");
```

これにより、特にヘッダーとフッターでテキストの置換を実行できるようになります。

## ヘッダーとフッターの注文の変更を表示する

Aspose.Words を使用すると、ドキュメント内のヘッダーとフッターの順序の変更を表示できます。

```java
//ドキュメントをロードする
Document doc = new Document("your-document.docx");

//最初のセクションを取得する
Section firstPageSection = doc.getFirstSection();

//FindReplaceOptions インスタンスを作成し、ドキュメントの範囲に適用します。
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceLog());

//ヘッダーとフッターの順序に影響するテキストを置換する
doc.getRange().replace(Pattern.compile("(header|footer)"), "", options);

//変更したドキュメントを保存する
doc.save("modified-document.docx");
```

これにより、ドキュメント内のヘッダーとフッターの順序に関連する変更を視覚化できます。

## テキストをフィールドに置き換える

Aspose.Words for Java を使用してテキストをフィールドに置き換えることができます。

```java
//ドキュメントをロードする
Document doc = new Document("your-document.docx");

// FindReplaceOptions インスタンスを作成し、フィールドのカスタム置換コールバックを設定します。
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new ReplaceTextWithFieldHandler(FieldType.FIELD_MERGE_FIELD));

//テキストを置換するときにオプションを使用する
doc.getRange().replace(Pattern.compile("PlaceHolder(\\d+)"), "", options);

//変更したドキュメントを保存する
doc.save("modified-document.docx");
```

この例では、テキストをフィールドに置き換え、フィールドのタイプを指定します (例:`FieldType.FIELD_MERGE_FIELD`）。

## エバリュエーターに置き換える

カスタム エバリュエーターを使用して、置換テキストを動的に決定できます。

```java
//ドキュメントをロードする
Document doc = new Document("your-document.docx");

// FindReplaceOptions インスタンスを作成し、カスタム置換コールバックを設定する
FindReplaceOptions options = new FindReplaceOptions();
options.setReplacingCallback(new MyReplaceEvaluator());

//テキストを置換するときにオプションを使用する
doc.getRange().replace(Pattern.compile("[s|m]ad"), "", options);

//変更したドキュメントを保存する
doc.save("modified-document.docx");
```

この例では、カスタム エバリュエーター (`MyReplaceEvaluator`) テキストを置き換えます。

## 正規表現で置き換える

Aspose.Words for Java を使用すると、正規表現を使用してテキストを置換できます。

```java
//ドキュメントをロードする
Document doc = new Document("your-document.docx");

//正規表現を使用してテキストを検索および置換する
doc.getRange().replace(Pattern.compile("[s|m]ad"), "bad", new FindReplaceOptions());

//変更したドキュメントを保存する
doc.save("modified-document.docx");
```

この例では、正規表現パターンを使用して、ドキュメント内のテキストを検索して置換します。

## 置換パターン内の認識と置換

Aspose.Words for Java を使用すると、置換パターン内で置換を認識して実行できます。

```java
//ドキュメントをロードする
Document doc = new Document("your-document.docx");

//UseSubstitutions を true に設定して FindReplaceOptions インスタンスを作成します
FindReplaceOptions options = new FindReplaceOptions();
options.setUseSubstitutions(true);

//テキストをパターンに置き換える場合はオプションを使用します
doc.getRange().replace(Pattern.compile("([A-z]+) give money to ([A-z]+)"), "$2 take money from $1", options);

//変更したドキュメントを保存する
doc.save("modified-document.docx");
```

これにより、置換パターン内で置換を実行して、より高度な置換を行うことができます。

## 文字列に置き換える

Aspose.Words for Java を使用して、テキストを単純な文字列に置き換えることができます。

```java
//ドキュメントをロードする
Document doc = new Document("your-document.docx");

//テキストを文字列に置き換える
doc.getRange().replace("text-to-replace", "new-string", new FindReplaceOptions());

//変更したドキュメントを保存する
doc.save("modified-document.docx");
```

この例では、文書内の「置換するテキスト」を「新しい文字列」に置き換えます。

## 従来の注文の使用

検索および置換操作を実行するときに従来の順序を使用できます。

```java
//ドキュメントをロードする
Document doc = new Document("your-document.docx");

// FindReplaceOptions インスタンスを作成し、UseLegacyOrder を true に設定します。
FindReplaceOptions options = new FindReplaceOptions();
options.setUseLegacyOrder(true);

//テキストを置換するときにオプションを使用する
doc.getRange().replace(Pattern.compile("\\[(.*?)\\]"), "", options);

//変更したドキュメントを保存する
doc.save("modified-document.docx");
```

これにより、検索および置換操作に従来の順序を使用できるようになります。

## 表内のテキストの置換

Word 文書内の表内のテキストを検索して置換できます。

```java
//ドキュメントをロードする
Document doc = new Document("your-document.docx");

//特定のテーブル (最初のテーブルなど) を取得します。
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);

//テーブル内のテキストを置換するには FindReplaceOptions を使用します
table.getRange().replace("old-text", "new-text", new FindReplaceOptions());

//変更したドキュメントを保存する
doc.save("modified-document.docx");
```

これにより、特にテーブル内でテキストの置換を実行できるようになります。

## 結論

Aspose.Words for Java は、Word 文書内のテキストを検索および置換するための包括的な機能を提供します。単純なテキスト置換を実行する必要がある場合でも、正規表現、フィールド操作、またはカスタム エバリュエーターを使用したより高度な操作を実行する必要がある場合でも、Aspose.Words for Java が対応します。この強力な Java ライブラリの可能性を最大限に活用するには、Aspose が提供する広範なドキュメントと例を必ず調べてください。

## よくある質問

### Aspose.Words for Java をダウンロードするにはどうすればよいですか?

 Aspose.Words for Java は、次の Web サイトからダウンロードできます。[このリンク](https://releases.aspose.com/words/java/).

### テキストの置換に正規表現を使用できますか?

はい、Aspose.Words for Java では正規表現を使用してテキストを置換できます。これにより、より高度で柔軟な検索および置換操作を実行できるようになります。

### 置換中にフィールド内のテキストを無視するにはどうすればよいですか?

置換中にフィールド内のテキストを無視するには、`IgnoreFields`の財産`FindReplaceOptions`に`true`。これにより、差し込みフィールドなどのフィールド内のテキストが置換から除外されます。

### ヘッダーとフッター内のテキストを置き換えることはできますか?

はい、Word 文書のヘッダーとフッター内のテキストを置き換えることができます。適切なヘッダーまたはフッターにアクセスし、`replace`希望の方法で`FindReplaceOptions`.

### UseLegacyOrder オプションは何のためにありますか?

の`UseLegacyOrder`のオプション`FindReplaceOptions`を使用すると、検索および置換操作を実行するときに従来の順序を使用できます。これは、従来の注文動作が必要な特定のシナリオで役立ちます。