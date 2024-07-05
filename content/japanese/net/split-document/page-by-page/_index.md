---
title: Word 文書をページごとに分割する
linktitle: Word 文書をページごとに分割する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書を個別のページに分割する方法を学びます。この強力な API により、文書の分割プロセスが簡素化され、効率的かつ便利になります。
type: docs
weight: 10
url: /ja/net/split-document/page-by-page/
---

このチュートリアルでは、Aspose.Words for .NET のドキュメント処理機能を使用して Word ドキュメントを個別のページに分割する方法について説明します。ソース コードを理解し、ページごとに個別のドキュメントを取得するには、以下の手順に従ってください。

## ステップ1: ドキュメントの読み込み

まず、ドキュメントのディレクトリを指定して、ドキュメントを Document オブジェクトに読み込みます。手順は次のとおりです。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Large document.docx");
```

## ステップ2: ページごとにドキュメントを分割する

次に、ドキュメントの各ページを反復処理して、ドキュメントを個別のページに分割します。方法は次のとおりです。

```csharp
int pageCount = doc. PageCount;

for (int page = 0; page < pageCount; page++)
{
//各ページを個別のドキュメントとして保存します。
Document extractedPage = doc.ExtractPages(page, 1);
extractedPage.Save(dataDir + $"SplitDocument.PageParPage_{page + 1}.docx");
}
```

### Aspose.Words for .NET を使用した Page By Page のサンプル ソース コード

以下は、Aspose.Words for .NET の Page by Page 機能の完全なソース コードです。

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Big document.docx");

int pageCount = doc.PageCount;

for (int page = 0; page < pageCount; page++)
{
	//各ページを個別のドキュメントとして保存します。
	Document extractedPage = doc.ExtractPages(page, 1);
	extractedPage.Save(dataDir + $"SplitDocument.PageByPage_{page + 1}.docx");
}


```

このコードを使用すると、Aspose.Words for .NET を使用して Word 文書を個別のページに分割できます。必要に応じて、個別の文書を結合することもできます。

## 結論

おめでとうございます! Aspose.Words for .NET のページごとの機能を使用して、Word 文書を個別のページに分割する方法を学習しました。提供されているソース コードに従うことで、文書の各ページを抽出し、個別の文書として保存できます。

特定のページを操作したり、コンテンツを細かく配布したりする必要がある場合は、ドキュメントをページごとに分割すると便利です。Aspose.Words for .NET は、ドキュメントの分割プロセスを簡素化し、効率的で便利なものにする強力な API を提供します。

ドキュメント処理機能を強化し、ワークフローを効率化するために、Aspose.Words for .NET が提供するその他の機能を自由に探索してください。

### よくある質問

#### Aspose.Words for .NET を使用してドキュメントを複数のページに分割するにはどうすればよいですか?

文書を複数のページに分割するには、`ExtractPages` Aspose.Words API のメソッドを使用してページ範囲を取得します。開始ページと抽出するページ数を指定することで、ページごとに個別のドキュメントを作成できます。

#### ドキュメントをページごとに分割するときに出力形式をカスタマイズできますか?

はい、Aspose.Words for .NET は、ドキュメントをページごとに分割する際にさまざまな出力形式をサポートしています。要件に応じて、各ページを DOCX、PDF、HTML などの形式で個別のドキュメントとして保存できます。

#### ドキュメントを特定のページ範囲で分割できますか?

もちろんです! Aspose.Words for .NET では、特定のページ範囲でドキュメントを分割できます。開始ページと抽出するページ数を調整することで、ドキュメントを分割するページ範囲を正確に定義できます。

#### 分割されたドキュメントを 1 つのドキュメントに戻すことは可能ですか?

はい、Aspose.Words for .NET が提供するマージ機能を使用して、分割されたドキュメントを 1 つのドキュメントにマージすることができます。個別のドキュメントを結合することで、必要に応じて元のドキュメントを再作成したり、異なる構造の新しいドキュメントを作成したりできます。