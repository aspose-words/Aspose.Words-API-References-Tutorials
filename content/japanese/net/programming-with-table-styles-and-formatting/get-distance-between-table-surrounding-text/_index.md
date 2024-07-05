---
title: 表の周囲のテキスト間の距離を取得する
linktitle: 表の周囲のテキスト間の距離を取得する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内のテキストと表の間の距離を取得するためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-table-styles-and-formatting/get-distance-between-table-surrounding-text/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、表内の周囲のテキスト間の距離を取得するプロセスを段階的に説明します。バンドルされている C# ソース コードについて説明し、この機能を理解して独自のプロジェクトに実装するのに役立つ包括的なガイドを提供します。このチュートリアルの最後には、Aspose.Words for .NET を使用して Word 文書内の表と周囲のテキスト間のさまざまな距離にアクセスする方法がわかります。

## ステップ1: ドキュメントディレクトリを定義する
まず、ドキュメント ディレクトリへのパスを設定する必要があります。これは Word ドキュメントが保存されている場所です。「YOUR DOCUMENTS DIRECTORY」を適切なパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ2: 既存のドキュメントを読み込む
次に、既存のWord文書を`Document`クラス。

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## ステップ3: 表と周囲のテキスト間の距離を取得する
表と周囲のテキストの間の距離を取得するには、`GetChild()`方法と`NodeType.Table`プロパティ。配列プロパティを使用してさまざまな距離を表示できます。`DistanceTop`, `DistanceBottom`, `DistanceRight`そして`DistanceLeft`.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Console.WriteLine("Distance between table and top text: " + table.DistanceTop);
Console.WriteLine("Distance between table and bottom text: " + table.DistanceBottom);
Console.WriteLine("Distance between the table and the text on the right: " + table.DistanceRight);
Console.WriteLine("Distance between the table and the text on the left: " + table.DistanceLeft);
```

### Aspose.Words for .NET を使用して表の周囲のテキスト間の距離を取得するためのサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Console.WriteLine("\nGet distance between table left, right, bottom, top and the surrounding text.");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Console.WriteLine(table.DistanceTop);
	Console.WriteLine(table.DistanceBottom);
	Console.WriteLine(table.DistanceRight);
	Console.WriteLine(table.DistanceLeft);
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して、表内の周囲のテキスト間の距離を取得する方法を学習しました。このステップバイステップ ガイドに従うことで、Word ドキュメント内の表と周囲のテキスト間のさまざまな距離に簡単にアクセスできます。Aspose.Words は、ドキュメント内の表を操作および書式設定するための強力で柔軟な API を提供します。この知識があれば、テキストに関連して表のレイアウトを分析し、特定のニーズを満たすことができます。