---
title: 画像のダウンサンプリングでPDF文書のサイズを縮小
linktitle: 画像のダウンサンプリングでPDF文書のサイズを縮小
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して PDF に変換するときに、画像をダウンサンプリングして PDF ドキュメントのサイズを縮小する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-pdfsaveoptions/downsampling-images/
---

このチュートリアルでは、Aspose.Words for .NET を使用して PDF に変換するときに、画像をダウンサンプリングして PDF ドキュメントのサイズを縮小する手順を説明します。これにより、生成される PDF ファイルのサイズが縮小されます。以下の手順に従ってください。

## ステップ1: ドキュメントの読み込み

まず、PDF に変換したいドキュメントをアップロードします。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

ドキュメントへの正しいパスを必ず指定してください。

## ステップ2: PDF保存オプションを設定する

PdfSaveOptions クラスのインスタンスを作成し、画像の縮小オプションを設定します。

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
};
```

の`Resolution`プロパティは画像のターゲット解像度を指定し、`ResolutionThreshold`プロパティは、画像が縮小されない最小解像度を指定します。

## ステップ3: ドキュメントをPDFに変換する

使用`Save`保存オプションを指定してドキュメントを PDF に変換する方法:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);
```

変換した PDF を保存するには、正しいパスを指定してください。

### Aspose.Words for .NET を使用して画像をダウンサンプリングするためのサンプル ソース コード

```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	//ダウンサンプリングの最小しきい値を設定できます。
	//この値により、入力ドキュメント内の 2 番目の画像がダウンサンプリングされなくなります。
	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);

```

これらの手順に従うと、Aspose.Words for .NET を使用して PDF に変換するときに、画像の解像度を簡単に下げることができます。

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して PDF に変換するときに、画像サンプリングを使用して PDF ドキュメントのサイズを縮小する方法について説明しました。説明されている手順に従うことで、画像の解像度と生成される PDF ファイルのサイズを簡単に縮小できます。ドキュメントへの正しいパスを指定し、必要に応じて画像サンプリング オプションを構成するようにしてください。PDF ファイルのサイズを縮小すると、さまざまなプラットフォームでファイルを共有、保存、およびすばやく読み込むことが容易になります。Aspose.Words for .NET を使用して、画像サンプリングを使用して PDF ドキュメントのサイズを縮小するメリットを享受してください。

### よくある質問

#### Q: 画像サンプリングによる PDF ドキュメントのサイズ縮小とは何ですか?
A: 画像サンプリングを使用して PDF ドキュメントのサイズを縮小すると、PDF に変換するときに画像の解像度を下げることで、生成される PDF ファイルのサイズが小さくなります。これにより、ストレージ スペースの使用が最適化され、PDF ファイルの共有や転送が容易になります。

#### Q: Aspose.Words for .NET を使用して画像サンプリングを行い、PDF ドキュメントのサイズを縮小するにはどうすればよいですか?
A: Aspose.Words for .NET を使用して画像サンプリングにより PDF ドキュメントのサイズを縮小するには、次の手順に従います。

ドキュメントが保存されているディレクトリパスを次のように設定します。`"YOUR DOCUMENTS DIRECTORY"`ドキュメント ディレクトリの実際のパスを入力します。

 PDFに変換したい文書を読み込み、`Document`クラスを作成し、指定されたドキュメント ディレクトリ内のドキュメントへのパスを指定します。

 PDFとして保存オプションを設定するには、`PdfSaveOptions`クラスと画像サンプリングオプションの設定`DownsampleOptions`プロパティを使用して、画像のターゲット解像度を指定できます。`Resolution`プロパティを設定し、それを超える画像は縮小されない最小解像度のしきい値を設定します。`ResolutionThreshold`財産。

ドキュメントをPDF形式で保存するには、`Save`方法の`Document`パスと保存オプションを指定するクラス。

#### Q: 画像サンプリングを使用して PDF ドキュメントのサイズを縮小する利点は何ですか?
A: 画像サンプリングを使用して PDF ドキュメントのサイズを縮小する利点は次のとおりです。

PDF ファイル サイズの縮小: 画像サンプリングにより、PDF ドキュメント内の画像の解像度が低減され、PDF ファイル サイズが大幅に縮小されます。これにより、特に電子メールやオンラインでのファイルの共有や転送が容易になります。

ストレージ スペースの最適化: PDF ファイルのサイズを縮小すると、特に高解像度の画像を含む PDF ファイルが多数ある場合に、ストレージ スペースの使用を最適化できます。

パフォーマンスの向上: 小さい PDF ファイルはより速く読み込まれ、さまざまなデバイスでより速く開いて表示できます。