---
title: コメントを追加
linktitle: コメントを追加
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書にコメントを追加する方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-comments/add-comments/
---

この包括的なチュートリアルでは、Aspose.Words for .NET を使用して Word 文書にコメントを追加する方法を学習します。プロセスをガイドし、必要な C# コード スニペットを提供します。このガイドの最後まで学習すると、文書にコメントを挿入し、その内容をカスタマイズできるようになります。

## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
- Aspose.Words for .NET ライブラリがシステムにインストールされています。

## ステップ1: 新しいドキュメントとDocumentBuilderを作成する
まず、Document クラスを使用して新しいドキュメントを作成し、DocumentBuilder オブジェクトを初期化します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ2: ドキュメントにコンテンツを追加する
次に、DocumentBuilder オブジェクトを使用して、ドキュメントに必要なコンテンツを追加します。この例では、テキストを追加します。

```csharp
builder.Write("Some text is added.");
```

## ステップ3: コメントを作成し、コンテンツを追加する
コメントを追加するには、Document オブジェクト、作成者名、作成者のイニシャル、および現在の日付を渡して、Comment クラスのインスタンスを作成します。

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
```

次に、現在の段落にコメントを追加します。

```csharp
builder.CurrentParagraph.AppendChild(comment);
```

段落やテキストなどのコンテンツをコメントに追加します。

```csharp
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));
```

## ステップ4: ドキュメントを保存する
コメントとその内容を追加したら、Document クラスの Save メソッドを使用してドキュメントをファイルに保存します。

```csharp
doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## Aspose.Words for .NET を使用してコメントを追加するためのサンプル ソース コード
Aspose.Words for .NET を使用してコメントを追加するための完全なソース コードは次のとおりです。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text is added.");

Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
builder.CurrentParagraph.AppendChild(comment);

comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## 結論
おめでとうございます。Aspose.Words for .NET を使用して Word 文書にコメントを追加する方法を学習しました。ステップバイステップのガイドに従い、提供されているソース コードを利用することで、文書にコメントを挿入し、その内容をカスタマイズできるようになりました。

コメントは、共同作業、追加情報の提供、またはドキュメント内でのメモの作成に役立ちます。特定の要件を満たすために、さまざまな作成者名、イニシャル、コメントの内容を試してみてください。

### よくある質問

#### Q: Aspose.Words for .NET ドキュメントにコメントを追加するにはどうすればよいですか?

A: Aspose.Words for .NET ドキュメントにコメントを追加するには、チュートリアルに記載されている手順に従う必要があります。

#### Q: Aspose.Words for .NET でコメント テキストをフォーマットできますか?

A: はい、Aspose.Words for .NET では、利用可能な書式設定プロパティを使用してコメント テキストを書式設定できます。

#### Q: ドキュメント内にあるすべてのコメントを取得するにはどうすればよいですか?

 A: ドキュメント内にあるすべてのコメントを取得するには、`Document.Comments`財産。

#### Q: Aspose.Words for .NET で特定のコメントを削除できますか?

 A: はい、Aspose.Words for .NETでは、`Comment.Remove`方法。

#### Q: Aspose.Words for .NET で既存のコメントのテキストを変更するにはどうすればよいですか?

 A: Aspose.Words for .NETで既存のコメントのテキストを変更するには、`Comment.Text`対応する`Comment`オブジェクトを作成し、必要に応じてテキストを変更します。