---
title: PDF ドキュメントのアウトライン オプションを設定する
linktitle: PDF ドキュメントのアウトライン オプションを設定する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して PDF ドキュメントのアウトライン オプションを設定するためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-pdfsaveoptions/set-outline-options/
---

この記事では、Aspose.Words for .NET でアウトライン オプションをメタファイル サイズに設定する機能を使用する方法について、段階的なガイドを提供します。コードの各部分について詳しく説明します。このチュートリアルを終えると、ドキュメントにアウトライン オプションを設定し、対応するアウトライン オプションを使用して PDF を生成する方法を理解できるようになります。

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

## ステップ 3: プラン オプションを使用して PDF として保存オプションを構成する

生成された PDF でアウトライン オプションを設定するには、`PdfSaveOptions`物体。見出しのアウトライン レベルの数を設定できます (`HeadingsOutlineLevels`) と展開されたアウトライン レベルの数 (`ExpandedOutlineLevels`）。

```csharp
PdfSaveOptions saveOptions = new PdfSaveOptions();
saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;
```

## ステップ 4: アウトライン オプションを使用してドキュメントを PDF として保存する

最後に、前に設定した保存オプションを使用してドキュメントを PDF 形式で保存できます。

```csharp
doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
```

それだけです ！ Aspose.Words for .NET を使用して、文書にアウトライン オプションを設定し、対応するアウトライン オプションを含む PDF を生成しました。

### Aspose.Words for .NET でプラン オプションをメタファイル サイズに設定するソース コードの例


```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Rendering.docx");

	PdfSaveOptions saveOptions = new PdfSaveOptions();
	saveOptions.OutlineOptions.HeadingsOutlineLevels = 3;
	saveOptions.OutlineOptions.ExpandedOutlineLevels = 1;

	doc.Save(dataDir + "WorkingWithPdfSaveOptions.SetOutlineOptions.pdf", saveOptions);
   
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して PDF ドキュメントにアウトライン オプションを設定する方法を説明しました。ここで説明する手順を使用すると、文書内の見出しとアウトラインのレベルを簡単に指定し、対応するアウトライン オプションを備えた PDF ファイルを生成できます。 Aspose.Words for .NET を使用して PDF ドキュメントの構造とナビゲーションを改善するアウトライン オプションの利点をお楽しみください。

### よくある質問

#### Q: PDF ドキュメントのアウトライン オプションとは何ですか?
A: PDF ドキュメントのアウトライン オプションは、ドキュメント コンテンツの階層構造を指します。これにより、対話型の目次を作成でき、ドキュメント内のナビゲーションが容易になります。アウトライン オプションは、アウトラインに含めるタイトルとサブタイトルのレベル、および生成されたアウトラインに表示する詳細レベルを決定します。

#### Q: Aspose.Words for .NET を使用して PDF ドキュメントにアウトライン オプションを設定するにはどうすればよいですか?
A: Aspose.Words for .NET を使用して PDF ドキュメントのアウトライン オプションを設定するには、次の手順に従います。

を置き換えて、ドキュメントが配置されているディレクトリ パスを設定します。`"YOUR DOCUMENT DIRECTORY"`ドキュメントディレクトリの実際のパスに置き換えます。

 PDF に変換したいドキュメントをロードします。`Document`クラスを作成し、指定されたドキュメント ディレクトリ内のドキュメントへのパスを指定します。

のインスタンスを作成して、PDF として保存オプションを構成します。`PdfSaveOptions`クラスとそれを使用する`OutlineOptions`プロパティを使用してアウトライン オプションを設定します。アウトラインに含める見出しレベルの数を指定するには、`HeadingsOutlineLevels`プロパティと展開されたアウトライン レベルの数を使用して、`ExpandedOutlineLevels`財産。

ドキュメントを PDF 形式で保存するには、`Save`の方法`Document`パスと保存オプションを指定するクラス。

#### Q: PDF ドキュメントのプラン オプションとは何ですか?
A: PDF ドキュメントのアウトライン オプションを使用すると、コンテンツの階層構造を作成できるため、ドキュメント内の移動やさまざまなセクションへのアクセスが容易になります。これにより、ユーザーは目次またはアウトライン内のエントリをクリックして、ドキュメントの特定の部分にすばやくジャンプできます。また、アウトライン オプションを使用すると、文書全体の構造の概要が提供されるため、読書体験が向上します。
