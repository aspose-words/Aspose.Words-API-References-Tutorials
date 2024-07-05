---
title: 追加 削除 コメント 返信
linktitle: 追加 削除 コメント 返信
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書にコメントの返信を追加および削除する方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-comments/add-remove-comment-reply/
---

この包括的なチュートリアルでは、Aspose.Words for .NET を使用して Word 文書にコメントの返信を追加および削除する方法を学習します。プロセスをガイドし、必要な C# コード スニペットを提供します。このガイドの最後までに、コメントの返信を管理し、要件に応じてカスタマイズできるようになります。

## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
- Aspose.Words for .NET ライブラリがシステムにインストールされています。

## ステップ1: ドキュメントを読み込む
まず、Document クラスを使用してコメントを含むドキュメントを読み込みます。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");
```

## ステップ2: コメントにアクセスして返信を管理する
次に、NodeType.Comment パラメータを指定した GetChild メソッドを使用して、ドキュメントからコメントにアクセスします。

```csharp
Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);
```

コメントから返信を削除するには、RemoveReply メソッドを使用して、必要な返信インデックスを指定します。

```csharp
comment.RemoveReply(comment.Replies[0]);
```

コメントに新しい返信を追加するには、AddReply メソッドを使用して、作成者名、作成者のイニシャル、日時、返信テキストを指定します。

```csharp
comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");
```

## ステップ3: ドキュメントを保存する
コメントの返信を追加または削除した後、Document クラスの Save メソッドを使用してドキュメントをファイルに保存します。

```csharp
doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

### Aspose.Words for .NET を使用してコメント返信を追加および削除するためのサンプル ソース コード
Aspose.Words for .NET を使用してコメントの返信を追加および削除するための完全なソース コードは次のとおりです。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);

comment.RemoveReply(comment.Replies[0]);

comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");

doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

## 結論
おめでとうございます! Aspose.Words for .NET を使用して Word 文書にコメントの返信を追加および削除する方法を学習しました。ステップバイステップのガイドに従い、提供されているソース コードを利用することで、コメントの返信を管理し、必要に応じてカスタマイズできるようになりました。

コメント返信により、ドキュメント内での共同ディスカッションやフィードバックが可能になります。さまざまな返信作成者、イニシャル、日付、テキストを試して、ドキュメント内での共同作業とコミュニケーションを強化します。

### よくある質問

#### Q: Aspose.Words for .NET でコメントを追加するにはどうすればよいですか?

 A: Aspose.Words for .NETでコメントを追加するには、`Comment.AddComment`コメントのテキストと、ドキュメント内でコメントを追加する場所を指定するメソッド。

#### Q: Aspose.Words for .NET でコメントを削除するにはどうすればよいですか?

A: Aspose.Words for .NETでコメントを削除するには、`Comment.Remove`指定方法`Comment`削除したいオブジェクト。

#### Q: Aspose.Words for .NET でコメントに返信できますか?

 A: はい、Aspose.Words for .NETでは、`Comment.AddReply`返信テキストと、それをドキュメント内に追加する場所を指定する方法。

#### Q: Aspose.Words for .NET で既存のコメントにアクセスするにはどうすればいいですか?

 A: Aspose.Words for .NETの既存のコメントにアクセスするには、`CommentCollection`の財産`Document`オブジェクト。これにより、ドキュメント内に存在するすべてのコメントを参照できるようになります。

#### Q: Aspose.Words for .NET でコメント テキストを編集できますか?

 A: はい、Aspose.Words for .NETでは、コメントのテキストを編集することができます。`Comment.Text`対応する`Comment`オブジェクトを作成し、必要に応じてテキストを変更します。