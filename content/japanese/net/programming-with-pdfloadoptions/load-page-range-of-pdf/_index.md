---
title: PDF のページ範囲を読み込む
linktitle: PDF のページ範囲を読み込む
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して特定の PDF ページ範囲を読み込むためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-pdfloadoptions/load-page-range-of-pdf/
---

このチュートリアルでは、Aspose.Words for .NET を使用して PDF ドキュメントから特定のページ範囲を読み込む方法について説明します。以下の手順に従ってください。

## ステップ1: PDFページの範囲を読み込む

PDF ドキュメントから特定のページ範囲を読み込むには、次のコードを使用します。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);
```

この例では、PDF文書の最初のページを読み込んでいます。`PageIndex`そして`PageCount`目的のページ範囲に。

## ステップ2: ドキュメントを保存する

最後に、特定のページ範囲を含む文書を`Save`方法：

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
```

編集したドキュメントを保存するには、必ず正しいパスを指定してください。

以上です。Aspose.Words for .NET を使用して PDF ドキュメントから特定のページ範囲を読み込むことができました。

### Aspose.Words for .NET を使用して PDF のページ範囲を読み込むためのサンプル ソース コード

```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

	
	Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
   
```
PDF ドキュメントのディレクトリへの正しいパスを必ず指定してください。



