---
title: Word文書を見出しHTMLごとに分割する
linktitle: 見出しHTML別
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET の見出し HTML 機能による分割 Word ドキュメントの C# ソース コードを説明するステップバイステップ ガイド
type: docs
weight: 10
url: /ja/net/split-document/by-headings-html/
---
このチュートリアルでは、Aspose.Words for .NET の HTML 見出し機能を使用して Word 文書を小さな部分に分割する方法を説明します。以下の手順に従ってソース コードを理解し、見出しに基づいて個別の HTML ドキュメントを生成します。

## ステップ 1: ドキュメントをロードする

まず、ドキュメントのディレクトリを指定し、ドキュメントを Document オブジェクトにロードします。その方法は次のとおりです。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## ステップ 2: HTML 形式で文書を見出しごとに分割する

次に、HTML 形式の見出しに基づいてドキュメントを小さな部分に分割するための保存オプションを設定します。その方法は次のとおりです。

```csharp
HtmlSaveOptions options = new HtmlSaveOptions
{
//ドキュメントを小さな部分に分割します。この場合はタイトルごとに分けます。
DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};

doc.Save(dataDir + "SplitDocument.ParTitresHtml.html", options);
```

### Aspose.Words for .NET を使用した By Headings HTML のソース コード例

Aspose.Words for .NET の By HTML Heading 機能の完全なソース コードを次に示します。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");

HtmlSaveOptions options = new HtmlSaveOptions
{
	//文書を小さな部分に分割します。この例では見出しごとに分割します。
	DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};


doc.Save(dataDir + "SplitDocument.ByHeadingsHtml.html", options);
```

このコードを使用すると、Aspose.Words for .NET を使用して、見出しに基づいて Word 文書を小さな部分に分割できます。その後、パーツごとに個別の HTML ドキュメントを生成できます。

## 結論

このチュートリアルでは、Aspose.Words for .NET の HTML 見出し機能を使用して Word 文書を小さな部分に分割する方法を学びました。を指定することで、`DocumentSplitCriteria`として`HeadingParagraph`の中に`HtmlSaveOptions`、元の文書に存在する見出しに基づいて個別の HTML 文書を生成することができました。

文書を見出しごとに分割すると、特に複数のセクションを持つ大きな文書の場合、コンテンツの整理と管理に役立ちます。 Aspose.Words for .NET は、ドキュメントの分割を処理し、さまざまな形式で出力を生成するための信頼性が高く効率的なソリューションを提供します。

Aspose.Words for .NET が提供する追加機能やオプションを自由に探索して、ドキュメント処理機能をさらに強化し、ワークフローを合理化してください。

### よくある質問

#### Aspose.Words for .NET を使用して Word 文書を見出しに基づいて小さな部分に分割するにはどうすればよいですか?

 Word 文書を見出しに基づいて分割するには、Aspose.Words for .NET の HTML 見出し機能を使用できます。提供されたソースコードに従って、`DocumentSplitCriteria`に`HeadingParagraph`の中に`HtmlSaveOptions`物体。これにより、文書が見出しごとに小さな部分に分割されます。

#### Word 文書をどの形式に分割できますか?

提供されているソース コードは、Word ドキュメントを HTML 形式で小さな部分に分割する方法を示しています。ただし、Aspose.Words for .NET は、DOCX、PDF、EPUB などのさまざまな出力形式をサポートしています。コードを変更して、目的の出力形式を指定できます。`HtmlSaveOptions`それに応じて反対します。

#### ドキュメントを分割するために別の基準を選択できますか?

はい、要件に基づいてドキュメントを分割するための別の基準を選択できます。 Aspose.Words for .NET には、次のようないくつかの基準オプションが用意されています。`HeadingParagraph`, `Page`, `Section` 、 もっと。を変更します。`DocumentSplitCriteria`のプロパティ`HtmlSaveOptions`オブジェクトを使用して、適切な分割基準を選択します。

#### 分割された部分の出力 HTML をカスタマイズするにはどうすればよいですか?

 Aspose.Words for .NET を使用すると、追加のオプションを指定することで分割部分の出力 HTML をカスタマイズできます。`HtmlSaveOptions`物体。 CSS スタイル、画像、フォントなどのさまざまな要素を制御できます。 HTML 出力のカスタマイズの詳細については、Aspose.Words のドキュメントを参照してください。

#### 複数の基準に基づいてドキュメントを分割できますか?

はい、基準オプションを適宜組み合わせることで、複数の基準に基づいてドキュメントを分割できます。たとえば、ドキュメントを見出しとページの両方で分割するには、`DocumentSplitCriteria`財産を`HeadingParagraph | Page`。これにより、ドキュメントが各見出しと各ページで分割され、両方の基準に基づいて小さな部分が作成されます。