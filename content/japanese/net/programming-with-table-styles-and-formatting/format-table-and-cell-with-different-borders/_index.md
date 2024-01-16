---
title: テーブルとセルを異なる枠線で書式設定する
linktitle: テーブルとセルを異なる枠線で書式設定する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、さまざまな枠線でテーブルとセルを書式設定するためのステップバイステップ ガイド。
type: docs
weight: 10
url: /ja/net/programming-with-table-styles-and-formatting/format-table-and-cell-with-different-borders/
---

このチュートリアルでは、Aspose.Words for .NET を使用してテーブルとセルを異なる枠線で書式設定するプロセスを段階的に説明します。バンドルされている C# ソース コードについて説明し、この機能を理解し、独自のプロジェクトに実装するのに役立つ包括的なガイドを提供します。このチュートリアルの最後には、Aspose.Words for .NET を使用して Word 文書内の特定の表とセルにカスタム枠線を適用する方法がわかります。

## ステップ 1: ドキュメント ディレクトリを定義する
まず、ドキュメント ディレクトリへのパスを設定する必要があります。これは、編集した Word 文書を保存する場所です。 「YOUR DOCUMENTS DIRECTORY」を適切なパスに置き換えます。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 2: 新しいドキュメントとドキュメント ビルダーを作成する
次に、の新しいインスタンスを作成する必要があります。`Document`クラスとそのドキュメントのドキュメント コンストラクター。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ 3: 新しいテーブルを開始し、セルを追加する
テーブルの作成を開始するには、`StartTable()`ドキュメントビルダーのメソッドを使用してテーブルにセルを追加します。`InsertCell()`メソッドを使用し、セルの内容を に書き込みます。`Writeln()`方法。

```csharp
Table table = builder. StartTable();
builder. InsertCell();
//表全体に枠線を設定します。
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
//このセルのパディングを設定します。
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
builder. InsertCell();
// 2 番目のセルに別のセル パディングを指定します。
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder. EndRow();
//以前の操作からセルの書式設定をクリアします。
builder.CellFormat.ClearFormatting();
builder. InsertCell();
//この行の最初のセルに太い枠線を作成します。それは違うでしょう
//テーブルに定義された境界線を基準にします。
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
builder.Writeln("Cell #3");
builder. InsertCell();
builder.CellFormat.ClearFormatting();
builder.Writeln("Cell #4");
```

## ステップ 4: ドキュメントを保存する

  修正された
最後に、変更したドキュメントをファイルに保存します。出力ドキュメントの適切な名前と場所を選択できます。

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

おめでとうございます！これで、Aspose.Words for .NET を使用して、異なる枠線を持つテーブルとセルの書式設定が完了しました。

### Aspose.Words for .NET を使用してテーブルとセルを異なる枠線でフォーマットするサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	//表全体の枠線を設定します。
	table.SetBorders(LineStyle.Single, 2.0, Color.Black);
	//このセルのセルのシェーディングを設定します。
	builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
	builder.Writeln("Cell #1");
	builder.InsertCell();
	// 2 番目のセルに別のセルの網掛けを指定します。
	builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
	builder.Writeln("Cell #2");
	builder.EndRow();
	//以前の操作からセルの書式設定をクリアします。
	builder.CellFormat.ClearFormatting();
	builder.InsertCell();
	//この行の最初のセルに大きな境界線を作成します。これは違うでしょう
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
このチュートリアルでは、Aspose.Words for .NET を使用して、テーブルとセルを異なる境界線で書式設定する方法を学びました。このステップバイステップのガイドに従うことで、Word 文書の表とセルの境界線を簡単にカスタマイズできます。 Aspose.Words は、ドキュメント内の表を操作および書式設定するための強力で柔軟な API を提供します。この知識があれば、Word 文書の視覚的なプレゼンテーションを改善し、特定のニーズを満たすことができます。