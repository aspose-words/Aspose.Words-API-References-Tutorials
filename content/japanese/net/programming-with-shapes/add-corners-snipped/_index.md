---
title: 切り取ったコーナーを追加
linktitle: 切り取ったコーナーを追加
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、角を切り取った図形を Word 文書に追加する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-shapes/add-corners-snipped/
---

このチュートリアルでは、Aspose.Words for .NETを使用して、角を切り取った図形をWord文書に追加する方法について説明します。角を切り取った図形は、`InsertShape`方法。

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

## ステップ3: 角を切り取った図形を挿入する
使用`InsertShape`方法の`DocumentBuilder`オブジェクトをクリックして、角を切り取った図形を挿入します。図形の種類を指定します（この場合は、`ShapeType.TopCornersSnipped`) をクリックし、図形の希望するサイズを指定します。

```csharp
builder.InsertShape(ShapeType.TopCornersSnipped, 50, 50);
```

## ステップ4: ドキュメントを保存する
指定されたディレクトリにドキュメントを保存するには、`Save`メソッド。適切なファイル拡張子を持つファイル名を指定します。この例では、ドキュメントを「WorkingWithShapes.AddCornersSnipped.docx」として保存します。

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.Docx)
{
    Compliance = OoxmlCompliance.Iso29500_2008_Transitional
};
doc.Save(dataDir + "WorkingWithShapes.AddCornersSnipped.docx", saveOptions);
```

### Aspose.Words for .NET を使用してコーナーを切り取る例のソース コード 

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

これで完了です。Aspose.Words for .NET を使用して、角を切り取った図形を Word 文書に正常に追加できました。