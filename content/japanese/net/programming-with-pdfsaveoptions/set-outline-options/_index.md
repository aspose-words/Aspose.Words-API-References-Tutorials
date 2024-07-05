---
title: PDF ドキュメントのアウトライン オプションを設定する
linktitle: PDF ドキュメントのアウトライン オプションを設定する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して PDF ドキュメントのアウトライン オプションを設定する手順ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-pdfsaveoptions/set-outline-options/
---

この記事では、Aspose.Words for .NET でアウトライン オプションをメタファイル サイズに設定する機能を使用する方法について、ステップ バイ ステップ ガイドを提供します。コードの各部分を詳しく説明します。このチュートリアルの最後には、ドキュメントでアウトライン オプションを設定し、対応するアウトライン オプションを使用して PDF を生成する方法を理解できるようになります。

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

## ステップ3: プランオプションでPDFとして保存オプションを設定する

生成されたPDFのアウトラインオプションを設定するには、`PdfSaveOptions`オブジェクト。見出しのアウトラインレベルの数を設定できます（`HeadingsOutlineLevels`）と拡張アウトラインレベルの数（`ExpandedOutlineLevels`）。

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;
```

## ステップ4: アウトラインオプションを使用してドキュメントをPDFとして保存する

最後に、以前に設定した保存オプションを使用して、ドキュメントを PDF 形式で保存できます。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
```

これで完了です。Aspose.Words for .NET を使用して、ドキュメントのアウトライン オプションを設定し、対応するアウトライン オプションを含む PDF を生成できました。

### Aspose.Words for .NET を使用してメタファイル サイズにプラン オプションを設定するサンプル ソース コード


```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
	saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
   
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して PDF ドキュメントのアウトライン オプションを設定する方法について説明しました。説明されている手順を使用すると、ドキュメントの見出しとアウトライン レベルを簡単に指定し、対応するアウトライン オプションを含む PDF ファイルを生成できます。Aspose.Words for .NET を使用して PDF ドキュメントの構造とナビゲーションを改善するアウトライン オプションの利点を活用してください。

### よくある質問

#### Q: PDF ドキュメントのアウトライン オプションとは何ですか?
A: PDF ドキュメントのアウトライン オプションは、ドキュメント コンテンツの階層構造を指します。これにより、インタラクティブな目次を作成し、ドキュメント内のナビゲーションを容易にすることができます。アウトライン オプションは、アウトラインに含めるタイトルとサブタイトルのレベル、および生成されたアウトラインに表示される詳細レベルを決定します。

#### Q: Aspose.Words for .NET を使用して PDF ドキュメントのアウトライン オプションを設定するにはどうすればよいですか?
A: Aspose.Words for .NET を使用して PDF ドキュメントのアウトライン オプションを設定するには、次の手順に従います。

ドキュメントが保存されているディレクトリパスを次のように設定します。`"YOUR DOCUMENT DIRECTORY"`ドキュメント ディレクトリの実際のパスを入力します。

 PDFに変換したい文書を読み込み、`Document`クラスを作成し、指定されたドキュメント ディレクトリ内のドキュメントへのパスを指定します。

 PDFとして保存オプションを設定するには、`PdfSaveOptions`クラスと使用`OutlineOptions`プロパティを使用してアウトラインオプションを設定します。アウトラインに含める見出しレベルの数を指定するには、`HeadingsOutlineLevels`プロパティと拡張アウトラインレベルの数`ExpandedOutlineLevels`財産。

ドキュメントをPDF形式で保存するには、`Save`方法の`Document`パスと保存オプションを指定するクラス。

#### Q: PDF ドキュメントのプラン オプションとは何ですか?
A: PDF ドキュメントのアウトライン オプションを使用すると、コンテンツの階層構造を作成できるため、ドキュメント内を移動したり、さまざまなセクションにアクセスしたりしやすくなります。これにより、ユーザーは目次またはアウトラインのエントリをクリックして、ドキュメントの特定の部分にすばやく移動できます。アウトライン オプションは、ドキュメント全体の構造の概要を提供することで、読みやすさも向上させます。
