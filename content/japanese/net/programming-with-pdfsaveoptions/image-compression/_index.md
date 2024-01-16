---
title: PDF ドキュメントの画像圧縮
linktitle: PDF ドキュメントの画像圧縮
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して PDF ドキュメント内の画像を圧縮するためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-pdfsaveoptions/image-compression/
---

この記事では、Aspose.Words for .NET で PDF ドキュメントの画像圧縮機能を使用する方法をステップごとに説明します。コードの各部分について詳しく説明します。このチュートリアルを終えると、ドキュメント内の画像を圧縮し、適切な画像圧縮を使用して PDF を生成する方法を理解できるようになります。

開始する前に、プロジェクトに Aspose.Words for .NET ライブラリがインストールされ、構成されていることを確認してください。ライブラリとインストール手順は、Aspose Web サイトで見つけることができます。

## ステップ 1: ドキュメント ディレクトリを定義する

まず、ドキュメントが配置されているディレクトリへのパスを定義する必要があります。交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリへの実際のパスを含めます。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: ドキュメントをアップロードする

次に、処理するドキュメントをロードする必要があります。この例では、ドキュメントが「Rendering.docx」という名前で、指定されたドキュメント ディレクトリに配置されていると仮定します。

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## ステップ 3: 画像圧縮を使用して PDF として保存オプションを構成する

PDF に変換するときに画像を圧縮するには、`PdfSaveOptions`物体。必要に応じて、画像圧縮タイプ、JPEG 品質、その他の PDF 準拠オプションを設定できます。

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
ImageCompression = PdfImageCompression.Jpeg,
PreserveFormFields = true
};
```

## ステップ 4: 画像圧縮を使用してドキュメントを PDF として保存する

最後に、前に設定した保存オプションを使用してドキュメントを PDF 形式で保存できます。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression.pdf", saveOptions);
```

## ステップ 5: 画像圧縮を使用して PDF/A-2u に保存するためのオプションを構成する

画像圧縮を使用して PDF/A-2u 準拠の PDF を生成する場合は、追加の保存オプションを構成できます。

```csharp
PdfSaveOptions saveOptionsA2U = new PdfSaveOptions
{
Compliance = PdfCompliance.PdfA2u,
ImageCompression = PdfImageCompression.Jpeg,
JpegQuality=100, //ファイル サイズを削減するには、50% の品質の JPEG 圧縮を使用します。
};
```

## ステップ 6: 画像圧縮を使用してドキュメントを PDF/A-2u として保存する

前に構成した追加の保存オプションを使用して、ドキュメントを PDF/A-2u 形式で保存します。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
```



それだけです ！ Aspose.Words for .NET を使用して、ドキュメント内の画像を正常に圧縮し、適切な画像圧縮を使用して PDF を生成しました。

### Aspose.Words for .NET を使用して画像を圧縮するためのサンプル ソース コード

```csharp

	//ドキュメントディレクトリへのパス。
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
		JpegQuality = 100, //ファイル サイズを小さくするには、50% の品質で JPEG 圧縮を使用します。
	};

	

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.PdfImageCompression_A2u.pdf", saveOptionsA2U);
	
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して PDF ドキュメント内の画像を圧縮する方法を説明しました。ここで説明する手順に従うことで、PDF ドキュメント内の画像のサイズを簡単に縮小し、適切な画像圧縮を使用して PDF を生成できます。 Aspose.Words for .NET の画像圧縮機能を使用して、画質を維持しながら PDF ドキュメントのサイズを最適化します。

### よくある質問

#### Q: PDF ドキュメントの画像圧縮とは何ですか?
A: PDF ドキュメント内の画像の圧縮とは、PDF ドキュメントに含まれる画像のサイズを縮小して、PDF ファイル全体のサイズを小さくすることです。これにより、必要なストレージ容量が削減され、PDF のロードおよび表示時のパフォーマンスが向上します。

#### Q: Aspose.Words for .NET を使用して PDF ドキュメント内の画像を圧縮するにはどうすればよいですか?
A: Aspose.Words for .NET を使用して PDF ドキュメント内の画像を圧縮するには、次の手順に従います。

のインスタンスを作成します。`Document` Word ドキュメントへのパスを指定するクラス。

のインスタンスを作成します。`PdfSaveOptions`クラスを設定して、`ImageCompression`財産を`PdfImageCompression.Jpeg` JPEG圧縮を使用します。

必要に応じて、JPEG 品質などの他の画像圧縮オプションを設定することもできます。

使用`Save`の方法`Document`保存オプションを指定してドキュメントを PDF 形式で保存するクラス。

#### Q: 標準の画像圧縮と PDF/A-2u 画像圧縮の違いは何ですか?
A: 標準の画像圧縮により、フォーム フィールドを維持しながら PDF ドキュメント内の画像のサイズが削減されます。これにより、フォーム フィールドの機能を損なうことなく PDF ファイル全体のサイズが削減されます。

PDF/A-2u による画像圧縮は、画像圧縮を適用しながら PDF/A-2u 標準に準拠した PDF ファイルを生成できる追加オプションです。 PDF/A-2u は、アーカイブ PDF ドキュメントの ISO 標準であり、ドキュメントの長期保存を保証します。
