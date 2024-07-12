---
title: 画像
linktitle: 画像
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して画像を挿入およびカスタマイズする方法をステップバイステップ ガイドで学習します。
type: docs
weight: 10
url: /ja/net/working-with-markdown/image/
---

この例では、Aspose.Words for .NET で画像機能を使用する方法について説明します。画像を使用すると、イラストやグラフィックをドキュメントに挿入できます。

## ステップ1: ドキュメントジェネレーターの使用

まず、ドキュメント ジェネレーターを使用してドキュメントにコンテンツを追加します。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## ステップ2: 画像の挿入

画像を挿入するには、`Shape`クラスと画像の種類を指定します。`ShapeType.Image`画像の折り返しタイプも設定します`WrapType.Inline`.

```csharp
Shape shape = new Shape(builder.Document, ShapeType.Image);
shape. WrapType = WrapType. Inline;
```

## ステップ3: 画像のカスタマイズ

画像のフルパスを指定してカスタマイズします。例えば`"/attachment/1456/pic001.png"`画像にタイトルを追加します。

```csharp
shape.ImageData.SourceFullName = "/attachment/1456/pic001.png";
shape.ImageData.Title = "Title";
```

### Aspose.Words for .NET を使用した画像のサンプル ソース コード

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

 A: ローカルファイルからAspose.Wordsに画像を挿入するには、`Shape`クラスと`InsertImage`方法。

#### Q: Aspose.Words で URL から画像を挿入できますか?

 A: はい、Aspose.WordsでURLから画像を挿入できます。同じ方法を使用できます。`InsertImage`メソッドを使用し、ローカル ファイル パスの代わりにイメージ URL を指定します。

#### Q: Aspose.Words で画像のサイズを変更するにはどうすればよいですか?

 A: Aspose.Wordsで画像のサイズを変更するには、`Width`そして`Height`の特性`Shape`物体。

#### Q: Aspose.Words で画像にフィルターを適用できますか?

 A: はい、Aspose.Wordsでは画像にフィルターを適用できます。たとえば、画像にぼかしフィルターを適用することができます。`ApplyGaussianBlur`方法の`Shape`物体。

#### Q: Aspose.Words で画像を別の画像に置き換えるにはどうすればよいですか?

 A: Aspose.Wordsで画像を別の画像に置き換えるには、`Replace`方法の`Shape`クラス。このメソッドはパラメータとして`Shape`置換する画像のオブジェクトと`Shape`新しいイメージのオブジェクト。