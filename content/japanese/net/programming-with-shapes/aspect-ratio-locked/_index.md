---
title: アスペクト比が固定されています
linktitle: アスペクト比が固定されています
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書内の図形のアスペクト比をロックまたはロック解除する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-shapes/aspect-ratio-locked/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の図形の縦横比をロックまたはロック解除する方法について説明します。縦横比をロックすると、図形のサイズを変更するときに元の比率を維持できます。

## 前提条件
このチュートリアルを実行するには、次のものが必要です。

- Aspose.Words for .NET ライブラリがインストールされています。
- C# と Word 文書を使用した Words Processing に関する基本的な知識。

## ステップ1: ドキュメントディレクトリを設定する
まず、ドキュメントディレクトリへのパスを設定します。`"YOUR DOCUMENT DIRECTORY"`ドキュメントを保存するディレクトリへの実際のパスを入力します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ2: 新しいドキュメントとDocumentBuilderを作成する
新しいインスタンスを作成する`Document`クラスと`DocumentBuilder`ドキュメントを操作するオブジェクト。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ3: 画像シェイプを挿入する
使用`InsertImage`方法の`DocumentBuilder`オブジェクトを使用して、ドキュメントに画像シェイプを挿入します。パラメータとして画像ファイルへのパスを指定します。

```csharp
Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
```

## ステップ4: アスペクト比をロックまたはロック解除する
をセットする`AspectRatioLocked`形状の特性`true`または`false`それぞれアスペクト比をロックまたはロック解除します。

```csharp
shape.AspectRatioLocked = false; //アスペクト比のロックを解除
```

## ステップ5: ドキュメントを保存する
指定されたディレクトリにドキュメントを保存するには、`Save`メソッド。適切なファイル拡張子を持つファイル名を指定します。この例では、ドキュメントを「WorkingWithShapes.AspectRatioLocked.docx」として保存します。

```csharp
doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

### Aspose.Words for .NET を使用したアスペクト比固定のサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertImage(ImagesDir + "Transparent background logo.png");
	shape.AspectRatioLocked = false;
	doc.Save(dataDir + "WorkingWithShapes.AspectRatioLocked.docx");
```

これで完了です。Aspose.Words for .NET を使用して、Word 文書内の図形の縦横比を正常にロックまたはロック解除できました。