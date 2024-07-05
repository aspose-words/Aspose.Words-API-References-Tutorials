---
title: 暗号化されたPDFを読み込む
linktitle: 暗号化されたPDFを読み込む
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して暗号化された PDF を読み込むためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-pdfloadoptions/load-encrypted-pdf/
---

.NET アプリケーションで PDF ドキュメントを Words 処理する場合、パスワードで保護された PDF ファイルを読み込む必要がある場合があります。Aspose.Words for .NET は、暗号化された PDF ドキュメントを読み込む機能を提供する強力なライブラリです。この記事では、この機能を理解して使用する方法を段階的に説明します。

## 暗号化されたPDFの読み込み機能について

Aspose.Words for .NET の暗号化された PDF の読み込み機能を使用すると、パスワードで保護された PDF ファイルを読み込むことができます。ドキュメントを読み込むときにパスワードを指定できるので、必要に応じてそのコンテンツにアクセスして操作することができます。

## ステップ1: 暗号化されたPDF文書の読み込み

最初のステップは、暗号化された PDF ドキュメントをアプリケーションに読み込むことです。手順は次のとおりです。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document doc = new Document(dataDir + "Document.pdf");
```

暗号化されたPDFファイルへの正しいパスを必ず指定してください。`dataDir`変数。

## ステップ2: PDF文書の暗号化

PDF文書を暗号化したい場合は、`PdfSaveOptions`クラスと暗号化の詳細を指定します。

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
EncryptionDetails = new PdfEncryptionDetails("Aspose", null)
};

```

これにより、指定されたディレクトリに PDF ドキュメントの暗号化バージョンが作成されます。

## ステップ3: 暗号化されたPDF文書を保存する

PDF ドキュメントをアップロードし、オプションで暗号化した後、別の形式で保存したり、特定のニーズに応じてさらに処理したりできます。

```csharp
doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", saveOptions);
```

## ステップ5: パスワード付き暗号化PDF文書の読み込み

メンテナンス

ただし、パスワード付きの暗号化されたPDF文書を読み込む場合は、`PdfLoadOptions`クラスを作成し、ドキュメントを読み込むときにパスワードを指定します。

```csharp
PdfLoadOptions loadOptions = new PdfLoadOptions { Password = "Aspose", LoadFormat = LoadFormat.Pdf };

doc = new Document(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", loadOptions);
```

必ず正しいパスワードを入力してください。`Password`変数。

### Aspose.Words for .NET を使用して暗号化された PDF を読み込むためのサンプル ソース コード

```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Pdf Document.pdf");

	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		EncryptionDetails = new PdfEncryptionDetails("Aspose", null)
	};

	doc.Save(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", saveOptions);

	PdfLoadOptions loadOptions = new PdfLoadOptions { Password = "Aspose", LoadFormat = LoadFormat.Pdf };

	doc = new Document(dataDir + "WorkingWithPdfLoadOptions.LoadEncryptedPdf.pdf", loadOptions);
        
```

## 結論

この記事では、Aspose.Words for .NET の暗号化された PDF の読み込み機能の使い方について説明しました。暗号化された PDF ファイルをアップロードする方法、PDF ドキュメントを暗号化する方法、パスワード付きの暗号化された PDF をアップロードする方法、および Markdown 形式で出力を生成する方法を学習しました。この機能は、セキュリティで保護された PDF ドキュメントで Words Processing を実行する場合に非常に便利です。


