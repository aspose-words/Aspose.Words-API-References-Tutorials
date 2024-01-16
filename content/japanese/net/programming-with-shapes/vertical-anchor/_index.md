---
title: 垂直アンカー
linktitle: 垂直アンカー
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET の垂直アンカー機能を使用して、ドキュメント内で図形を垂直に配置する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-shapes/vertical-anchor/
---

このチュートリアルでは、Aspose.Words for .NET の垂直アンカー機能を使用して、ドキュメント内で図形を垂直に配置する方法について説明します。図形の垂直アンカー プロパティを設定すると、テキストまたはページに対する垂直方向の配置を制御できます。

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

## ステップ 3: 形状を挿入して構成する
を使用してドキュメントに図形を挿入します。`InsertShape`の方法`DocumentBuilder`物体。形状に必要な寸法を設定します。

```csharp
Shape textBox = builder.InsertShape(ShapeType.TextBox, 200, 200);
```

## ステップ 4: 垂直アンカーを設定する
図形の垂直アンカー プロパティを設定して、垂直方向の配置を制御します。この例では、テキストまたはページの下部に図形を固定するために「Bottom」に設定します。

```csharp
textBox.TextBox.VerticalAnchor = TextBoxAnchor.Bottom;
```

## ステップ 5: シェイプにコンテンツを追加する
使用`MoveTo`の方法`DocumentBuilder`オブジェクトを使用して、カーソルを図形の最初の段落に移動します。次に、`Write`シェイプにコンテンツを追加するメソッド。

```csharp
builder.MoveTo(textBox.FirstParagraph);
builder.Write("Textbox contents");
```

## ステップ 6: ドキュメントを保存する
を使用してドキュメントを指定されたディレクトリに保存します。`Save`方法。適切なファイル拡張子を付けて、目的のファイル名を指定します。この例では、ドキュメントを「WorkingWithShapes.VerticalAnchor.docx」として保存します。

```csharp
doc.Save(dataDir + "WorkingWithShapes.VerticalAnchor.docx");
```

### Aspose.Words for .NET を使用した垂直アンカーのソース コード例 

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

それでおしまい！ Aspose.Words for .NET の垂直アンカー機能を使用して、ドキュメント内に図形を垂直に配置することに成功しました。