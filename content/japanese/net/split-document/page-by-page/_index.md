---
title: Word文書をページごとに分割する
linktitle: Word文書をページごとに分割する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書を個々のページに分割する方法を学びます。この強力な API により、ドキュメントの分割プロセスが簡素化され、効率的かつ便利になります。
type: docs
weight: 10
url: /ja/net/split-document/page-by-page/
---

このチュートリアルでは、Aspose.Words for .NET の文書処理機能を使用して Word 文書を個々のページに分割する方法を説明します。以下の手順に従ってソース コードを理解し、ページごとに個別のドキュメントを取得します。

## ステップ 1: ドキュメントをロードする

まず、ドキュメントのディレクトリを指定し、ドキュメントを Document オブジェクトにロードします。その方法は次のとおりです。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Large document.docx");
```

## ステップ 2: ドキュメントをページごとに分割する

ここで、ドキュメントの各ページを繰り返し処理し、ドキュメントを個々のページに分割します。その方法は次のとおりです。

```csharp
int pageCount = doc. PageCount;

for (int page = 0; page < pageCount; page++)
{
//各ページを個別の文書として保存します。
Document extractedPage = doc.ExtractPages(page, 1);
extractedPage.Save(dataDir + $"SplitDocument.PageParPage_{page + 1}.docx");
}
```

### Aspose.Words for .NET を使用したページごとのソース コードの例

Aspose.Words for .NET のページごとの機能の完全なソース コードは次のとおりです。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Big document.docx");

int pageCount = doc.PageCount;

for (int page = 0; page < pageCount; page++)
{
	//各ページを個別の文書として保存します。
	Document extractedPage = doc.ExtractPages(page, 1);
	extractedPage.Save(dataDir + $"SplitDocument.PageByPage_{page + 1}.docx");
}


```

このコードを使用すると、Aspose.Words for .NET を使用して Word ドキュメントを個々のページに分割できます。必要に応じて、別々のドキュメントを結合することもできます。

## 結論

おめでとう！ Aspose.Words for .NET のページごとの機能を使用して、Word 文書を個々のページに分割する方法を学習しました。提供されたソース コードに従って、ドキュメントの各ページを抽出し、個別のドキュメントとして保存できます。

ドキュメントをページごとに分割することは、特定のページを操作する必要がある場合や、コンテンツをきめ細かく配布する必要がある場合に便利です。 Aspose.Words for .NET は、ドキュメントの分割プロセスを簡素化し、効率的かつ便利にする強力な API を提供します。

Aspose.Words for .NET が提供する他の機能を自由に探索して、ドキュメント処理機能を強化し、ワークフローを合理化してください。

### よくある質問

#### Aspose.Words for .NET を使用してドキュメントを複数のページに分割するにはどうすればよいですか?

ドキュメントを複数のページに分割するには、`ExtractPages` Aspose.Words API のメソッドを使用してページ範囲を取得します。抽出開始ページとページ数を指定することで、ページごとに文書を作成できます。

#### ドキュメントをページごとに分割するときに出力形式をカスタマイズできますか?

はい、Aspose.Words for .NET は、ドキュメントをページごとに分割する際のさまざまな出力形式をサポートしています。要件に応じて、各ページを DOCX、PDF、HTML などの形式で個別のドキュメントとして保存できます。

#### ドキュメントを特定のページ範囲で分割できますか?

絶対に！ Aspose.Words for .NET を使用すると、特定のページ範囲でドキュメントを分割できます。開始ページと抽出するページ数を調整することで、ドキュメントを分割するページ範囲を正確に定義できます。

#### 分割された文書を結合して 1 つの文書に戻すことはできますか?

はい、Aspose.Words for .NET が提供する結合機能を使用して、分割されたドキュメントを単一のドキュメントに結合し直すことができます。必要に応じて、別々のドキュメントを結合することで、元のドキュメントを再作成したり、異なる構造の新しいドキュメントを作成したりできます。