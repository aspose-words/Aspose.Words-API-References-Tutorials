---
title: Aspose.Words for Java でドキュメントを PDF として保存
linktitle: ドキュメントを PDF として保存する
second_title: Aspose.Words Java ドキュメント処理 API
description: Aspose.Words for Java を使用して Word ドキュメントを PDF として保存する方法を学びます。フォント、プロパティ、画質をカスタマイズします。 PDF 変換に関する包括的なガイド。
type: docs
weight: 22
url: /ja/java/document-loading-and-saving/saving-documents-as-pdf/
---

## Aspose.Words for Java でドキュメントを PDF として保存する方法の概要

このステップバイステップ ガイドでは、Aspose.Words for Java を使用してドキュメントを PDF として保存する方法を説明します。 PDF 変換のさまざまな側面を説明し、プロセスを容易にするコード例を提供します。

## 前提条件

始める前に、次の前提条件が満たされていることを確認してください。

- Java Development Kit (JDK) がシステムにインストールされています。
-  Aspose.Words for Java ライブラリ。からダウンロードできます[ここ](https://releases.aspose.com/words/java/).

## ドキュメントを PDF に変換する

Word 文書を PDF に変換するには、次のコード スニペットを使用できます。

```java
Document doc = new Document("input.docx");
PdfSaveOptions saveOptions = new PdfSaveOptions();
doc.save("output.pdf", saveOptions);
```

交換する`"input.docx"` Word 文書へのパスと`"output.pdf"`目的の出力 PDF ファイルのパスを指定します。

## PDF 保存オプションの制御

を使用して、さまざまな PDF 保存オプションを制御できます。`PdfSaveOptions`クラス。たとえば、次のように PDF ドキュメントの表示タイトルを設定できます。

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setDisplayDocTitle(true);
doc.save("output.pdf", saveOptions);
```

## PDF へのフォントの埋め込み

生成された PDF にフォントを埋め込むには、次のコードを使用します。

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setEmbedFullFonts(true);
doc.save("output.pdf", saveOptions);
```

## ドキュメントのプロパティのカスタマイズ

生成された PDF のドキュメントのプロパティをカスタマイズできます。例えば：

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setCustomPropertiesExport(PdfCustomPropertiesExport.STANDARD);
doc.save("output.pdf", saveOptions);
```

## ドキュメント構造のエクスポート

ドキュメント構造をエクスポートするには、`exportDocumentStructure`というオプション`true`:

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setExportDocumentStructure(true);
doc.save("output.pdf", saveOptions);
```

## 画像圧縮

次のコードを使用して画像圧縮を制御できます。

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setImageCompression(PdfImageCompression.JPEG);
doc.save("output.pdf", saveOptions);
```

## 最後に印刷されたプロパティの更新

PDF の「最終印刷」プロパティを更新するには、次を使用します。

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setUpdateLastPrintedProperty(true);
doc.save("output.pdf", saveOptions);
```

## DML 3D 効果のレンダリング

DML 3D 効果の高度なレンダリングを行うには、レンダリング モードを設定します。

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setDml3DEffectsRenderingMode(Dml3DEffectsRenderingMode.ADVANCED);
doc.save("output.pdf", saveOptions);
```

## 画像の補間

画像補間を有効にして画質を向上させることができます。

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setInterpolateImages(true);
doc.save("output.pdf", saveOptions);
```

## 結論

Aspose.Words for Java は、柔軟性とカスタマイズ オプションを備えた Word ドキュメントを PDF 形式に変換するための包括的な機能を提供します。フォント、ドキュメントのプロパティ、画像圧縮など、PDF 出力のさまざまな側面を制御できます。

## よくある質問

### Aspose.Words for Java を使用して Word 文書を PDF に変換するにはどうすればよいですか?

Word 文書を PDF に変換するには、次のコードを使用します。

```java
Document doc = new Document("input.docx");
PdfSaveOptions saveOptions = new PdfSaveOptions();
doc.save("output.pdf", saveOptions);
```

交換する`"input.docx"` Word 文書へのパスと`"output.pdf"`目的の出力 PDF ファイルのパスを指定します。

### Aspose.Words for Java で生成された PDF にフォントを埋め込むことはできますか?

はい、次の設定を行うことで PDF にフォントを埋め込むことができます。`setEmbedFullFonts`というオプション`true`で`PdfSaveOptions`。以下に例を示します。

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setEmbedFullFonts(true);
doc.save("output.pdf", saveOptions);
```

### 生成された PDF のドキュメント プロパティをカスタマイズするにはどうすればよいですか?

 PDF 内のドキュメントのプロパティをカスタマイズするには、`setCustomPropertiesExport`のオプション`PdfSaveOptions`。例えば：

```java
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.setCustomPropertiesExport(PdfCustomPropertiesExport.STANDARD);
doc.save("output.pdf", saveOptions);
```

### Aspose.Words for Java での画像圧縮の目的は何ですか?

画像圧縮を使用すると、生成される PDF 内の画像の品質とサイズを制御できます。画像圧縮モードは次を使用して設定できます。`setImageCompression`で`PdfSaveOptions`.

### PDF の「最終印刷」プロパティを更新するにはどうすればよいですか?

設定することで、PDF の「最終印刷日」プロパティを更新できます。`setUpdateLastPrintedProperty`に`true`で`PdfSaveOptions`。これにより、PDF メタデータの最終印刷日が反映されます。

### PDF に変換する際の画質を向上するにはどうすればよいですか?

画質を向上させるには、設定で画像補間を有効にします。`setInterpolateImages`に`true`で`PdfSaveOptions`。これにより、PDF 内の画像がより滑らかで高品質になります。