---
title: スマートアート形状の検出
linktitle: スマートアート形状の検出
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内の Smart Art 図形を検出し、グラフィック表現を識別する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-shapes/detect-smart-art-shape/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の Smart Art シェイプを検出する方法について説明します。スマート アート シェイプは、情報やアイデアを視覚的に表現するために使用されるグラフィック表現です。

## 前提条件
このチュートリアルに従うには、以下が必要です。

- Aspose.Words for .NET ライブラリがインストールされています。
- C# と Word ドキュメントを使用したワード処理の基本的な知識。

## ステップ 1: ドキュメント ディレクトリを設定する
まず、ドキュメント ディレクトリへのパスを設定します。交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメントが置かれているディレクトリへの実際のパスを置き換えます。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: ドキュメントをロードする
を使用して Word 文書をロードします。`Document`コンストラクターを使用して、ドキュメントへのパスをパラメーターとして渡します。

```csharp
Document doc = new Document(dataDir + "Smart Art.docx");
```

## ステップ 3: スマート アートの形状を検出する
タイプの子ノードを反復処理します。`Shape`を使用して文書内で`GetChildNodes`方法。を使用して、各図形にスマート アートがあるかどうかを確認します。`HasSmart Art`財産。

```csharp
int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
```

## ステップ 4: 結果を出力する
ドキュメント内で検出された Smart Art を含む図形の数を印刷します。

```csharp
Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

### Aspose.Words for .NET を使用したスマート アート シェイプの検出のソース コード例 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Smart Art.docx");
	int count = doc.GetChildNodes(NodeType.Shape, true).Cast<Shape>().Count(shape => shape.HasSmart Art);
	Console.WriteLine("The document has {0} shapes with Smart Art.", count);
```

それでおしまい！ Aspose.Words for .NET を使用して、Word 文書内のスマート アート シェイプが正常に検出されました。