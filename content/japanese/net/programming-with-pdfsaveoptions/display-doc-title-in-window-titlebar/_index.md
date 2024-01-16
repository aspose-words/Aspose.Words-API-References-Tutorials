---
title: ウィンドウのタイトルバーにドキュメントのタイトルを表示
linktitle: ウィンドウのタイトルバーにドキュメントのタイトルを表示
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して PDF に変換するときに、ウィンドウのタイトル バーにドキュメントのタイトルを表示する方法を説明します。
type: docs
weight: 10
url: /ja/net/programming-with-pdfsaveoptions/display-doc-title-in-window-titlebar/
---

このチュートリアルでは、Aspose.Words for .NET を使用してウィンドウのタイトル バーにドキュメント タイトルを表示する手順を説明します。この機能を使用すると、生成された PDF ドキュメントを開いたときにウィンドウのタイトル バーにドキュメントのタイトルを表示できます。以下の手順に従います。

## ステップ 1: ドキュメントをロードする

まず、PDF に変換するドキュメントをアップロードします。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Rendering.docx");
```

必ずドキュメントへの正しいパスを指定してください。

## ステップ 2: PDF 保存オプションを構成する

PdfSaveOptions クラスのインスタンスを作成し、ウィンドウのタイトル バーにドキュメント タイトルを表示できるようにします。

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions { DisplayDocTitle = true };
```

このオプションは、PDF への変換時にウィンドウのタイトル バーにドキュメント タイトルを表示できるようにします。

## ステップ 3: ドキュメントを PDF に変換する

使用`Save`変換オプションを指定してドキュメントを PDF に変換するメソッド:

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisplayDocTitleInWindowTitlebar.pdf", saveOptions);
```

変換された PDF を保存するための正しいパスを指定してください。

### Aspose.Words for .NET を使用してウィンドウ タイトルバーにドキュメント タイトルを表示するソース コードの例

Aspose.Words for .NET を使用して PDF ドキュメントのウィンドウ タイトル バーにドキュメント タイトルを表示する完全なソース コードを次に示します。

```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions { DisplayDocTitle = true };

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.DisplayDocTitleInWindowTitlebar.pdf", saveOptions);
        
```
以下の手順に従うことで、Aspose.Words for .NET で PDF に変換するときに、ウィンドウのタイトル バーにドキュメントのタイトルを簡単に表示できます。

### よくある質問

#### Q: Aspose.Words for .NET の「ウィンドウ タイトル バーにドキュメント タイトルを表示」機能とは何ですか?
Aspose.Words for .NET の「ウィンドウ タイトル バーにドキュメント タイトルを表示」機能を使用すると、生成された PDF ドキュメントを開いたときにウィンドウ タイトル バーにドキュメント タイトルを表示できます。これにより、閲覧環境での PDF ドキュメントの識別と区別が容易になります。

#### Q: この機能を Aspose.Words for .NET で使用するにはどうすればよいですか?
Aspose.Words for .NET でこの機能を使用するには、次の手順に従います。

を使用してドキュメントをロードします。`Document`メソッドを指定し、PDF に変換するファイルのパスを指定します。

のインスタンスを作成して PDF 保存オプションを構成します。`PdfSaveOptions`クラスと設定`DisplayDocTitle`財産を`true`。これにより、PDF に変換するときにウィンドウのタイトル バーにドキュメントのタイトルを表示できるようになります。

使用`Save`変換オプションを指定してドキュメントを PDF に変換するメソッド。

#### Q: この機能はドキュメント自体の内容を変更しますか?
いいえ、この機能はドキュメント自体の内容を変更するものではありません。 PDF ドキュメントとして開いたときのウィンドウ タイトル バーのドキュメント タイトルの表示にのみ影響します。文書の内容は変更されません。

#### Q: ウィンドウのタイトル バーに表示されるドキュメントのタイトルをカスタマイズすることはできますか?
はい、ウィンドウのタイトル バーに表示されるドキュメントのタイトルをカスタマイズできます。`Document.Title` PDF に変換する前にドキュメントのプロパティを変更します。文字列を使用して任意のタイトルを設定できます。電話をかける前に必ずタイトルを設定してください。`Save` PDFに変換する方法です。

#### Q: Aspose.Words はドキュメント変換に関して他にどのような出力形式をサポートしていますか?
Aspose.Words for .NET は、PDF、XPS、HTML、EPUB、MOBI、画像 (JPEG、PNG、BMP、TIFF、GIF) など、ドキュメント変換用の多くの出力形式をサポートしています。まだ他にも。特定のニーズに応じて、適切な出力形式を選択できます。