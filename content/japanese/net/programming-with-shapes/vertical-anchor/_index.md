---
title: 垂直アンカー
linktitle: 垂直アンカー
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET の垂直アンカー機能を使用して、ドキュメント内で図形を垂直に配置する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-shapes/vertical-anchor/
---

このチュートリアルでは、Aspose.Words for .NET の垂直アンカー機能を使用して、ドキュメント内で図形を垂直に配置する方法について説明します。図形の垂直アンカー プロパティを設定すると、テキストまたはページに対する図形の垂直配置を制御できます。

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

## ステップ3: 図形を挿入して構成する
ドキュメントに図形を挿入するには、`InsertShape`方法の`DocumentBuilder`オブジェクト。図形の希望の寸法を設定します。

```csharp
Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
```

## ステップ4: 垂直アンカーを設定する
図形の垂直方向の配置を制御するには、図形の垂直アンカー プロパティを設定します。この例では、図形をテキストまたはページの下部に固定するために、これを「下」に設定しています。

```csharp
textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
```

## ステップ5: 図形にコンテンツを追加する
使用`MoveTo`方法の`DocumentBuilder`オブジェクトを使用してカーソルを図形の最初の段落に移動します。次に、`Write`図形にコンテンツを追加する方法。

```csharp
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Textbox contents");
```

## ステップ6: ドキュメントを保存する
指定されたディレクトリにドキュメントを保存するには、`Save`メソッド。適切なファイル拡張子を持つファイル名を指定します。この例では、ドキュメントを「WorkingWithShapes.VerticalAnchor.docx」として保存します。

```csharp
doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

### Aspose.Words for .NET を使用した垂直アンカーのサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
	textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
	builder.MoveTo(textBox.FirstParagraph);
	builder.Write("Textbox contents");
	doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

これで完了です。Aspose.Words for .NET の垂直アンカー機能を使用して、ドキュメント内で図形を垂直に配置することができました。