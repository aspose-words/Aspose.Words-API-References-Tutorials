---
title: 改訂版にアクセス
linktitle: 改訂版にアクセス
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書の改訂版にアクセスします。
type: docs
weight: 10
url: /ja/net/working-with-revisions/access-revised-version/
---

このステップバイステップ ガイドでは、Aspose.Words for .NET を使用して Word 文書の改訂版にアクセスする方法を説明します。完全なソース コードを提供し、マークダウン出力をフォーマットする方法を説明します。

## ステップ1: ドキュメントの読み込み

最初のステップは、修正を含むドキュメントをアップロードすることです。

```csharp
Document doc = new Document(MyDir + "Revisions.docx");
doc.UpdateListLabels();
```

## ステップ2: 改訂版にアクセスする

それでは、文書の改訂版に移りましょう。

```csharp
doc.RevisionsView = RevisionsView.Final;
```

## ステップ3: リビジョンを参照する

次に、ドキュメント内に存在するリビジョンをループし、リスト項目である段落の特定の情報を表示します。

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

### Aspose.Words for .NET を使用した Access 改訂版のサンプル ソース コード

Aspose.Words for .NET を使用してドキュメントの改訂版にアクセスするための完全なソース コードは次のとおりです。

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

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書の改訂版にアクセスする方法を学習しました。文書を読み込み、改訂版に移動して改訂版を参照することで、リスト項目である段落の特定の情報を取得できました。Aspose.Words for .NET は、レビューへのアクセスなど、Word 文書を操作するための強力な機能を提供します。この知識を使用して、Aspose.Words for .NET を使用して独自の Word 文書の改訂版にアクセスできるようになりました。

### よくある質問

#### Q: 修正を加えたドキュメントを Aspose.Words for .NET に読み込むにはどうすればよいですか?

 A:`Document` Aspose.Words for .NET のクラスを使用して、リビジョンを含むファイルからドキュメントを読み込みます。ドキュメントの完全なパスを指定できます。

```csharp
Document doc = new Document("path/to/the/document.docx");
```

#### Q: Aspose.Words for .NET でドキュメントの改訂版にアクセスするにはどうすればよいですか?

 A:`RevisionsView`の財産`Document`オブジェクトを使用して、ドキュメントの改訂版にアクセスします。`RevisionsView`財産に`RevisionsView.Final`修正を加えずに最終バージョンを表示します。

```csharp
doc.RevisionsView = RevisionsView.Final;
```

#### Q: Aspose.Words for .NET でドキュメントのリビジョンを参照するにはどうすればよいですか?

A: 使用してください`foreach`ループを使用して、文書内のリビジョンを反復処理します。`Revisions`の財産`Document`ドキュメントのすべてのリビジョンのコレクションを取得するオブジェクト。

```csharp
foreach (Revision revision in doc.Revisions)
{
     //各リビジョンをここで処理します
}
```

#### Q: Aspose.Words for .NET で段落がリスト項目であるかどうかを確認する方法を教えてください。

 A:`IsListItem`の財産`Paragraph`オブジェクトは段落がリスト項目であるかどうかをチェックします。`IsListItem`不動産収益`true`段落がリスト項目である場合は、そうでない場合は`false`.

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