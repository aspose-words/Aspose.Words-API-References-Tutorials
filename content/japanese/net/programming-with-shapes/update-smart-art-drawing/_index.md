---
title: スマートアート描画の更新
linktitle: スマートアート描画の更新
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内の Smart Art 描画を更新する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-shapes/update-smart-art-drawing/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の Smart Art 描画を更新する方法について説明します。文書内の図形を反復処理し、Smart Art があるかどうかを確認することで、Smart Art 描画を更新し、データに加えられた変更を反映できます。

## 前提条件
このチュートリアルを実行するには、次のものが必要です。

- Aspose.Words for .NET ライブラリがインストールされています。
- C# と Word 文書を使用した Words Processing に関する基本的な知識。

## ステップ1: ドキュメントディレクトリを設定する
まず、ドキュメントディレクトリへのパスを設定します。`"YOUR DOCUMENT DIRECTORY"`ドキュメントが配置されているディレクトリへの実際のパスを入力します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ2: ドキュメントを読み込む
スマートアートの描画を含むWord文書を読み込み、`Document`クラスコンストラクター。

```csharp
Document doc = new Document(dataDir + "SmartArt.docx");
```

## ステップ3: スマートアートの描画を更新する
ドキュメント内の図形を反復処理するには、`GetChildNodes`方法`NodeType.Shape`パラメータ。各図形にスマートアートが含まれているかどうかを確認します。`HasSmartArt`プロパティを呼び出し、trueの場合は`UpdateSmartArtDrawing`Smart Art 描画を更新する方法。

```csharp
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```


### Aspose.Words for .NET を使用して Smart Art Drawing を更新するためのサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "SmartArt.docx");
	foreach (Shape shape in doc.GetChildNodes(NodeType.Shape, true))
		if (shape.HasSmartArt)
			shape.UpdateSmartArtDrawing();
```

これで完了です。Aspose.Words for .NET を使用して、Word 文書内の Smart Art 描画が正常に更新されました。