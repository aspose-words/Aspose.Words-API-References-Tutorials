---
title: アスペクト比がロックされました
linktitle: アスペクト比がロックされました
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内の図形のアスペクト比をロックまたはロック解除する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-shapes/aspect-ratio-locked/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の図形のアスペクト比をロックまたはロック解除する方法について説明します。アスペクト比をロックすると、サイズを変更するときに形状の元の比率を維持できます。

## 前提条件
このチュートリアルに従うには、以下が必要です。

- Aspose.Words for .NET ライブラリがインストールされています。
- C# と Word ドキュメントを使用したワード処理の基本的な知識。

## ステップ 1: ドキュメント ディレクトリを設定する
まず、ドキュメント ディレクトリへのパスを設定します。交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメントを保存するディレクトリへの実際のパスを指定します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: 新しいドキュメントと DocumentBuilder を作成する
の新しいインスタンスを作成します。`Document`クラスと`DocumentBuilder`ドキュメントを操作するオブジェクト。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ 3: 画像の形状を挿入する
使用`InsertImage`の方法`DocumentBuilder`オブジェクトを使用して画像図形をドキュメントに挿入します。画像ファイルへのパスをパラメータとして指定します。

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## ステップ 4: アスペクト比をロックまたはロック解除する
をセットする`AspectRatioLocked`形状のプロパティを`true`または`false`それぞれアスペクト比をロックまたはロック解除します。

```csharp
shape.AspectRatioLocked = false; //アスペクト比のロックを解除する
```

## ステップ 5: ドキュメントを保存する
を使用してドキュメントを指定されたディレクトリに保存します。`Save`方法。適切なファイル拡張子を付けて、目的のファイル名を指定します。この例では、ドキュメントを「WorkingWithShapes.AspectRatioLocked.docx」として保存します。

```csharp
doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

### Aspose.Words for .NET を使用したアスペクト比ロックのソース コード例 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

それでおしまい！ Aspose.Words for .NET を使用して、Word 文書内の図形のアスペクト比を正常にロックまたはロック解除できました。