---
title: グループシェイプを追加
linktitle: グループシェイプを追加
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、複数の図形を含むグループ図形を Word 文書に追加する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-shapes/add-group-shape/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、複数の図形を含むグループ図形を Word 文書に追加する方法について説明します。グループ図形を使用すると、複数の図形を 1 つのエンティティとして結合して操作できます。

## 前提条件
このチュートリアルを実行するには、次のものが必要です。

- Aspose.Words for .NET ライブラリがインストールされています。
- C# と Word 文書を使用した Words Processing に関する基本的な知識。

## ステップ1: ドキュメントディレクトリを設定する
まず、ドキュメントディレクトリへのパスを設定します。`"YOUR DOCUMENT DIRECTORY"`ドキュメントを保存するディレクトリへの実際のパスを入力します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ2: 新しいドキュメントとGroupShapeを作成する
新しいインスタンスを作成する`Document`クラスと`GroupShape`ドキュメントを操作するオブジェクト。

```csharp
Document doc = new Document();
doc.EnsureMinimum();
GroupShape groupShape = new GroupShape(doc);
```

## ステップ 3: GroupShape に図形を作成して追加する
次のような個別の図形を作成します。`accentBorderShape`そして`actionButtonShape`使用して`Shape`クラス。必要に応じてプロパティをカスタマイズします。これらの図形を`groupShape`物体。

```csharp
Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1) { Width = 100, Height = 100 };
groupShape.AppendChild(accentBorderShape);

Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
{
    Left = 100,
    Width = 100,
    Height = 200
};
groupShape.AppendChild(actionButtonShape);
```

## ステップ4: GroupShapeの寸法を設定する
幅、高さ、座標サイズを設定します。`groupShape`.

```csharp
groupShape.Width = 200;
groupShape.Height = 200;
groupShape.CoordSize = new Size(200, 200);
```

## ステップ5: GroupShapeをドキュメントに挿入する
作成する`DocumentBuilder`オブジェクトを挿入し、`groupShape`文書に`InsertNode`方法。

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(groupShape);
```

## ステップ6: ドキュメントを保存する
指定されたディレクトリにドキュメントを保存するには、`Save`メソッド。適切なファイル拡張子を持つファイル名を指定します。この例では、ドキュメントを「WorkingWithShapes.AddGroupShape.docx」として保存します。

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

### Aspose.Words for .NET を使用してグループ図形を追加するためのサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	doc.EnsureMinimum();
	GroupShape groupShape = new GroupShape(doc);
	Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1) { Width = 100, Height = 100 };
	groupShape.AppendChild(accentBorderShape);
	Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
	{
		Left = 100, Width = 100, Height = 200
	};
	groupShape.AppendChild(actionButtonShape);
	groupShape.Width = 200;
	groupShape.Height = 200;
	groupShape.CoordSize = new Size(200, 200);
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertNode(groupShape);
	doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

これで完了です。Aspose.W を使用して、複数の図形を含むグループ図形を Word 文書に追加できました。