---
title: コメントの追加 削除 返信
linktitle: コメントの追加 削除 返信
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書のコメント返信を追加および削除する方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-comments/add-remove-comment-reply/
---

この包括的なチュートリアルでは、Aspose.Words for .NET を使用して Word 文書にコメント返信を追加および削除する方法を学習します。プロセスを案内し、必要な C# コード スニペットを提供します。このガイドを終えると、コメントの返信を管理し、要件に応じてカスタマイズできるようになります。

## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
- Aspose.Words for .NET ライブラリがシステムにインストールされています。

## ステップ 1: ドキュメントをロードする
まず、Document クラスを使用してコメントを含むドキュメントを読み込みます。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");
```

## ステップ 2: コメントにアクセスして返信を管理する
次に、NodeType.Comment パラメーターを指定した GetChild メソッドを使用して、ドキュメントからコメントにアクセスします。

```csharp
Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);
```

コメントから返信を削除するには、RemoveReply メソッドを使用し、必要な返信インデックスを指定します。

```csharp
comment.RemoveReply(comment.Replies[0]);
```

コメントに新しい返信を追加するには、AddReply メソッドを使用して、作成者名、作成者のイニシャル、日付と時刻、返信テキストを指定します。

```csharp
comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");
```

## ステップ 3: ドキュメントを保存する
コメント返信を追加または削除した後、Document クラスの Save メソッドを使用してドキュメントをファイルに保存します。

```csharp
doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

### Aspose.Words for .NET を使用したコメント返信の追加および削除のソース コード例
Aspose.Words for .NET を使用してコメント返信を追加および削除するための完全なソース コードを次に示します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

Comment comment = (Comment)doc.GetChild(NodeType.Comment, 0, true);

comment.RemoveReply(comment.Replies[0]);

comment.AddReply("John Doe", "JD", new DateTime(2017, 9, 25, 12, 15, 0), "New reply");

doc.Save(dataDir + "WorkingWithComments.AddRemoveCommentReply.docx");
```

## 結論
おめでとう！ Aspose.Words for .NET を使用して Word 文書にコメント返信を追加および削除する方法を学習しました。ステップバイステップのガイドに従い、提供されているソース コードを利用することで、コメントの返信を管理し、要件に応じてカスタマイズできるようになります。

コメント返信により、ドキュメント内で共同でディスカッションやフィードバックを行うことができます。文書内でのコラボレーションとコミュニケーションを強化するには、さまざまな返信著者、イニシャル、日付、テキストを試してください。

### よくある質問

#### Q: Aspose.Words for .NET にコメントを追加するにはどうすればよいですか?

 A: Aspose.Words for .NET にコメントを追加するには、`Comment.AddComment`コメントのテキストとそれをドキュメント内で追加する場所を指定するメソッド。

#### Q: Aspose.Words for .NET でコメントを削除するにはどうすればよいですか?

A: Aspose.Words for .NET でコメントを削除するには、`Comment.Remove`を指定するメソッド`Comment`削除したいオブジェクト。

#### Q: Aspose.Words for .NET のコメントに返信できますか?

 A: はい、Aspose.Words for .NET のコメントに返信するには、`Comment.AddReply`メソッドで返信テキストとそれを文書内のどこに追加するかを指定します。

#### Q: Aspose.Words for .NET の既存のコメントにアクセスするにはどうすればよいですか?

 A: Aspose.Words for .NET の既存のコメントには、`CommentCollection`の財産`Document`物体。これにより、ドキュメント内に存在するすべてのコメントを参照できるようになります。

#### Q: Aspose.Words for .NET でコメント テキストを編集できますか?

 A: はい、Aspose.Words for .NET でコメントのテキストを編集するには、`Comment.Text`対応するプロパティ`Comment`オブジェクトを編集し、必要に応じてテキストを変更します。