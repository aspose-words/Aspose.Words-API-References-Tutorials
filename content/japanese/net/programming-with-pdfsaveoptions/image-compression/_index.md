---
title: PDF 文書内の画像圧縮
linktitle: PDF 文書内の画像圧縮
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して PDF ドキュメント内の画像を圧縮する手順ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-pdfsaveoptions/image-compression/
---

この記事では、Aspose.Words for .NET の PDF ドキュメントでの画像圧縮機能を使用する方法について、ステップ バイ ステップで説明します。コードの各部分を詳しく説明します。このチュートリアルの最後には、ドキュメント内の画像を圧縮し、適切な画像圧縮で PDF を生成する方法を理解できるようになります。

開始する前に、プロジェクトに Aspose.Words for .NET ライブラリがインストールされ、構成されていることを確認してください。ライブラリとインストール手順は、Aspose Web サイトで参照できます。

## ステップ1: ドキュメントディレクトリを定義する

まず、ドキュメントが保存されているディレクトリへのパスを定義する必要があります。`"YOUR DOCUMENT DIRECTORY"`ドキュメント ディレクトリへの実際のパスを入力します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ2: ドキュメントをアップロードする

次に、処理するドキュメントを読み込む必要があります。この例では、ドキュメントの名前は「Rendering.docx」で、指定されたドキュメント ディレクトリにあると想定しています。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## ステップ3: 画像圧縮によるPDF保存オプションを設定する

PDFに変換するときに画像を圧縮するには、`PdfSaveOptions`オブジェクト。必要に応じて、画像圧縮タイプ、JPEG 品質、その他の PDF 準拠オプションを設定できます。

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
ImageCompression = PdfImageCompression.Jpeg,
PreserveFormFields = true
};
```

## ステップ4: 画像圧縮を使用してドキュメントをPDFとして保存する

最後に、以前に設定した保存オプションを使用して、ドキュメントを PDF 形式で保存できます。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);
```

## ステップ5: 画像圧縮でPDF/A-2uに保存するためのオプションを設定する

画像圧縮を使用して PDF/A-2u 準拠の PDF を生成する場合は、追加の保存オプションを設定できます。

```csharp
PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
{
Compliance = PdfCompliance.PdfA2u,
ImageCompression = PdfImageCompression.Jpeg,
JpegQuality=100, //ファイル サイズを縮小するには、50% 品質の JPEG 圧縮を使用します。
};
```

## ステップ6: 画像圧縮されたPDF/A-2uとして文書を保存する

以前に設定した追加の保存オプションを使用して、ドキュメントを PDF/A-2u 形式で保存します。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
```



これで完了です。Aspose.Words for .NET を使用して、ドキュメント内の画像を正常に圧縮し、適切な画像圧縮で PDF を生成できました。

### Aspose.Words for .NET で画像を圧縮するためのサンプル ソース コード

```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		ImageCompression = PdfImageCompression.Jpeg, PreserveFormFields = true
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);

	PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
	{
		Compliance = PdfCompliance.PdfA2u,
		ImageCompression = PdfImageCompression.Jpeg,
		JpegQuality = 100, //ファイル サイズを縮小するには、50% の品質で JPEG 圧縮を使用します。
	};

	

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
	
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して PDF ドキュメント内の画像を圧縮する方法を説明しました。説明されている手順に従うことで、PDF ドキュメント内の画像のサイズを簡単に縮小し、適切な画像圧縮で PDF を生成できます。Aspose.Words for .NET の画像圧縮機能を使用して、画像の品質を維持しながら PDF ドキュメントのサイズを最適化します。

### よくある質問

#### Q: PDF 文書における画像圧縮とは何ですか?
A: PDF ドキュメント内の画像を圧縮すると、PDF ドキュメントに含まれる画像のサイズが縮小され、PDF ファイル全体のサイズが縮小されます。これにより、必要なストレージ容量が削減され、PDF の読み込みと表示時のパフォーマンスが向上します。

#### Q: Aspose.Words for .NET を使用して PDF ドキュメント内の画像を圧縮するにはどうすればよいですか?
A: Aspose.Words for .NET を使用して PDF ドキュメント内の画像を圧縮するには、次の手順に従います。

インスタンスを作成する`Document` Word 文書へのパスを指定するクラス。

インスタンスを作成する`PdfSaveOptions`クラスを設定し、`ImageCompression`財産に`PdfImageCompression.Jpeg` JPEG 圧縮を使用します。

必要に応じて、JPEG 品質などの他の画像圧縮オプションを設定することもできます。

使用`Save`方法の`Document`保存オプションを指定してドキュメントを PDF 形式で保存するクラス。

#### Q: 標準画像圧縮と PDF/A-2u 画像圧縮の違いは何ですか?
A: 標準的な画像圧縮では、フォーム フィールドを保持しながら PDF ドキュメント内の画像のサイズが縮小されます。これにより、フォーム フィールドの機能を損なうことなく、PDF ファイル全体のサイズが縮小されます。

PDF/A-2u による画像圧縮は、画像圧縮を適用しながら PDF/A-2u 標準に準拠した PDF ファイルを生成できる追加オプションです。PDF/A-2u はアーカイブ PDF ドキュメントの ISO 標準であり、ドキュメントの長期保存を保証します。
