---
title: Word 文書を PDF 1.7 に変換
linktitle: Word 文書を PDF 1.7 に変換
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word ドキュメントを PDF 1.7 に変換する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-pdfsaveoptions/conversion-to-pdf-17/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word ドキュメントを PDF 1.7 に変換する手順を説明します。 PDF 1.7 に変換すると、PDF 1.7 標準に準拠した PDF ファイルを生成できます。以下の手順に従います。

## ステップ 1: ドキュメントをロードする

まず、PDF に変換するドキュメントをアップロードします。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

必ずドキュメントへの正しいパスを指定してください。

## ステップ 2: PDF 変換オプションを設定する

PdfSaveOptions クラスのインスタンスを作成し、使用する PDF 標準のバージョンを指定します。

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };
```

このオプションにより、生成された PDF ファイルが PDF 1.7 標準に準拠していることが保証されます。

## ステップ 3: ドキュメントを PDF に変換する

使用`Save`変換オプションを指定してドキュメントを PDF に変換するメソッド:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);
```

変換された PDF を保存するための正しいパスを指定してください。

### Aspose.Words for .NET を使用した PDF 17 への変換のソース コード例

Aspose.Words for .NET を使用して PDF 1.7 に変換する完全なソース コードは次のとおりです。

```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { Compliance = PdfCompliance.Pdf17 };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.ConversionToPdf17.pdf", saveOptions);

```

次の手順に従うと、Aspose.Words for .NET を使用して PDF 1.7 に簡単に変換できます。


## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書を PDF 1.7 に変換する方法を説明しました。説明されている手順に従うことで、PDF 1.7 標準に準拠した PDF ファイルを簡単に生成できます。 Word 文書への正しいパスを指定し、必要に応じて PDF に変換するオプションを構成してください。 PDF 1.7 に変換すると、さまざまなプラットフォームでの最適な互換性と読みやすさが保証されます。

### よくある質問

#### Q: Word から PDF 1.7 への変換とは何ですか?
A: Word 文書を PDF 1.7 に変換すると、PDF 1.7 標準に準拠した PDF ファイルが生成されます。この標準は PDF ファイルの機能と要件を指定し、さまざまなプラットフォームで最適な互換性と読みやすさを実現します。

#### Q: Aspose.Words for .NET を使用して Word 文書を PDF 1.7 に変換するにはどうすればよいですか?
A: Aspose.Words for .NET を使用して Word 文書を PDF 1.7 に変換するには、次の手順に従います。

を置き換えて、ドキュメントが配置されているディレクトリ パスを設定します。`"YOUR DOCUMENTS DIRECTORY"`ドキュメントディレクトリの実際のパスに置き換えます。

 PDF に変換したい Word 文書をロードします。`Document`クラスを指定し、指定したドキュメント ディレクトリ内の Word ドキュメントへのパスを指定します。

のインスタンスを作成して、PDF として変換オプションを構成します。`PdfSaveOptions`クラスを選択し、使用する PDF 標準のバージョンを指定します。`Compliance`値を持つプロパティ`PdfCompliance. Pdf17`PDF 1.7 標準に準拠した PDF ファイルを生成します。

ドキュメントを PDF 形式で保存するには、`Save`の方法`Document`パスと保存オプションを指定するクラス。

#### Q: Aspose.Words for .NET を使用して PDF 1.7 に変換する利点は何ですか?
A: Aspose.Words for .NET を使用して PDF 1.7 に変換する利点は次のとおりです。

PDF 1.7 準拠: PDF 1.7 に変換すると、生成された PDF ファイルが PDF 1.7 に準拠し、さまざまなプラットフォームでの互換性と読みやすさが保証されます。

ドキュメントの書式設定の保持: Aspose.Words for .NET は、書式設定、画像、スタイルを保持することで Word ドキュメントを正確に変換し、オリジナルに忠実な PDF ファイルを生成します。