---
title: 改訂版にアクセスする
linktitle: 改訂版にアクセスする
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書の改訂版にアクセスします。
type: docs
weight: 10
url: /ja/net/working-with-revisions/access-revised-version/
---

このステップバイステップ ガイドでは、Aspose.Words for .NET を使用して Word 文書の改訂版にアクセスする方法を説明します。完全なソース コードを提供し、マークダウン出力をフォーマットする方法を示します。

## ステップ 1: ドキュメントをロードする

最初のステップは、リビジョンを含むドキュメントをアップロードすることです。

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();
```

## ステップ 2: 改訂版にアクセスする

それでは、この文書の改訂版に移ります。

```csharp
doc.RevisionsView = RevisionsView.Final;
```

## ステップ 3: リビジョンを参照する

次に、ドキュメント内に存在するリビジョンをループして、リスト項目である段落の特定の情報を表示します。

```csharp
foreach (Revision revision in doc.Revisions)
{
     if (revision.ParentNode.NodeType == NodeType.Paragraph)
     {
         Paragraph paragraph = (Paragraph)revision.ParentNode;
         if (paragraph.IsListItem)
         {
             Console.WriteLine(paragraph.ListLabel.LabelString);
             Console.WriteLine(paragraph.ListFormat.ListLevel);
         }
     }
}
```

### Aspose.Words for .NET を使用した Access 改訂版のソース コード例

Aspose.Words for .NET を使用してドキュメントの改訂版にアクセスするための完全なソース コードを次に示します。

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();

//ドキュメントの改訂版に切り替えます。
doc.RevisionsView = RevisionsView.Final;

foreach (Revision revision in doc.Revisions)
{
	 if (revision.ParentNode.NodeType == NodeType.Paragraph)
	 {
		 Paragraph paragraph = (Paragraph)revision.ParentNode;
		 if (paragraph.IsListItem)
		 {
			 Console.WriteLine(paragraph.ListLabel.LabelString);
			 Console.WriteLine(paragraph.ListFormat.ListLevel);
		 }
	 }
}
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書の改訂版にアクセスする方法を学びました。ドキュメントをロードし、改訂版に移動し、改訂版を参照することで、リスト項目である段落の特定の情報を取得できました。 Aspose.Words for .NET は、レビューへのアクセスなど、Word ドキュメントを操作するための強力な機能を提供します。この知識を利用して、Aspose.Words for .NET を使用して独自の Word 文書の改訂版にアクセスできるようになりました。

### よくある質問

#### Q: リビジョンを含むドキュメントを Aspose.Words for .NET にロードするにはどうすればよいですか?

 A: を使用してください。`Document`Aspose.Words for .NET のクラスを使用して、リビジョンを含むファイルからドキュメントをロードします。ドキュメントの完全なパスを指定できます。

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Q: Aspose.Words for .NET でドキュメントの改訂版にアクセスするにはどうすればよいですか?

 A: を使用してください。`RevisionsView`の財産`Document`オブジェクトを使用してドキュメントの改訂版にアクセスします。の値を設定できます。`RevisionsView`財産を`RevisionsView.Final`リビジョンのない最終バージョンを表示します。

```csharp
doc.RevisionsView = RevisionsView.Final;
```

#### Q: Aspose.Words for .NET でドキュメントのリビジョンを参照するにはどうすればよいですか?

 A: を使用してください`foreach`ループを使用して、ドキュメント内に存在するリビジョンを反復処理します。使用できます`Revisions`の財産`Document`オブジェクトを使用して、ドキュメントのすべてのリビジョンのコレクションを取得します。

```csharp
foreach (Revision revision in doc.Revisions)
{
     //ここで各リビジョンを処理します
}
```

#### Q: 段落が Aspose.Words for .NET のリスト項目であるかどうかを確認するにはどうすればよいですか?

 A: を使用してください。`IsListItem`の財産`Paragraph`オブジェクトが段落がリスト項目であるかどうかを確認します。の`IsListItem`財産の返還`true`段落がリスト項目の場合、それ以外の場合は戻り値`false`.

```csharp
if (paragraph.IsListItem)
{
     //段落はリスト項目です
}
else
{
     //段落はリスト項目ではありません
}
```