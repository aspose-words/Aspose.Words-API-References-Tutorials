---
title: スタイルからセルと行の書式設定を展開
linktitle: スタイルからセルと行の書式設定を展開
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、テーブル スタイルからセルと行に書式設定を拡張する手順ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-table-styles-and-formatting/expand-formatting-on-cells-and-row-from-style/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、スタイルからセルと行に書式設定を拡張するプロセスを段階的に説明します。バンドルされている C# ソース コードについて説明し、この機能を理解して独自のプロジェクトに実装するのに役立つ包括的なガイドを提供します。このチュートリアルの最後には、Aspose.Words for .NET を使用して Word ドキュメント内の特定のセルと行にテーブル スタイルの書式設定を適用する方法がわかります。


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

## ステップ3: 最初の表の最初のセルに移動する
まず、文書の最初の表の最初のセルに移動する必要があります。`GetChild()`そして`FirstRow.FirstCell`最初のセルへの参照を取得する方法。

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Cell firstCell = table.FirstRow.FirstCell;
```

## ステップ4: セルの初期書式を表示する
テーブルのスタイルを展開する前に、セルの現在の背景色を表示します。現在の書式設定はテーブルのスタイルに保存されるため、このフィールドは空である必要があります。

```csharp
Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("Shading cell before style expansion: " + cellShadingBefore);
```

## ステップ5: 表スタイルを展開して直接書式設定する
ここで、表のスタイルをドキュメントの`ExpandTableStylesToDirectFormatting()`方法。

```csharp
doc.ExpandTableStylesToDirectFormatting();
```

## ステップ6: スタイル展開後にセルの書式を表示する
ここで、テーブル スタイルを展開した後、セルの背景色を表示します。テーブル スタイルから青色の背景色を適用する必要があります。

```csharp
Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("

Shading the cell after style expansion: " + cellShadingAfter);
```

### Aspose.Words for .NET を使用してスタイルからセルと行の書式設定を展開するためのサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	//ドキュメント内の最初の表の最初のセルを取得します。
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Cell firstCell = table.FirstRow.FirstCell;
	//まずセルの網掛けの色を印刷します。
	//現在のシェーディングはテーブル スタイルに保存されるため、これは空である必要があります。
	Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading before style expansion: " + cellShadingBefore);
	doc.ExpandTableStylesToDirectFormatting();
	//テーブル スタイルを展開した後、セルの網掛けを印刷します。
	//テーブル スタイルから青色の背景パターン カラーが適用されているはずです。
	Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading after style expansion: " + cellShadingAfter);
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して、表スタイルからセルと行に書式設定を拡張する方法を学びました。このステップバイステップ ガイドに従うことで、Word 文書内の特定のセルと行に表スタイルの書式設定を簡単に適用できます。Aspose.Words は、文書内の表を操作および書式設定するための強力で柔軟な API を提供します。この知識があれば、Word 文書のレイアウトと表示をさらにカスタマイズできます。