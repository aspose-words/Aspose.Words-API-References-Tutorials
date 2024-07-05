---
title: 図形を挿入
linktitle: 図形を挿入
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書に図形を挿入する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-shapes/insert-shape/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書に図形を挿入する方法について説明します。図形を使用すると、文書の外観とレイアウトを強化できます。

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

## ステップ3: 図形を挿入する
使用`InsertShape`方法の`DocumentBuilder`オブジェクトを使用して、ドキュメントに図形を挿入します。図形の種類、相対的な水平位置と垂直位置、ページ寸法、サイズ、折り返しの種類を指定します。必要に応じて、図形の回転角度を設定することもできます。

```csharp
Shape shape = builder.InsertShape(ShapeType.TextBox, RelativeHorizontalPosition.Page, 100,
	RelativeVerticalPosition.Page, 100, 50, 50, WrapType.None);
shape.Rotation = 30.0;
builder.Writeln();
shape = builder.InsertShape(ShapeType.TextBox, 50, 50);
shape.Rotation = 30.0;
```

## ステップ4: ドキュメントを保存する
指定されたディレクトリにドキュメントを保存するには、`Save`メソッド。適切なファイル拡張子を持つファイル名を指定します。この例では、ドキュメントを「WorkingWithShapes.InsertShape.docx」として保存します。

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
	Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.InsertShape.docx", saveOptions);
```

### Aspose.Words for .NET を使用して図形を挿入するためのサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertShape(ShapeType.TextBox, RelativeHorizontalPosition.Page, 100,
		RelativeVerticalPosition.Page, 100, 50, 50, WrapType.None);
	shape.Rotation = 30.0;
	builder.Writeln();
	shape = builder.InsertShape(ShapeType.TextBox, 50, 50);
	shape.Rotation = 30.0;
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
	{
		Compliance = OoxmlCompliance.Iso29500_2008_Transitional
	};
	doc.Save(dataDir + "WorkingWithShapes.InsertShape.docx", saveOptions);
```

これで完了です。Aspose.Words for .NET を使用して、Word 文書に図形を正常に挿入できました。