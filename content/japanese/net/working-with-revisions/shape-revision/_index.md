---
title: 形状修正
linktitle: 形状修正
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内の図形を修正します。
type: docs
weight: 10
url: /ja/net/working-with-revisions/shape-revision/
---

このステップバイステップ ガイドでは、Aspose.Words for .NET を使用して Word 文書内の図形を修正する方法について説明します。完全なソース コードを提供し、マークダウン出力の書式設定方法を説明します。

## ステップ1: ドキュメントの作成と図形の追加

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

## ステップ2: 変更を追跡し、別の図形を追加する

リビジョン追跡をオンにして、別の図形を追加します。

```csharp
doc.StartTrackRevisions("John Doe");

shape = new Shape(doc, ShapeType.Sun);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

## ステップ3: シェイプコレクションを取得してリビジョンを確認する

ドキュメントから図形のコレクションを取得し、各図形に関連付けられているリビジョンを確認します。

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

## ステップ4: 図形移動の修正を確認する

形状変位の修正を含む既存のドキュメントを読み込み、関連する修正を確認します。

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```

### Aspose.Words for .NET を使用した図形修正のサンプル ソース コード

以下は、Aspose.Words for .NET を使用してドキュメント内の図形を修正するための完全なソース コードです。

```csharp
Document doc = new Document();

//リビジョンを追跡せずにインライン シェイプを挿入します。
Assert.False(doc.TrackRevisions);
Shape shape = new Shape(doc, ShapeType.Cube);
shape.WrapType = WrapType.Inline;
shape.Width = 100.0;
shape.Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);

//修正の追跡を開始し、別の図形を挿入します。
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

//変更が追跡されている間にその図形を削除したため、その図形は削除リビジョンとしてカウントされます。
Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

//また、変更を追跡しながら別の図形を挿入したので、その図形は挿入リビジョンとしてカウントされます。
Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);

//ドキュメントには移動された図形が 1 つありますが、図形移動のリビジョンにはその図形のインスタンスが 2 つ含まれます。
// 1 つは到着先の形状になり、もう 1 つは元の位置の形状になります。
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

//これは修正への動きであり、到着先での形状でもあります。
Assert.False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

//これは、元の場所にある形状であるリビジョンからの移動です。
Assert.True(shapes[1].IsMoveFromRevision);
Assert.False(shapes[1].IsMoveToRevision);
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の図形を修正する方法を学びました。文書の作成、修正の追跡の有効化、各図形に関連付けられた修正の確認、図形の移動の修正の確認の手順に従うことで、修正を正常に管理できました。Aspose.Words for .NET は、Word 文書のレビューとフォームを備えた強力な Words Processing API を提供します。

### よくある質問

#### Q: Aspose.Words for .NET で新しいドキュメントを作成し、図形を追加するにはどうすればよいですか?

A: Aspose.Words for .NET で新しいドキュメントを作成し、図形を追加するには、次のコードを使用できます。ここでは、立方体と太陽の 2 つの図形をドキュメントの最初のセクションに追加します。

```csharp
Document doc = new Document();
Assert.False(doc.TrackRevisions);

Shape shape = new Shape(doc, ShapeType.Cube);
shape. WrapType = WrapType. Inline;
shape. Width = 100.0;
shape. Height = 100.0;
doc.FirstSection.Body.FirstParagraph.AppendChild(shape);
```

#### Q: Aspose.Words for .NET でリビジョン追跡を有効にするにはどうすればいいですか?

 A: Aspose.Words for .NETでリビジョントラッキングを有効にするには、`StartTrackRevisions`方法の`Document`オブジェクト。このメソッドは、リビジョンの作成者の名前をパラメータとして受け取ります。

```csharp
doc.StartTrackRevisions("John Doe");
```

#### Q: Aspose.Words for .NET ドキュメント内の各図形に関連付けられたリビジョンを確認するにはどうすればよいですか?

A: Aspose.Words for .NETドキュメント内の各図形に関連付けられたリビジョンを確認するには、`GetChildNodes`方法`NodeType.Shape`ノードタイプ。その後、各シェイプの`IsDeleteRevision`, `IsInsertRevision`, `IsMoveFromRevision` 、 そして`IsMoveToRevision`シェイプに関連付けられているリビジョンの種類を決定するプロパティ:

```csharp
List<Shape> shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert.AreEqual(ShapeType.Cube, shapes[0].ShapeType);
Assert.True(shapes[0].IsDeleteRevision);

Assert.AreEqual(ShapeType.Sun, shapes[1].ShapeType);
Assert.True(shapes[1].IsInsertRevision);
```

#### Q: Aspose.Words for .NET ドキュメント内の図形の変位リビジョンを確認するにはどうすればよいですか?

 A: Aspose.Words for .NET ドキュメント内の図形変位リビジョンを確認するには、図形変位リビジョンを含む既存のドキュメントをロードします。その後、各図形の`IsMoveFromRevision`そして`IsMoveToRevision`移動されているかどうか、移動されている場合はどこからどこへ移動されているかを判断するためのプロパティ:

```csharp
doc = new Document(MyDir + "Revision shape.docx");

shapes = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().ToList();
Assert.AreEqual(2, shapes.Count);

Assert. False(shapes[0].IsMoveFromRevision);
Assert.True(shapes[0].IsMoveToRevision);

Assert.True(shapes[1].IsMoveFromRevision);
Assert. False(shapes[1].IsMoveToRevision);
```