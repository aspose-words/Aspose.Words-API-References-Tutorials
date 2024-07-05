---
title: コメントの解決と返信
linktitle: コメントの解決と返信
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内のコメントとその返信を解決する方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-comments/comment-resolved-and-replies/
---

この包括的なチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内のコメントとその返信を解決する方法を学習します。プロセスをガイドし、必要な C# コード スニペットを提供します。このガイドの最後までに、コメントの解決を管理し、コメントとその返信のステータスを更新できるようになります。

## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
- Aspose.Words for .NET ライブラリがシステムにインストールされています。

## ステップ1: ドキュメントを読み込み、コメントにアクセスする
まず、Document クラスを使用してコメントを含むドキュメントを読み込み、コメント コレクションにアクセスします。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Comments.docx");

NodeCollection comments = doc.GetChildNodes(NodeType.Comment, true);
```

## ステップ2: コメントとその返信を解決する
次に、コメントとその返信を反復処理して、解決済みとしてマークします。

```csharp
Comment parentComment = (Comment)comments[0];

foreach (Comment childComment in parentComment.Replies)
{
    Console.WriteLine(childComment.Ancestor.Id);
    Console.WriteLine(childComment.Done);

    childComment.Done = true;
}
```

上記のコードでは、親コメントにアクセスし、その返信を反復処理します。親コメント ID とその解決ステータスを取得できます。次に、各コメント返信の「完了」マークを更新して、解決を示します。

## ステップ3: ドキュメントを保存する
コメントを解決してステータスを更新したら、Document クラスの Save メソッドを使用して、変更されたドキュメントをファイルに保存します。

```csharp
doc.Save(dataDir + "WorkingWithComments.CommentResolvedAndReplies.docx");
```

### Aspose.Words for .NET を使用してコメントとその返信を解決するためのサンプル ソース コード
以下は、Aspose.Words for .NET を使用してコメントとその返信を解決するための完全なソース コードです。

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
ドキュメントファイルのパスや追加のカスタマイズなど、特定の要件に応じてコードを調整することを忘れないでください。

## 結論
おめでとうございます。Aspose.Words for .NET を使用して Word 文書内のコメントとその返信を解決する方法を学習しました。ステップバイステップのガイドに従い、提供されているソース コードを利用することで、コメントの解決を管理し、必要に応じてコメントとその返信のステータスを更新できるようになりました。

コメントの解決は、ドキュメント内のフィードバックの追跡と管理に役立ちます。さまざまなコメント ステータスを試してカスタマイズし、ドキュメント内の共同作業とレビュー プロセスを改善します。

### よくある質問

#### Q: Aspose.Words for .NET でコメントを解決するにはどうすればよいですか?

 A: Aspose.Words for .NETでコメントを解決するには、`Comment.Resolve`指定方法`Comment`解決したいオブジェクトを選択します。これにより、コメントは解決済みとしてマークされ、最終文書では非表示になります。

#### Q: Aspose.Words for .NET で解決済みのコメントに返信を追加するにはどうすればよいですか?

 A: 解決済みのコメントは最終文書ではデフォルトで非表示になっていますが、`Comment.AddReply`返信テキストとそれを追加する場所を指定する方法。

#### Q: Aspose.Words for .NET で解決済みのコメントを表示するにはどうすればいいですか?

 A: デフォルトでは、解決されたコメントは最終文書では非表示になっています。ただし、`CommentOptions.ShowResolvedComments`の財産`Document`オブジェクトを設定し、`true`.

#### Q: Aspose.Words for .NET で、返信を含むすべてのコメントを非表示にするにはどうすればよいですか?

 A: Aspose.Words for .NETで返信を含むすべてのコメントを非表示にするには、`CommentOptions.CommentDisplayMode`の財産`Document`オブジェクトに設定して`CommentDisplayMode.None`.

#### Q: Aspose.Words for .NET で解決済みのコメントのテキストを編集できますか?

 A: はい、Aspose.Words for .NETで解決されたコメントのテキストを編集するには、`Comment.Text`対応する`Comment`オブジェクトを作成し、必要に応じてテキストを変更します。