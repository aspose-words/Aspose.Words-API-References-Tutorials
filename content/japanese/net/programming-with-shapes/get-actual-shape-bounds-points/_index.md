---
title: 実際の形状の境界点を取得する
linktitle: 実際の形状の境界点を取得する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書内の図形の実際の境界をポイント (測定単位) で取得する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-shapes/get-actual-shape-bounds-points/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、Word 文書内の図形の実際の境界をポイント (測定単位) で取得する方法について説明します。境界は、ドキュメント内の図形のサイズと位置を表します。

## 前提条件
このチュートリアルに従うには、以下が必要です。

- Aspose.Words for .NET ライブラリがインストールされています。
- C# と Word ドキュメントを使用したワード処理の基本的な知識。

## ステップ 1: 新しいドキュメントと DocumentBuilder を作成する
の新しいインスタンスを作成します。`Document`クラスと`DocumentBuilder`ドキュメントを操作するオブジェクト。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ 2: 画像の形状を挿入する
使用`InsertImage`の方法`DocumentBuilder`オブジェクトを使用して画像図形をドキュメントに挿入します。画像ファイルへのパスをパラメータとして指定します。

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
shape.AspectRatioLocked = false;
```

## ステップ 3: 実際の形状境界点を取得する
シェイプにアクセスします`ShapeRenderer`を使用して`GetShapeRenderer`方法。次に、次のコマンドを使用して、シェイプの実際の境界をポイント単位で取得します。`BoundsInPoints`財産。

```csharp
Console.Write("\nGets the actual bounds of the shape in points: ");
Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```


### Aspose.Words for .NET を使用して実際の形状の境界点を取得するためのソース コードの例 

```csharp
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	Console.Write("\nGets the actual bounds of the shape in points: ");
	Console.WriteLine(shape.GetShapeRenderer().BoundsInPoints);
```

それでおしまい！ Aspose.Words for .NET を使用して、Word 文書内のポイント単位で図形の実際の境界を取得することに成功しました。