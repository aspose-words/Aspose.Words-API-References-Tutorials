---
title: Word 文書を PDF に変換する 1.7
linktitle: Word 文書を PDF に変換する 1.7
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書を PDF 1.7 に変換する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-pdfsaveoptions/conversion-to-pdf-17/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書を PDF 1.7 に変換する手順を説明します。PDF 1.7 に変換すると、PDF 1.7 標準に準拠した PDF ファイルを生成できます。以下の手順に従ってください。

## ステップ1: ドキュメントの読み込み

まず、PDF に変換したいドキュメントをアップロードします。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

ドキュメントへの正しいパスを必ず指定してください。

## ステップ2: PDF変換オプションを設定する

PdfSaveOptions クラスのインスタンスを作成し、使用する PDF 標準のバージョンを指定します。

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };
```

このオプションにより、生成された PDF ファイルが PDF 1.7 標準に準拠していることが保証されます。

## ステップ3: ドキュメントをPDFに変換する

使用`Save`変換オプションを指定してドキュメントを PDF に変換する方法:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);
```

変換した PDF を保存するには、正しいパスを指定してください。

### Aspose.Words for .NET を使用して PDF 17 に変換するためのサンプル ソース コード

Aspose.Words for .NET を使用して PDF 1.7 に変換するための完全なソース コードは次のとおりです。

```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);

```

これらの手順に従うと、Aspose.Words for .NET を使用して簡単に PDF 1.7 に変換できます。


## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書を PDF 1.7 に変換する方法について説明しました。説明されている手順に従うことで、PDF 1.7 標準に準拠した PDF ファイルを簡単に生成できます。Word 文書への正しいパスを指定し、必要に応じて PDF に変換するためのオプションを構成するようにしてください。PDF 1.7 への変換により、さまざまなプラットフォームで最適な互換性と読みやすさが確保されます。

### よくある質問

#### Q: Word から PDF 1.7 への変換とは何ですか?
A: Word 文書を PDF 1.7 に変換すると、PDF 1.7 標準に準拠した PDF ファイルが生成されます。この標準では、PDF ファイルの機能と要件が指定されており、さまざまなプラットフォームで最適な互換性と読みやすさが実現されます。

#### Q: Aspose.Words for .NET を使用して Word 文書を PDF 1.7 に変換するにはどうすればよいですか?
A: Aspose.Words for .NET を使用して Word 文書を PDF 1.7 に変換するには、次の手順に従います。

ドキュメントが保存されているディレクトリパスを次のように設定します。`"YOUR DOCUMENTS DIRECTORY"`ドキュメント ディレクトリの実際のパスを入力します。

 PDFに変換したいWord文書を読み込み、`Document`クラスを作成し、指定されたドキュメント ディレクトリ内の Word ドキュメントへのパスを指定します。

 PDFオプションとして変換するには、`PdfSaveOptions`クラスと使用したいPDF標準のバージョンを指定するには、`Compliance`値を持つプロパティ`PdfCompliance. Pdf17`PDF 1.7 標準に準拠した PDF ファイルを生成します。

ドキュメントをPDF形式で保存するには、`Save`方法の`Document`パスと保存オプションを指定するクラス。

#### Q: Aspose.Words for .NET を使用して PDF 1.7 に変換する利点は何ですか?
A: Aspose.Words for .NET を使用して PDF 1.7 に変換する利点は次のとおりです。

PDF 1.7 準拠: PDF 1.7 に変換すると、生成された PDF ファイルが PDF 1.7 に準拠し、さまざまなプラットフォームでの互換性と読みやすさが確保されます。

ドキュメントの書式設定の保持: Aspose.Words for .NET は、書式設定、画像、スタイルを保持することで Word ドキュメントの正確な変換を保証し、元の PDF ファイルに忠実な結果をもたらします。