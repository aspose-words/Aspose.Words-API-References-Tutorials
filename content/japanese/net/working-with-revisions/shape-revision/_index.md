---
title: 形状修正
linktitle: 形状修正
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内の図形を修正します。
type: docs
weight: 10
url: /ja/net/working-with-revisions/shape-revision/
---

このステップバイステップ ガイドでは、Aspose.Words for .NET を使用して Word 文書内の図形を修正する方法を説明します。完全なソース コードを提供し、マークダウン出力をフォーマットする方法を示します。

## ステップ 1: ドキュメントの作成と図形の追加

最初のステップは、新しいドキュメントを作成し、図形を追加することです。

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## ステップ 2: リビジョンを追跡し、別の形状を追加する

リビジョン追跡をオンにして、別のシェイプを追加します。

```csharp
doc.StartTrackRevisions("John Doe");

shape = new Shape(doc, ShapeType.Sun);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## ステップ 3: 形状コレクションを取得し、リビジョンを確認する

ドキュメントから形状のコレクションを取得し、各形状に関連付けられたリビジョンを確認します。

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

## ステップ 4: 図形移動リビジョンの確認

形状変位のリビジョンを含む既存のドキュメントをロードし、関連するリビジョンを確認します。

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```

### Aspose.Words for .NET を使用した Shape Revision のソース コード例

Aspose.Words for .NET を使用してドキュメント内の図形を修正するための完全なソース コードを次に示します。

```csharp
Document doc = new Document();

//リビジョンを追跡せずにインライン図形を挿入します。
Assert.False(doc.TrackRevisions);
Shape shape = new Shape(doc, ShapeType.Cube);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

//リビジョンの追跡を開始してから、別の図形を挿入します。
doc.StartTrackRevisions("John Doe");
shape = new Shape(doc, ShapeType.Sun);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

//追加した 2 つの図形だけを含むドキュメントの図形コレクションを取得します。
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

//最初の図形を削除します。
shapes[0].Remove();

//変更の追跡中にその図形を削除したため、その図形は削除リビジョンとしてカウントされます。
Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

//また、変更の追跡中に別の図形を挿入したため、その図形は挿入リビジョンとしてカウントされます。
Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);

//ドキュメントには移動された図形が 1 つありますが、図形移動リビジョンにはその図形のインスタンスが 2 つあります。
// 1 つは到着先での形状、もう 1 つは元の場所での形状です。
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

//これは改訂への動きであり、その到達先の形でもあります。
Assert.False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

//これはリビジョンからの移動であり、元の位置のシェイプです。
Assert.True(shapes[1].IsMoveFromRevision);
Assert.False(shapes[1].IsMoveToRevision);
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の図形を修正する方法を学びました。ドキュメントを作成し、リビジョン追跡を有効にし、各図形に関連付けられたリビジョンを確認し、図形を移動するためのリビジョンを確認するという手順に従って、リビジョンを正常に管理することができました。 Aspose.Words for .NET は、Word ドキュメント内のレビューとフォームを備えた Word Processing 用の強力な API を提供します。

### よくある質問

#### Q: Aspose.Words for .NET で新しいドキュメントを作成し、図形を追加するにはどうすればよいですか?

A: Aspose.Words for .NET で新しいドキュメントを作成し、図形を追加するには、次のコードを使用できます。ここでは、立方体と太陽という 2 つの図形をドキュメントの最初のセクションに追加します。

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

#### Q: Aspose.Words for .NET でリビジョン追跡を有効にするにはどうすればよいですか?

 A: Aspose.Words for .NET でリビジョン追跡を有効にするには、`StartTrackRevisions`の方法`Document`物体。このメソッドは、リビジョンの作成者の名前をパラメータとして受け取ります。

```csharp
doc.StartTrackRevisions("John Doe");
```

#### Q: Aspose.Words for .NET ドキュメント内の各図形に関連付けられたリビジョンを確認するにはどうすればよいですか?

A: Aspose.Words for .NET ドキュメント内の各図形に関連付けられたリビジョンを確認するには、次のコマンドを使用してドキュメントの図形のコレクションを取得できます。`GetChildNodes`を使用したメソッド`NodeType.Shape`ノードタイプ。その後、各シェイプにアクセスできます`IsDeleteRevision`, `IsInsertRevision`, `IsMoveFromRevision` 、 そして`IsMoveToRevision`プロパティを使用して、形状に関連付けられているリビジョンのタイプを決定します。

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

#### Q: Aspose.Words for .NET ドキュメント内の図形のディスプレイスメント リビジョンを確認するにはどうすればよいですか?

 A: Aspose.Words for .NET ドキュメント内のシェイプ ディスプレイスメントのリビジョンを確認するには、シェイプ ディスプレイスメントのリビジョンを含む既存のドキュメントをロードします。その後、各シェイプにアクセスできます`IsMoveFromRevision`そして`IsMoveToRevision`プロパティを使用して、移動されているかどうか、移動されている場合にはどこからどこへ移動するかを判断します。

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```