---
title: 表とセルを異なる境界線で書式設定する
linktitle: 表とセルを異なる境界線で書式設定する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、異なる境界線でテーブルとセルをフォーマットするためのステップ バイ ステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-table-styles-and-formatting/format-table-and-cell-with-different-borders/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、表とセルをさまざまな境界線で書式設定する手順を順を追って説明します。バンドルされている C# ソース コードについて説明し、この機能を理解して独自のプロジェクトに実装するのに役立つ包括的なガイドを提供します。このチュートリアルの最後には、Aspose.Words for .NET を使用して Word 文書内の特定の表とセルにカスタム境界線を適用する方法がわかります。

## ステップ1: ドキュメントディレクトリを定義する
まず、ドキュメント ディレクトリへのパスを設定する必要があります。これは、編集した Word 文書を保存する場所です。「YOUR DOCUMENTS DIRECTORY」を適切なパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ2: 新しいドキュメントとドキュメントビルダーを作成する
次に、新しいインスタンスを作成する必要があります。`Document`クラスとそのドキュメントのドキュメント コンストラクター。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ3: 新しい表を作成してセルを追加する
テーブルの作成を開始するには、`StartTable()`ドキュメントビルダーのメソッドを使用してテーブルにセルを追加します。`InsertCell()`メソッドを使用してセルの内容を書き込みます`Writeln()`方法。

```csharp
Table table = builder. StartTable();
builder.InsertCell();
//表全体の境界線を設定します。
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
//このセルのパディングを設定します。
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
builder.InsertCell();
// 2 番目のセルに異なるセル パディングを指定します。
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder.EndRow();
//以前の操作によるセルの書式設定をクリアします。
builder.CellFormat.ClearFormatting();
builder.InsertCell();
//この行の最初のセルに太い罫線を作成します。
//テーブルに定義された境界線を基準にします。
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
builder.Writeln("Cell #3");
builder.InsertCell();
builder.CellFormat.ClearFormatting();
builder.Writeln("Cell #4");
```

## ステップ4: ドキュメントを保存する

  修正された
最後に、変更したドキュメントをファイルに保存します。出力ドキュメントに適切な名前と場所を選択できます。

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

おめでとうございます！Aspose.Words for .NET を使用して、異なる境界線を持つテーブルとセルをフォーマットしました。

### Aspose.Words for .NET を使用して表とセルを異なる境界線で書式設定するためのサンプル ソース コード 

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.StartTable();
builder.InsertCell();
//表全体の境界線を設定します。
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
//このセルのセルの網掛けを設定します。
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
builder.InsertCell();
// 2 番目のセルに異なるセルの網かけを指定します。
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder.EndRow();
//以前の操作によるセルの書式設定をクリアします。
builder.CellFormat.ClearFormatting();
builder.InsertCell();
//この行の最初のセルに大きい境界線を作成します。これは異なります
//テーブルに設定された境界線と比較します。
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
builder.Writeln("Cell #3");
builder.InsertCell();
builder.CellFormat.ClearFormatting();
builder.Writeln("Cell #4");
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して、表とセルを異なる境界線で書式設定する方法を学びました。このステップバイステップ ガイドに従うことで、Word 文書内の表とセルの境界線を簡単にカスタマイズできます。Aspose.Words は、文書内の表を操作および書式設定するための強力で柔軟な API を提供します。この知識があれば、Word 文書の視覚的なプレゼンテーションを改善し、特定のニーズを満たすことができます。