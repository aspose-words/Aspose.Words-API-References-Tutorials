---
title: Aspose.Words for Java でドキュメントを ODT 形式で保存する
linktitle: ドキュメントを ODT 形式で保存する
second_title: Aspose.Words Java ドキュメント処理 API
description: Aspose.Words for Java を使用してドキュメントを ODT 形式で保存する方法を学びます。オープンソースのオフィス スイートとの互換性を確保します。
type: docs
weight: 19
url: /ja/java/document-loading-and-saving/saving-documents-as-odt-format/
---

## Aspose.Words for Java でドキュメントを ODT 形式で保存する方法の概要

この記事では、Aspose.Words for Java を使用してドキュメントを ODT (Open Document Text) 形式で保存する方法を説明します。 ODT は、OpenOffice や LibreOffice などのさまざまなオフィス スイートで使用される一般的なオープン標準ドキュメント形式です。ドキュメントを ODT 形式で保存すると、これらのソフトウェア パッケージとの互換性を確保できます。

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

1. Java 開発環境: システムに Java Development Kit (JDK) がインストールされていることを確認します。

2.  Aspose.Words for Java: Aspose.Words for Java ライブラリをダウンロードしてインストールします。ダウンロードリンクが見つかります[ここ](https://releases.aspose.com/words/java/).

3. サンプル ドキュメント: ODT 形式に変換するサンプル Word ドキュメント (「Document.docx」など) を用意します。

## ステップ 1: ドキュメントをロードする

まず、Aspose.Words for Java を使用して Word ドキュメントをロードしましょう。

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
```

ここ、`"Your Directory Path"`ドキュメントが存在するディレクトリを指す必要があります。

## ステップ 2: ODT 保存オプションを指定する

ドキュメントを ODT として保存するには、ODT 保存オプションを指定する必要があります。さらに、ドキュメントの測定単位を設定できます。 Open Office はセンチメートルを使用しますが、MS Office はインチを使用します。それをインチに設定します。

```java
OdtSaveOptions saveOptions = new OdtSaveOptions();
saveOptions.setMeasureUnit(OdtSaveMeasureUnit.INCHES);
```

## ステップ 3: ドキュメントを保存する

次に、ドキュメントを ODT 形式で保存します。

```java
doc.save("Your Directory Path" + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

ここ、`"Your Directory Path"`は、変換された ODT ファイルを保存するディレクトリを指す必要があります。

## Aspose.Words for Java でドキュメントを ODT 形式で保存するための完全なソース コード

```java
Document doc = new Document("Your Directory Path" + "Document.docx");
//Open Office では、長さ、幅、その他の測定可能な形式を指定するときにセンチメートルを使用します。
// MS Office ではインチが使用されますが、ドキュメント内のコンテンツ プロパティはインチです。
OdtSaveOptions saveOptions = new OdtSaveOptions(); { saveOptions.setMeasureUnit(OdtSaveMeasureUnit.INCHES); }
doc.save("Your Directory Path" + "WorkingWithOdtSaveOptions.MeasureUnit.odt", saveOptions);
```

## 結論

この記事では、Aspose.Words for Java を使用してドキュメントを ODT 形式で保存する方法を学習しました。これは、OpenOffice や LibreOffice などのオープンソース オフィス スイートとの互換性を確保する必要がある場合に特に役立ちます。

## よくある質問

### Aspose.Words for Java をダウンロードするにはどうすればよいですか?

 Aspose.Words for Java は、Aspose Web サイトからダウンロードできます。訪問[このリンク](https://releases.aspose.com/words/java/)ダウンロードページにアクセスします。

### ドキュメントを ODT 形式で保存する利点は何ですか?

ドキュメントを ODT 形式で保存すると、OpenOffice や LibreOffice などのオープンソース オフィス スイートとの互換性が保証され、これらのソフトウェア パッケージのユーザーがドキュメントにアクセスして編集することが容易になります。

### ODT形式で保存する場合、測定単位を指定する必要がありますか?

はい、測定単位を指定することをお勧めします。 Open Office はデフォルトでセンチメートルを使用するため、インチに設定すると一貫した書式が確保されます。

### バッチ処理で複数のドキュメントを ODT 形式に変換できますか?

はい、Aspose.Words for Java を使用してドキュメント ファイルを反復処理し、変換プロセスを適用することで、複数のドキュメントの ODT 形式への変換を自動化できます。

### Aspose.Words for Java は最新の Java バージョンと互換性がありますか?

Aspose.Words for Java は、最新の Java バージョンをサポートするために定期的に更新され、互換性とパフォーマンスの向上が保証されます。最新情報については、ドキュメントのシステム要件を必ずご確認ください。