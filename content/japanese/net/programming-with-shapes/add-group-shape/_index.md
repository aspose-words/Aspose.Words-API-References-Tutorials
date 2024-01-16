---
title: グループ形状の追加
linktitle: グループ形状の追加
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、複数の図形を含むグループ図形を Word 文書に追加する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-shapes/add-group-shape/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、複数の図形を含むグループ図形を Word 文書に追加する方法について説明します。グループ シェイプを使用すると、複数のシェイプを 1 つのエンティティとして組み合わせて操作できます。

## 前提条件
このチュートリアルに従うには、以下が必要です。

- Aspose.Words for .NET ライブラリがインストールされています。
- C# と Word ドキュメントを使用したワード処理の基本的な知識。

## ステップ 1: ドキュメント ディレクトリを設定する
まず、ドキュメント ディレクトリへのパスを設定します。交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメントを保存するディレクトリへの実際のパスを指定します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: 新しいドキュメントと GroupShape を作成する
の新しいインスタンスを作成します。`Document`クラスと`GroupShape`ドキュメントを操作するオブジェクト。

```csharp
Document doc = new Document();
doc.EnsureMinimum();
GroupShape groupShape = new GroupShape(doc);
```

## ステップ 3: シェイプを作成して GroupShape に追加する
などの個別の形状を作成します。`accentBorderShape`そして`actionButtonShape`を使用して`Shape`クラス。必要に応じてプロパティをカスタマイズします。これらの形状を`groupShape`物体。

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

## ステップ 4: GroupShape の寸法を設定する
幅、高さ、座標サイズを設定します。`groupShape`.

```csharp
groupShape.Width = 200;
groupShape.Height = 200;
groupShape.CoordSize = new Size(200, 200);
```

## ステップ 5: GroupShape をドキュメントに挿入する
を作成します`DocumentBuilder`オブジェクトを挿入して、`groupShape`を使用して文書に取り込みます`InsertNode`方法。

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(groupShape);
```

## ステップ 6: ドキュメントを保存する
を使用してドキュメントを指定されたディレクトリに保存します。`Save`方法。適切なファイル拡張子を付けて、目的のファイル名を指定します。この例では、ドキュメントを「WorkingWithShapes.AddGroupShape.docx」として保存します。

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

### Aspose.Words for .NET を使用したグループ図形の追加のソース コード例 

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

それでおしまい！ Aspose.W を使用して、複数の図形を含むグループ図形を Word 文書に追加できました。