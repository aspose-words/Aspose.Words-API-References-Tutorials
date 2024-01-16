---
title: 画像
linktitle: 画像
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して画像を挿入およびカスタマイズする方法について説明するステップバイステップ ガイドです。
type: docs
weight: 10
url: /ja/net/working-with-markdown/image/
---

この例では、Aspose.Words for .NET で画像機能を使用する方法を説明します。画像を使用すると、ドキュメントにイラストやグラフィックを挿入できます。

## ステップ 1: ドキュメント ジェネレーターを使用する

まず、ドキュメント ジェネレーターを使用してドキュメントにコンテンツを追加します。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## ステップ 2: 画像を挿入する

画像を挿入するには、`Shape`ここでクラスと画像のタイプを指定します`ShapeType.Image`。また、画像のラップタイプを次のように設定します。`WrapType.Inline`.

```csharp
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape. WrapType = WrapType. Inline;
```

## ステップ 3: 画像のカスタマイズ

たとえば、フルパスを指定して画像をカスタマイズします。`"/attachment/1456/pic001.png"`、画像にタイトルを追加します。

```csharp
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "Title";
```

### Aspose.Words for .NET を使用した画像のソース コードの例

```csharp
//ドキュメント ビルダーを使用してドキュメントにコンテンツを追加します。
DocumentBuilder builder = new DocumentBuilder();

//画像を挿入します。
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape.WrapType = WrapType.Inline;
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "title";
builder.InsertNode(shape);
```

おめでとうございます！これで、Aspose.Words for .NET で画像機能を使用する方法を学習しました。


### よくある質問

#### Q: ローカル ファイルから Aspose.Words に画像を挿入するにはどうすればよいですか?

 A: ローカル ファイルから Aspose.Words に画像を挿入するには、`Shape`クラスと`InsertImage`方法。

#### Q: Aspose.Words に URL から画像を挿入できますか?

 A: はい、Aspose.Words の URL から画像を挿入できます。同じものを使用できます`InsertImage`メソッドを使用して、ローカル ファイル パスの代わりに画像 URL を指定します。

#### Q: Aspose.Words で画像のサイズを変更するにはどうすればよいですか?

 A: Aspose.Words で画像のサイズを変更するには、`Width`そして`Height`のプロパティ`Shape`物体。

#### Q: Aspose.Words の画像にフィルターを適用できますか?

A: はい、Aspose.Words で画像にフィルターを適用できます。たとえば、次のコマンドを使用して画像にぼかしフィルターを適用できます。`ApplyGaussianBlur`の方法`Shape`物体。

#### Q: Aspose.Words で 1 つの画像を別の画像に置き換えるにはどうすればよいですか?

 A: Aspose.Words で 1 つの画像を別の画像に置き換えるには、`Replace`の方法`Shape`クラス。このメソッドはパラメータとして`Shape`置き換えられる画像のオブジェクトと`Shape`新しい画像のオブジェクト。