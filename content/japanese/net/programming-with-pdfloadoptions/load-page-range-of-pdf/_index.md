---
title: PDF のページ範囲をロード
linktitle: PDF のページ範囲をロード
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して特定の PDF ページ範囲を読み込むためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-pdfloadoptions/load-page-range-of-pdf/
---

このチュートリアルでは、Aspose.Words for .NET を使用して PDF ドキュメントから特定のページ範囲を読み込む方法を説明します。以下の手順に従います。

## ステップ 1: PDF ページの範囲をロードする

PDF ドキュメントから特定のページ範囲をロードするには、次のコードを使用します。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";

PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);
```

この例では、PDF ドキュメントの最初のページをロードしています。の値を変更できます`PageIndex`そして`PageCount`希望のページ範囲に移動します。

## ステップ 2: ドキュメントを保存する

最後に、`Save`方法：

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
```

編集したドキュメントを保存するには、必ず正しいパスを指定してください。

それだけです ！これで、Aspose.Words for .NET を使用して PDF ドキュメントから特定のページ範囲が読み込まれました。

### Aspose.Words for .NET を使用した PDF のページ範囲の読み込みのソース コード例

```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	PdfLoadOptions loadOptions = new PdfLoadOptions { PageIndex = 0, PageCount = 1 };

	
	Document doc = new Document(dataDir + "Pdf Document.pdf", loadOptions);

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadPageRangeOfPdf.pdf");
   
```
PDF ドキュメントのディレクトリへの正しいパスを忘れずに指定してください。



