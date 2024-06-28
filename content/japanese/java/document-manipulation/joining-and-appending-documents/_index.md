---
title: Aspose.Words for Java でのドキュメントの結合と追加
linktitle: ドキュメントの結合と追加
second_title: Aspose.Words Java ドキュメント処理 API
description: Aspose.Words for Java を使用してドキュメントを簡単に結合および追加する方法を学びます。書式設定の保持、ヘッダー フッターなどの管理。
type: docs
weight: 30
url: /ja/java/document-manipulation/joining-and-appending-documents/
---

## Aspose.Words for Java でのドキュメントの結合と追加の概要

このチュートリアルでは、Aspose.Words for Java ライブラリを使用してドキュメントを結合および追加する方法を説明します。書式設定と構造を維持しながら複数のドキュメントをシームレスに結合する方法を学びます。

## 前提条件

始める前に、Java プロジェクトに Aspose.Words for Java API が設定されていることを確認してください。

## ドキュメント結合オプション

### 単純な追加

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### インポート形式オプションを使用して追加

```java
ImportFormatOptions options = new ImportFormatOptions();
options.setKeepSourceNumbering(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES, options);
```

### 空白の文書に追加

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document();
dstDoc.removeAllChildren();
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### ページ番号変換による追加

```java
Document srcDoc = new Document("source.docx");
Document dstDoc = new Document("destination.docx");
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
convertNumPageFieldsToPageRef(dstDoc); //NUMPAGES フィールドを変換する
dstDoc.updatePageLayout(); //正しい番号付けのためにページ レイアウトを更新する
```

## さまざまなページ設定の処理

異なるページ設定のドキュメントを追加する場合:

```java
srcDoc.getFirstSection().getPageSetup().setSectionStart(SectionStart.CONTINUOUS);
srcDoc.getFirstSection().getPageSetup().setRestartPageNumbering(true);
//ページ設定設定が宛先ドキュメントと一致していることを確認してください
```

## 異なるスタイルのドキュメントを結合する

```java
dstDoc.appendDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES);
```

## スマートなスタイルの動作

```java
ImportFormatOptions options = new ImportFormatOptions();
options.setSmartStyleBehavior(true);
builder.insertDocument(srcDoc, ImportFormatMode.USE_DESTINATION_STYLES, options);
```

## DocumentBuilder を使用したドキュメントの挿入

```java
DocumentBuilder builder = new DocumentBuilder(dstDoc);
builder.insertDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

## ソースの番号付けを維持する

```java
ImportFormatOptions importFormatOptions = new ImportFormatOptions();
importFormatOptions.setKeepSourceNumbering(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING, importFormatOptions);
```

## テキストボックスの処理

```java
ImportFormatOptions importFormatOptions = new ImportFormatOptions();
importFormatOptions.setIgnoreTextBoxes(false);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING, importFormatOptions);
```

## ヘッダーとフッターの管理

### ヘッダーとフッターのリンク

```java
srcDoc.getFirstSection().getHeadersFooters().linkToPrevious(true);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

### ヘッダーとフッターのリンクを解除する

```java
srcDoc.getFirstSection().getHeadersFooters().linkToPrevious(false);
dstDoc.appendDocument(srcDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
```

## 結論

Aspose.Words for Java は、書式設定の維持、さまざまなページ設定の処理、またはヘッダーとフッターの管理が必要な場合でも、ドキュメントを結合および追加するための柔軟で強力なツールを提供します。特定のドキュメント処理のニーズを満たすために、これらの手法を試してください。

## よくある質問

### 異なるスタイルのドキュメントをシームレスに結合するにはどうすればよいですか?

異なるスタイルのドキュメントを結合するには、次を使用します。`ImportFormatMode.USE_DESTINATION_STYLES`追加するとき。

### ドキュメントを追加するときにページ番号を保持できますか?

はい、次を使用してページ番号を保持できます。`convertNumPageFieldsToPageRef`方法とページレイアウトの更新。

### スマートスタイルの行動とは何ですか?

スマート スタイル動作は、ドキュメントを追加するときに一貫したスタイルを維持するのに役立ちます。と一緒に使用してください`ImportFormatOptions`より良い結果を得るために。

### ドキュメントを追加するときにテキスト ボックスを処理するにはどうすればよいですか?

セット`importFormatOptions.setIgnoreTextBoxes(false)`追加時にテキスト ボックスを含めるには。

### ドキュメント間のヘッダーとフッターをリンクまたはリンク解除したい場合はどうすればよいですか?

ヘッダーとフッターをリンクできます`linkToPrevious(true)`またはリンクを解除します`linkToPrevious(false)`必要に応じて。