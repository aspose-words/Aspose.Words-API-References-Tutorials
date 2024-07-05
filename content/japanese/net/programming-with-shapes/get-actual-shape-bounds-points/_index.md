---
title: 実際の形状境界ポイントを取得する
linktitle: 実際の形状境界ポイントを取得する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書内の図形の実際の境界をポイント (測定単位) 単位で取得する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-shapes/get-actual-shape-bounds-points/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、Word 文書内の図形の実際の境界をポイント (測定単位) で取得する方法について説明します。境界は、文書内の図形のサイズと位置を表します。

## 前提条件
このチュートリアルを実行するには、次のものが必要です。

- Aspose.Words for .NET ライブラリがインストールされています。
- C# と Word 文書を使用した Words Processing に関する基本的な知識。

## ステップ1: 新しいドキュメントとDocumentBuilderを作成する
新しいインスタンスを作成する`Document`クラスと`DocumentBuilder`ドキュメントを操作するオブジェクト。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ2: 画像シェイプを挿入する
使用`InsertImage`方法の`DocumentBuilder`オブジェクトを使用して、ドキュメントに画像シェイプを挿入します。パラメータとして画像ファイルへのパスを指定します。

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
shape.AspectRatioLocked = false;
```

## ステップ3: 実際の形状境界ポイントを取得する
図形の`ShapeRenderer`使用して`GetShapeRenderer`メソッドを使用します。次に、`BoundsInPoints`財産。

```csharp
Console.Write("\nGets the actual bounds of the shape in points: ");
Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```


### Aspose.Words for .NET を使用して実際の形状境界ポイントを取得するためのサンプル ソース コード 

```csharp
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	Console.Write("\nGets the actual bounds of the shape in points: ");
	Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```

これで完了です。Aspose.Words for .NET を使用して、Word 文書内の図形の実際の境界をポイント単位で取得できました。