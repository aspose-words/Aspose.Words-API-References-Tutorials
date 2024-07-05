---
title: 見出しで Word 文書を分割する HTML
linktitle: 見出し別 HTML
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET の見出し HTML 機能による分割 Word 文書の C# ソース コードを説明するステップ バイ ステップ ガイド
type: docs
weight: 10
url: /ja/net/split-document/by-headings-html/
---
このチュートリアルでは、Aspose.Words for .NET の HTML 見出し機能を使用して Word 文書を小さな部分に分割する方法について説明します。以下の手順に従ってソース コードを理解し、見出しに基づいて個別の HTML 文書を生成します。

## ステップ1: ドキュメントの読み込み

まず、ドキュメントのディレクトリを指定して、ドキュメントを Document オブジェクトに読み込みます。手順は次のとおりです。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## ステップ2: HTML形式で文書を見出しで分割する

ここで、HTML 形式の見出しに基づいてドキュメントを小さな部分に分割するための保存オプションを設定します。方法は次のとおりです。

```csharp
HtmlSaveOptions options = new HtmlSaveOptions
{
//ドキュメントを小さな部分に分割します。この場合は、タイトルごとに分割します。
DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};

doc.Save(dataDir + "SplitDocument.ParTitresHtml.html", options);
```

### Aspose.Words for .NET を使用した見出し別 HTML のサンプル ソース コード

以下は、Aspose.Words for .NET の HTML 見出し機能の完全なソース コードです。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");

HtmlSaveOptions options = new HtmlSaveOptions
{
	//ドキュメントを小さな部分に分割します。この例では、見出しごとに分割します。
	DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};


doc.Save(dataDir + "SplitDocument.ByHeadingsHtml.html", options);
```

このコードを使用すると、Aspose.Words for .NET を使用して、見出しに基づいて Word 文書を小さな部分に分割できます。その後、各部分ごとに個別の HTML 文書を生成できます。

## 結論

このチュートリアルでは、Aspose.Words for .NETのHTML見出し機能を使用してWord文書を小さな部分に分割する方法を学びました。`DocumentSplitCriteria`として`HeadingParagraph`の中に`HtmlSaveOptions`元のドキュメントに存在する見出しに基づいて、個別の HTML ドキュメントを生成することができました。

ドキュメントを見出しで分割すると、特に複数のセクションがある大きなドキュメントで、コンテンツを整理および管理するのに役立ちます。Aspose.Words for .NET は、ドキュメントの分割を処理し、さまざまな形式で出力を生成するための信頼性が高く効率的なソリューションを提供します。

Aspose.Words for .NET が提供する追加の機能とオプションを自由に調べて、ドキュメント処理機能をさらに強化し、ワークフローを効率化してください。

### よくある質問

#### Aspose.Words for .NET を使用して、見出しに基づいて Word 文書を小さな部分に分割するにはどうすればよいですか?

 Word文書を見出しに基づいて分割するには、Aspose.Words for .NETのHTML見出し機能を使用します。提供されているソースコードに従って、`DocumentSplitCriteria`に`HeadingParagraph`の中に`HtmlSaveOptions`オブジェクト。これにより、ドキュメントは見出しごとに小さな部分に分割されます。

#### Word 文書をどのような形式に分割できますか?

提供されているソースコードは、Word文書をHTML形式で小さな部分に分割する方法を示しています。ただし、Aspose.Words for .NETは、DOCX、PDF、EPUBなど、さまざまな出力形式をサポートしています。コードを変更して、必要な出力形式を`HtmlSaveOptions`それに応じて異議を申し立てます。

#### ドキュメントを分割するための別の基準を選択できますか?

はい、要件に応じて、ドキュメントを分割するための異なる基準を選択できます。Aspose.Words for .NET には、次のようないくつかの基準オプションが用意されています。`HeadingParagraph`, `Page`, `Section`など。`DocumentSplitCriteria`の財産`HtmlSaveOptions`分割の適切な基準を選択するためのオブジェクト。

#### 分割された部分の出力 HTML をカスタマイズするにはどうすればよいですか?

 Aspose.Words for .NETでは、追加オプションを指定して分割部分の出力HTMLをカスタマイズできます。`HtmlSaveOptions`オブジェクト。CSS スタイル、画像、フォントなど、さまざまな側面を制御できます。HTML 出力のカスタマイズの詳細については、Aspose.Words のドキュメントを参照してください。

#### 複数の基準に基づいてドキュメントを分割できますか?

はい、条件オプションを組み合わせることで、複数の条件に基づいて文書を分割できます。たとえば、次のように設定することで、見出しとページの両方で文書を分割できます。`DocumentSplitCriteria`財産に`HeadingParagraph | Page`これにより、ドキュメントが各見出しと各ページで分割され、両方の基準に基づいて小さな部分が作成されます。