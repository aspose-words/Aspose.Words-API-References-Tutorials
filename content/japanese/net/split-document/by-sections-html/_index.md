---
title: Word 文書をセクションごとに分割する HTML
linktitle: セクション別HTML
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書をセクション Html に分割する方法を完全なコード例とともに学びます。
type: docs
weight: 10
url: /ja/net/split-document/by-sections-html/
---

この例では、Aspose.Words for .NET の By HTML Sections 機能を使用して、Word ドキュメントを HTML 形式の個別のセクションに分割する方法を示します。以下の手順に従ってソース コードを理解し、セクションごとに個別の HTML ドキュメントを生成します。

## ステップ 1: ドキュメントをロードする

まず、ドキュメントのディレクトリを指定し、ドキュメントを Document オブジェクトにロードします。その方法は次のとおりです。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## ステップ 2: ドキュメントを HTML 形式でセクションに分割する

次に、ドキュメントを HTML 形式のセクションに分割するための保存オプションを設定します。その方法は次のとおりです。

```csharp
HtmlSaveOptions options = new HtmlSaveOptions { DocumentSplitCriteria = DocumentSplitCriteria.SectionBreak };

doc.Save(dataDir + "SplitDocument.ParSectionsHtml.html", options);
```

### Aspose.Words for .NET を使用したセクション別 HTML のソース コード例

Aspose.Words for .NET の By HTML Sections 機能の完全なソース コードを次に示します。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");


HtmlSaveOptions options = new HtmlSaveOptions { DocumentSplitCriteria = DocumentSplitCriteria.SectionBreak };


doc.Save(dataDir + "SplitDocument.BySectionsHtml.html", options);
```

このコードを使用すると、Aspose.Words for .NET を使用して Word ドキュメントを HTML 形式の個別のセクションに分割できます。

これで、初期ドキュメントのセクションごとに個別の HTML ドキュメントを生成できるようになりました。

## 結論

このチュートリアルでは、Aspose.Words for .NET の By HTML Sections 機能を使用して、Word ドキュメントを HTML 形式の個別のセクションに分割する方法を学びました。提供されたソース コードに従うことで、元のドキュメントのセクションごとに個別の HTML ドキュメントを生成できます。

ドキュメントをセクションに分割すると、Web ページの作成、特定のコンテンツの抽出、情報の整理など、さまざまな目的に役立ちます。 Aspose.Words for .NET は、要件に応じて Word ドキュメントを操作およびカスタマイズできる強力な API を提供します。

Aspose.Words for .NET が提供する追加機能を自由に探索して、ドキュメント処理機能をさらに強化し、ワークフローを改善してください。

### よくある質問

#### HTML 出力形式をカスタマイズするにはどうすればよいですか?

Aspose.Words for .NET には、HTML 出力形式をカスタマイズするためのさまざまなオプションが用意されています。保存オプションを調整することで、HTML ドキュメントのスタイル、フォント設定、画像解像度、その他の多くの要素を変更できます。利用可能なオプションとその使用方法の詳細については、Aspose.Words for .NET のドキュメントを参照してください。

#### 別の基準に基づいてドキュメントを分割できますか?

はい。分割基準としてセクション区切りを使用するほかに、Aspose.Words for .NET では、文書の分割基準として段落区切り、見出しスタイル、特定のコンテンツなどのオプションを提供しています。要件に基づいて最適な基準を選択し、それに応じてコードを調整できます。

#### ドキュメントを HTML 以外の形式に分割することはできますか?

はい、Aspose.Words for .NET は、PDF、プレーン テキスト、画像などを含むさまざまな形式へのドキュメントの分割をサポートしています。保存オプションを変更して、目的の出力形式を生成できます。使用可能な形式と保存オプションでの指定方法の詳細については、Aspose.Words for .NET のドキュメントを参照してください。

#### 複数のドキュメントを同時に分割できますか?

はい、ドキュメントのコレクションを反復処理し、各ドキュメントの分割コードを個別に実行することで、分割プロセスを複数のドキュメントに同時に適用できます。これにより、複数のドキュメントを効率的に処理し、ドキュメントごとに個別のセクションを生成できます。

#### セクションを結合して 1 つのドキュメントに戻すにはどうすればよいですか?

Aspose.Words for .NET は、複数のドキュメントまたはセクションを 1 つのドキュメントに結合するメソッドも提供します。これらの結合機能を利用すると、別々に生成されたセクションを結合して、統一された文書を作成できます。ドキュメントまたはセクションを結合する方法の詳細については、Aspose.Words for .NET のドキュメントを参照してください。


