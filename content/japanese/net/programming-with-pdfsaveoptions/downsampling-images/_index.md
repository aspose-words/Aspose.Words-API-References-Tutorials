---
title: 画像のダウンサンプリングにより PDF ドキュメントのサイズを削減
linktitle: 画像のダウンサンプリングにより PDF ドキュメントのサイズを削減
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して PDF に変換するときに、画像をダウンサンプリングして PDF ドキュメントのサイズを削減する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-pdfsaveoptions/downsampling-images/
---

このチュートリアルでは、Aspose.Words for .NET を使用して PDF に変換する際に、画像をダウンサンプリングして PDF ドキュメントのサイズを削減する手順を説明します。これにより、生成される PDF ファイルのサイズが小さくなります。以下の手順に従います。

## ステップ 1: ドキュメントをロードする

まず、PDF に変換するドキュメントをアップロードします。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

必ずドキュメントへの正しいパスを指定してください。

## ステップ 2: PDF 保存オプションを構成する

PdfSaveOptions クラスのインスタンスを作成し、画像のダウンスケーリング オプションを設定します。

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions
{
DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
};
```

の`Resolution`プロパティは画像のターゲット解像度を指定し、`ResolutionThreshold`このプロパティは、画像が縮小されない最小解像度を指定します。

## ステップ 3: ドキュメントを PDF に変換する

使用`Save`保存オプションを指定してドキュメントを PDF に変換するメソッド:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);
```

変換された PDF を保存するための正しいパスを指定してください。

### Aspose.Words for .NET を使用したダウンサンプリング画像のソース コードの例

```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	//ダウンサンプリングの最小しきい値を設定できます。
	//この値により、入力ドキュメントの 2 番目の画像がダウンサンプリングされなくなります。
	PdfSaveOptions saveOptions = new PdfSaveOptions
	{
		DownsampleOptions = { Resolution = 36, ResolutionThreshold = 128 }
	};

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DownsamplingImages.pdf", saveOptions);

```

これらの手順に従うことで、Aspose.Words for .NET を使用して PDF に変換するときに画像の解像度を簡単に下げることができます。

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して PDF に変換する際に、画像サンプリングを使用して PDF ドキュメントのサイズを削減する方法を説明しました。ここで説明する手順に従うことで、画像の解像度と生成される PDF ファイルのサイズを簡単に減らすことができます。必ずドキュメントへの正しいパスを指定し、必要に応じて画像サンプリング オプションを構成してください。 PDF ファイルのサイズを小さくすると、さまざまなプラットフォームでのファイルの共有、保存、迅速なロードが容易になります。 Aspose.Words for .NET を使用した画像サンプリングにより、PDF ドキュメントのサイズを削減するメリットを享受してください。

### よくある質問

#### Q: 画像サンプリングを使用して PDF ドキュメントのサイズを削減するとは何ですか?
A: 画像サンプリングによる PDF ドキュメント サイズの削減とは、PDF への変換時に画像の解像度を下げることで、生成される PDF ファイルのサイズを削減することです。これにより、ストレージスペースの使用が最適化され、PDF ファイルの共有と転送が容易になります。

#### Q: Aspose.Words for .NET を使用して画像サンプリングを行い、PDF ドキュメントのサイズを削減するにはどうすればよいですか?
A: Aspose.Words for .NET を使用して画像サンプリングにより PDF ドキュメントのサイズを削減するには、次の手順に従います。

を置き換えて、ドキュメントが配置されているディレクトリ パスを設定します。`"YOUR DOCUMENTS DIRECTORY"`ドキュメントディレクトリの実際のパスに置き換えます。

 PDF に変換したいドキュメントをロードします。`Document`クラスを作成し、指定されたドキュメント ディレクトリ内のドキュメントへのパスを指定します。

のインスタンスを作成して、PDF として保存オプションを構成します。`PdfSaveOptions`クラスを使用し、画像サンプリング オプションを設定します。`DownsampleOptions`財産。画像のターゲット解像度を指定するには、`Resolution`プロパティを使用して、画像が縮小されない最小解像度のしきい値を設定します。`ResolutionThreshold`財産。

ドキュメントを PDF 形式で保存するには、`Save`の方法`Document`パスと保存オプションを指定するクラス。

#### Q: 画像サンプリングを使用して PDF ドキュメントのサイズを削減すると、どのような利点がありますか?
A: 画像サンプリングを使用して PDF ドキュメントのサイズを削減する利点は次のとおりです。

PDF ファイル サイズの縮小: 画像サンプリングにより PDF ドキュメント内の画像の解像度が低下し、PDF ファイル サイズが大幅に減少します。これにより、特に電子メールやオンライン経由でファイルの共有や転送が簡単になります。

記憶域スペースの最適化: PDF ファイルのサイズを小さくすると、特に高解像度の画像を含む PDF ファイルが多数ある場合に、記憶域スペースの使用を最適化するのに役立ちます。

パフォーマンスの向上: 小さい PDF ファイルの読み込みが速くなり、さまざまなデバイスでより速く開いて表示できるようになります。