---
title: コメントの追加
linktitle: コメントの追加
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書にコメントを追加する方法を学びます。
type: docs
weight: 10
url: /ja/net/working-with-comments/add-comments/
---

この包括的なチュートリアルでは、Aspose.Words for .NET を使用して Word 文書にコメントを追加する方法を学習します。プロセスを案内し、必要な C# コード スニペットを提供します。このガイドを終えると、ドキュメントにコメントを挿入し、その内容をカスタマイズできるようになります。

## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
- Aspose.Words for .NET ライブラリがシステムにインストールされています。

## ステップ 1: 新しいドキュメントと DocumentBuilder を作成する
まず、Document クラスを使用して新しいドキュメントを作成し、DocumentBuilder オブジェクトを初期化します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ 2: ドキュメントにコンテンツを追加する
次に、DocumentBuilder オブジェクトを使用して、必要なコンテンツをドキュメントに追加します。この例では、いくつかのテキストを追加します。

```csharp
builder.Write("Some text is added.");
```

## ステップ 3: コメントを作成してコンテンツを追加する
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

## ステップ 4: ドキュメントを保存する
コメントとその内容を追加した後、Document クラスの Save メソッドを使用してドキュメントをファイルに保存します。

```csharp
doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## Aspose.Words for .NET を使用してコメントを追加するためのソース コードの例
Aspose.Words for .NET を使用してコメントを追加するための完全なソース コードを次に示します。

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
おめでとう！ Aspose.Words for .NET を使用して Word 文書にコメントを追加する方法を学習しました。ステップバイステップのガイドに従い、提供されているソース コードを利用することで、ドキュメントにコメントを挿入し、その内容をカスタマイズできるようになります。

コメントは、コラボレーション、追加情報の提供、文書内でのメモの作成に役立ちます。特定の要件を満たすために、さまざまな著者名、イニシャル、コメントの内容を試してください。

### よくある質問

#### Q: Aspose.Words for .NET ドキュメントにコメントを追加するにはどうすればよいですか?

A: Aspose.Words for .NET ドキュメントにコメントを追加するには、チュートリアルで説明されている手順に従う必要があります。

#### Q: Aspose.Words for .NET でコメント テキストの書式を設定できますか?

A: はい、利用可能な書式設定プロパティを使用して、Aspose.Words for .NET でコメント テキストを書式設定できます。

#### Q: ドキュメント内にあるすべてのコメントを取得するにはどうすればよいですか?

 A: ドキュメント内に表示されているすべてのコメントを取得するには、`Document.Comments`財産。

#### Q: Aspose.Words for .NET で特定のコメントを削除できますか?

 A: はい、Aspose.Words for .NET の特定のコメントを削除するには、`Comment.Remove`方法。

#### Q: Aspose.Words for .NET で既存のコメントのテキストを変更するにはどうすればよいですか?

 A: Aspose.Words for .NET の既存のコメントのテキストを変更するには、`Comment.Text`対応するプロパティ`Comment`オブジェクトを変更し、必要に応じてテキストを変更します。