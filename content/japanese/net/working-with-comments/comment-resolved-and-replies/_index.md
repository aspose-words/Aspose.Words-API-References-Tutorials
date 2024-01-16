---
title: コメントの解決と返信
linktitle: コメントの解決と返信
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内のコメントとその返信を解決する方法を学びます。
type: docs
weight: 10
url: /ja/net/working-with-comments/comment-resolved-and-replies/
---

この包括的なチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内のコメントとその返信を解決する方法を学習します。プロセスを案内し、必要な C# コード スニペットを提供します。このガイドを終えると、コメントの解決を管理し、コメントとその返信のステータスを更新できるようになります。

## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
- Aspose.Words for .NET ライブラリがシステムにインストールされています。

## ステップ 1: ドキュメントをロードしてコメントにアクセスする
まず、Document クラスを使用してコメントを含むドキュメントを読み込み、コメント コレクションにアクセスします。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);
```

## ステップ 2: コメントとその返信を解決する
次に、コメントとその返信を繰り返して、解決済みとしてマークします。

```csharp
Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}
```

上記のコードでは、親コメントにアクセスし、その返信を繰り返し処理します。親コメント ID とその解決ステータスを取得できます。次に、各コメント返信の「完了」マークを更新して、解決策を示します。

## ステップ 3: ドキュメントを保存する
コメントを解決し、そのステータスを更新した後、Document クラスの Save メソッドを使用して、変更したドキュメントをファイルに保存します。

```csharp
doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```

### Aspose.Words for .NET を使用してコメントとその返信を解決するためのソース コードの例
Aspose.Words for .NET を使用してコメントとその返信を解決するための完全なソース コードを次に示します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);

Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}

doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```
ドキュメント ファイルのパスや追加のカスタマイズなど、特定の要件に応じてコードを必ず調整してください。

## 結論
おめでとう！ Aspose.Words for .NET を使用して Word 文書内のコメントとその返信を解決する方法を学習しました。ステップバイステップのガイドに従い、提供されているソース コードを利用することで、コメントの解決を管理し、要件に応じてコメントとその返信のステータスを更新できるようになります。

コメント解決は、ドキュメント内のフィードバックの追跡と管理に役立ちます。さまざまなコメント ステータスを試してカスタマイズし、ドキュメント内のコラボレーションとレビュー プロセスを改善します。

### よくある質問

#### Q: Aspose.Words for .NET でコメントを解決するにはどうすればよいですか?

 A: Aspose.Words for .NET でコメントを解決するには、`Comment.Resolve`を指定するメソッド`Comment`解決したいオブジェクト。これにより、コメントが解決済みとしてマークされ、最終的な文書で非表示になります。

#### Q: Aspose.Words for .NET で解決されたコメントに返信を追加するにはどうすればよいですか?

 A: 解決されたコメントは最終的な文書ではデフォルトで非表示になりますが、解決されたコメントへの返信は、`Comment.AddReply`返信テキストとそれを追加する場所を指定するメソッド。

#### Q: Aspose.Words for .NET で解決されたコメントを表示するにはどうすればよいですか?

 A: デフォルトでは、解決されたコメントは最終ドキュメントでは非表示になります。ただし、次を使用して表示できます。`CommentOptions.ShowResolvedComments`の財産`Document`オブジェクトを設定し、`true`.

#### Q: Aspose.Words for .NET で返信を含むすべてのコメントを非表示にするにはどうすればよいですか?

 A: Aspose.Words for .NET で返信を含むすべてのコメントを非表示にするには、`CommentOptions.CommentDisplayMode`の財産`Document`オブジェクトを選択し、それに設定します`CommentDisplayMode.None`.

#### Q: Aspose.Words for .NET で解決されたコメントのテキストを編集できますか?

 A: はい、Aspose.Words for .NET で解決されたコメントのテキストを編集するには、`Comment.Text`対応するプロパティ`Comment`オブジェクトを編集し、必要に応じてテキストを変更します。