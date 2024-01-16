---
title: スマート アート描画を更新する
linktitle: スマート アート描画を更新する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内の Smart Art 描画を更新する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-shapes/update-smart-art-drawing/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word ドキュメント内の Smart Art 描画を更新する方法について説明します。ドキュメント内の図形を繰り返し処理し、スマート アートがあるかどうかを確認することで、データに加えられた変更を反映するようにスマート アート図面を更新できます。

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
Smart Art 描画を含む Word 文書をロードします。`Document`クラスコンストラクター。

```csharp
Document doc = new Document(dataDir + "SmartArt.docx");
```

## ステップ 3: スマート アート図面を更新する
を使用してドキュメント内の図形を反復処理します。`GetChildNodes`を使用したメソッド`NodeType.Shape`パラメータ。を使用して、各図形にスマート アートがあるかどうかを確認します。`HasSmartArt`プロパティを呼び出し、true の場合は、`UpdateSmartArtDrawing` Smart Art 図面を更新するメソッド。

```csharp
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```


### Aspose.Words for .NET を使用したスマート アート図面の更新のソース コード例 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "SmartArt.docx");
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```

それでおしまい！ Aspose.Words for .NET を使用して Word 文書内の Smart Art 描画を正常に更新しました。