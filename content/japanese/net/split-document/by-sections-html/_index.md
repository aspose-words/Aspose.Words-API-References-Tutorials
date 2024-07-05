---
title: Word 文書をセクション別に分割する HTML
linktitle: セクション別 HTML
second_title: Aspose.Words ドキュメント処理 API
description: 完全なコード例を使用して、Aspose.Words for .NET を使用して Word 文書をセクション HTML に分割する方法を学習します。
type: docs
weight: 10
url: /ja/net/split-document/by-sections-html/
---

この例では、Aspose.Words for .NET の By HTML Sections 機能を使用して、Word 文書を HTML 形式で個別のセクションに分割する方法を説明します。以下の手順に従ってソース コードを理解し、セクションごとに個別の HTML 文書を生成します。

## ステップ1: ドキュメントの読み込み

まず、ドキュメントのディレクトリを指定して、ドキュメントを Document オブジェクトに読み込みます。手順は次のとおりです。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## ステップ2: HTML形式でドキュメントをセクションに分割する

次に、ドキュメントを HTML 形式でセクションに分割するための保存オプションを設定します。手順は次のとおりです。

```csharp
HtmlSaveOptions options = new HtmlSaveOptions { DocumentSplitCriteria = DocumentSplitCriteria.SectionBreak };

doc.Save(dataDir + "SplitDocument.ParSectionsHtml.html", options);
```

### Aspose.Words for .NET を使用したセクション別 HTML のサンプル ソース コード

以下は、Aspose.Words for .NET の HTML セクション別機能の完全なソース コードです。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");


HtmlSaveOptions options = new HtmlSaveOptions { DocumentSplitCriteria = DocumentSplitCriteria.SectionBreak };


doc.Save(dataDir + "SplitDocument.BySectionsHtml.html", options);
```

このコードを使用すると、Aspose.Words for .NET を使用して、Word 文書を HTML 形式の個別のセクションに分割できるようになります。

これで、初期ドキュメントの各セクションごとに個別の HTML ドキュメントを生成できるようになりました。

## 結論

このチュートリアルでは、Aspose.Words for .NET の By HTML Sections 機能を使用して、Word 文書を HTML 形式で個別のセクションに分割する方法を学習しました。提供されているソース コードに従うことで、元の文書の各セクションに対して個別の HTML 文書を生成できます。

ドキュメントをセクションに分割すると、Web ページの作成、特定のコンテンツの抽出、情報の整理など、さまざまな目的に役立ちます。Aspose.Words for .NET は、要件に応じて Word ドキュメントを操作およびカスタマイズできる強力な API を提供します。

Aspose.Words for .NET が提供する追加機能を自由に探索して、ドキュメント処理機能をさらに強化し、ワークフローを改善してください。

### よくある質問

#### HTML 出力形式をカスタマイズするにはどうすればよいですか?

Aspose.Words for .NET には、HTML 出力形式をカスタマイズするためのさまざまなオプションが用意されています。保存オプションを調整することで、HTML ドキュメントのスタイル、フォント設定、画像解像度など、さまざまな側面を変更できます。使用可能なオプションとその使用方法の詳細については、Aspose.Words for .NET のドキュメントを参照してください。

#### 別の基準に基づいてドキュメントを分割できますか?

はい、セクション区切りを分割基準として使用することに加え、Aspose.Words for .NET では、段落区切り、見出しスタイル、特定のコンテンツなど、ドキュメントを分割するための基準となる他のオプションも提供しています。要件に基づいて最も適切な基準を選択し、それに応じてコードを調整できます。

#### ドキュメントを HTML 以外の形式に分割することは可能ですか?

はい、Aspose.Words for .NET は、PDF、プレーン テキスト、画像など、さまざまな形式へのドキュメントの分割をサポートしています。保存オプションを変更して、必要な出力形式を生成できます。使用可能な形式と、保存オプションでそれらを指定する方法の詳細については、Aspose.Words for .NET のドキュメントを参照してください。

#### 複数のドキュメントを同時に分割できますか?

はい、ドキュメントのコレクションを反復処理し、各ドキュメントの分割コードを個別に実行することで、複数のドキュメントに同時に分割プロセスを適用できます。これにより、複数のドキュメントを効率的に処理し、ドキュメントごとに個別のセクションを生成できます。

#### セクションを 1 つのドキュメントに再び結合するにはどうすればよいですか?

Aspose.Words for .NET には、複数のドキュメントまたはセクションを 1 つのドキュメントに結合する方法も用意されています。これらの結合機能を利用すると、別々に生成されたセクションを結合し、統合されたドキュメントを作成できます。ドキュメントまたはセクションを結合する方法の詳細については、Aspose.Words for .NET のドキュメントを参照してください。


