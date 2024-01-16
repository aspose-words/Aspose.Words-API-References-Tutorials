---
title: 切り取られたコーナーを追加
linktitle: 切り取られたコーナーを追加
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、角が切り取られた図形を Word 文書に追加する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-shapes/add-corners-snipped/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、角が切り取られた図形を Word 文書に追加する方法について説明します。角を切り取った形状はカスタマイズして挿入できます。`InsertShape`方法。

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

## ステップ 3: 角を切り取った形状を挿入する
使用`InsertShape`の方法`DocumentBuilder`オブジェクトを使用して、角を切り取った形状を挿入します。形状の種類を指定します (この場合、`ShapeType.TopCornersSnipped`)、シェイプに必要なサイズを指定します。

```csharp
builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
```

## ステップ 4: ドキュメントを保存する
を使用してドキュメントを指定されたディレクトリに保存します。`Save`方法。適切なファイル拡張子を付けて、目的のファイル名を指定します。この例では、ドキュメントを「WorkingWithShapes.AddCornersSnipped.docx」として保存します。

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);
```

### Aspose.Words for .NET を使用して切り取られたコーナーの追加のソース コード例 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
	OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
	{
		Compliance = OoxmlCompliance.Iso29500_2008_Transitional
	};
	doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);

```

それでおしまい！ Aspose.Words for .NET を使用して、角を切り取った図形を Word 文書に追加することに成功しました。