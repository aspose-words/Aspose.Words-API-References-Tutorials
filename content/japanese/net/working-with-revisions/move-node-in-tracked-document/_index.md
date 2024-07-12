---
title: 追跡ドキュメント内のノードを移動
linktitle: 追跡ドキュメント内のノードを移動
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、追跡されたドキュメント内のノードを移動します。
type: docs
weight: 10
url: /ja/net/working-with-revisions/move-node-in-tracked-document/
---

このステップバイステップ ガイドでは、Aspose.Words for .NET を使用して追跡された Word 文書内のノードを移動する方法について説明します。完全なソース コードを提供し、マークダウン出力をフォーマットする方法を説明します。

## ステップ1: ドキュメントの作成

最初のステップは、新しいドキュメントを作成し、段落を追加することです。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Number of paragraphs: {0}", body.Paragraphs.Count);
```

## ステップ2: 変更履歴を追跡する

ドキュメント内でリビジョン追跡を有効にします。

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

## ステップ3: ノードを移動する

リビジョンを生成しながら、ノード (段落) をある位置から別の位置に移動します。

```csharp
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
     Node nextNode = node. NextSibling;
     body. InsertBefore(node, referenceNode);
     node = nextNode;
}
```

## ステップ4: レビューの追跡を停止する

ドキュメント内の変更の追跡を停止します。

```csharp
doc.StopTrackRevisions();
```

## ステップ5: ドキュメントを保存する

テキスト入力フォームフィールドを挿入した後、`Save`メソッド。適切なファイル パスを指定してください。

```csharp
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```


### Aspose.Words for .NET を使用して追跡ドキュメント内のノードを移動するサンプル ソース コード

以下は、Aspose.Words for .NET を使用して追跡されたドキュメント内のノードを移動するための完全なソース コードです。


```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Paragraph 1");
builder.Writeln("Paragraph 2");
builder.Writeln("Paragraph 3");
builder.Writeln("Paragraph 4");
builder.Writeln("Paragraph 5");
builder.Writeln("Paragraph 6");
Body body = doc.FirstSection.Body;
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);

//リビジョンの追跡を開始します。
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));

//ノードをある場所から別の場所に移動するときにリビジョンを生成します。
Node node = body.Paragraphs[3];
Node endNode = body.Paragraphs[5].NextSibling;
Node referenceNode = body.Paragraphs[0];
while (node != endNode)
{
	Node nextNode = node.NextSibling;
	body.InsertBefore(node, referenceNode);
	node = nextNode;
}

//リビジョンの追跡プロセスを停止します。
doc.StopTrackRevisions();

//移動元の範囲には 3 つの追加の段落があります。
Console.WriteLine("Paragraph count: {0}", body.Paragraphs.Count);
doc.Save(dataDir + "WorkingWithRevisions.MoveNodeInTrackedDocument.docx");
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して、追跡された Word 文書内のノードを移動する方法を学びました。文書の作成、リビジョン追跡の有効化、ノードの移動、リビジョン追跡の停止の手順に従うことで、この操作を正常に実行できました。Aspose.Words for .NET は、Word 文書でのワード処理用の強力なツールであり、リビジョンを管理するための高度な機能を提供します。この知識を使用して、Aspose.Words for .NET を使用してリビジョンを追跡しながら、独自の Word 文書内のノードを移動できるようになりました。

### よくある質問

#### Q: Aspose.Words for .NET ドキュメントでリビジョン追跡を有効にするにはどうすればよいでしょうか?

 A: Aspose.Words for .NETドキュメントでリビジョン追跡を有効にするには、`StartTrackRevisions`方法の`Document`オブジェクト。このメソッドは、リビジョンの作成者の名前とリビジョンのフォローアップの開始日をパラメータとして受け取ります。

```csharp
doc.StartTrackRevisions("Author", new DateTime(2020, 12, 23, 14, 0, 0));
```

#### Q: リビジョンを生成せずに追跡されたドキュメント内のノードを移動するにはどうすればよいですか?

 A: 追跡されたドキュメント内のノードをリビジョンを生成せずに移動したい場合は、`Remove`そして`InsertAfter`または`InsertBefore`の`Node`オブジェクト。たとえば、段落を別の段落の後に移動するには、次のコードを使用します。

```csharp
Node nodeToMove = document.FirstSection.Body.Paragraphs[0];
Node referenceNode = document.FirstSection.Body.Paragraphs[1];
nodeToMove.Remove();
document.FirstSection.Body.InsertAfter(nodeToMove, referenceNode);
```

#### Q: Aspose.Words for .NET ドキュメントでリビジョン追跡を停止するにはどうすればよいですか?

 A: Aspose.Words for .NETドキュメントのリビジョンの追跡を停止するには、`StopTrackRevisions`方法の`Document`物体。

```csharp
doc.StopTrackRevisions();
```