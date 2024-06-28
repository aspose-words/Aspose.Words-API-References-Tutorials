---
title: 表の周囲のテキスト間の距離を取得する
linktitle: 表の周囲のテキスト間の距離を取得する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内のテキストと表の間の距離を取得するためのステップバイステップのガイド。
type: docs
weight: 10
url: /ja/net/programming-with-table-styles-and-formatting/get-distance-between-table-surrounding-text/
---

このチュートリアルでは、Aspose.Words for .NET を使用して表内の周囲のテキスト間の距離を取得するプロセスを段階的に説明します。バンドルされている C# ソース コードについて説明し、この機能を理解し、独自のプロジェクトに実装するのに役立つ包括的なガイドを提供します。このチュートリアルの最後には、Aspose.Words for .NET を使用して、Word 文書内の表と周囲のテキストの間のさまざまな距離にアクセスする方法がわかります。

## ステップ 1: ドキュメント ディレクトリを定義する
まず、ドキュメント ディレクトリへのパスを設定する必要があります。ここに Word 文書が配置されます。 「YOUR DOCUMENTS DIRECTORY」を適切なパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 2: 既存のドキュメントをロードする
次に、既存の Word 文書を`Document`クラス。

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## ステップ 3: 表と周囲のテキストの間の距離を取得する
表と周囲のテキストの間の距離を取得するには、次のコマンドを使用して文書内の表にアクセスする必要があります。`GetChild()`方法と`NodeType.Table`財産。次に、配列プロパティを使用してさまざまな距離を表示できます。`DistanceTop`, `DistanceBottom`, `DistanceRight`そして`DistanceLeft`.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Console.WriteLine("Distance between table and top text: " + table.DistanceTop);
Console.WriteLine("Distance between table and bottom text: " + table.DistanceBottom);
Console.WriteLine("Distance between the table and the text on the right: " + table.DistanceRight);
Console.WriteLine("Distance between the table and the text on the left: " + table.DistanceLeft);
```

### Aspose.Words for .NET を使用してテーブル周囲のテキスト間の距離を取得するためのサンプル ソース コード 

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
このチュートリアルでは、Aspose.Words for .NET を使用して表内の周囲のテキスト間の距離を取得する方法を学びました。このステップバイステップのガイドに従うことで、Word 文書内の表と周囲のテキストの間のさまざまな距離に簡単にアクセスできます。 Aspose.Words は、ドキュメント内の表を操作および書式設定するための強力で柔軟な API を提供します。この知識があれば、テキストとの関係で表のレイアウトを分析し、特定のニーズを満たすことができます。