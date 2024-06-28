---
title: アンカーコメント
linktitle: アンカーコメント
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、コメント返信を Word 文書内の特定のテキストに固定する方法を学びます。
type: docs
weight: 10
url: /ja/net/working-with-comments/anchor-comment/
---

この包括的なチュートリアルでは、Aspose.Words for .NET を使用して、コメント返信を Word 文書内の特定のテキストに固定する方法を学習します。プロセスを案内し、必要な C# コード スニペットを提供します。このガイドを終えると、コメントをドキュメント内の特定のテキストに関連付けることができるようになります。

## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
- Aspose.Words for .NET ライブラリがシステムにインストールされています。

## ステップ 1: 新しいドキュメントを作成してテキストを追加する
まず、Document クラスを使用して新しいドキュメントを作成し、必要なテキストを追加します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);
```

## ステップ 2: コメントを作成し、コメント範囲を追加する
次に、コメントを作成し、CommentRangeStart オブジェクトと CommentRangeEnd オブジェクトを使用して特定のテキストに関連付けます。

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);
```

## ステップ 3: ドキュメントを保存する
コメントを特定のテキストに固定した後、Document クラスの Save メソッドを使用してドキュメントをファイルに保存します。

```csharp
doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");
```

### Aspose.Words for .NET を使用したアンカー コメント返信のソース コード例
Aspose.Words for .NET を使用してコメント返信をアンカーするための完全なソース コードを次に示します。

```csharp
//ドキュメントのインスタンスを作成します。
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document();

// 3 つの Run オブジェクトを作成します。
//最初の 2 つはテキストを実行し、3 番目はコメントを実行します。

Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);

Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

//各 Run オブジェクトには、関連付けられた CommentRangeStart オブジェクトと CommentRangeEnd オブジェクトがあります。

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);

doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");	
```

### よくある質問

#### Q: Aspose.Words for .NET のコメント アンカーとは何ですか?

A: Aspose.Words for .NET では、コメント アンカーは、コメントをドキュメント内の特定の場所に接続するマーカーです。

#### Q: Aspose.Words for .NET ドキュメントにコメント アンカーを追加するにはどうすればよいですか?

A: Aspose.Words for .NET ドキュメントにコメント アンカーを追加するには、チュートリアルで説明されている手順に従います。

#### Q: Aspose.Words for .NET の既存のコメント アンカーにアクセスするにはどうすればよいですか?

 A: Aspose.Words for .NET の既存のコメント アンカーには、`Comment.Anchor`財産。

#### Q: Aspose.Words for .NET でコメント アンカーを指定できますか?

 A: はい、Aspose.Words for .NET のコメント アンカーを削除するには、`Comment.Remove`方法。

#### Q: Aspose.Words for .NET でコメント アンカーにリンクされているコメントのテキストを編集するにはどうすればよいですか?

A: Aspose.Words for .NET のコメント アンカーにバインドされたコメントのテキストを変更するには、`Comment.Text`対応するプロパティ`Comment`オブジェクトを変更し、必要に応じてテキストを変更します。

