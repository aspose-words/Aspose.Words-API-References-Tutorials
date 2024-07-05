---
title: フォーマットされた表
linktitle: フォーマットされた表
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書に書式設定された表を作成する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-tables/formatted-table/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書に書式設定された表を作成する方法を学習します。ステップ バイ ステップ ガイドに従ってコードを理解し、この機能を実装します。このチュートリアルの最後には、Word 文書にプログラムでカスタム書式の表を作成できるようになります。

## ステップ1: プロジェクトのセットアップ
1. Visual Studio を起動し、新しい C# プロジェクトを作成します。
2. Aspose.Words for .NET ライブラリへの参照を追加します。

## ステップ2: ドキュメントの作成とドキュメントジェネレータの初期化
フォーマットされたテーブルの構築を開始するには、新しいドキュメントを作成し、ドキュメント ジェネレーターを初期化する必要があります。次の手順に従います。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントを作成し、ドキュメントジェネレーターを初期化します
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

「YOUR DOCUMENTS DIRECTORY」を、ドキュメント ディレクトリへの実際のパスに置き換えてください。

## ステップ3: フォーマットされた表の作成
次に、ドキュメント ビルダーが提供するメソッドを使用して、フォーマットされたテーブルを構築します。次のコードを使用します。

```csharp
//配列の構築を開始する
Table table = builder. StartTable();

//表のヘッダー行の構築
builder. InsertCell();
table. LeftIndent = 20.0;
builder.RowFormat.Height = 40.0;
builder.RowFormat.HeightRule = HeightRule.AtLeast;
builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Font.Size = 16;
builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.CellFormat.Width = 100.0;
builder.Write("Header Row,\n Cell 1");

builder. InsertCell();
builder.Write("Header Row,\n Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Header Row,\n Cell 3");

builder. EndRow();

//アレイ本体の構築
builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
builder.CellFormat.Width = 100.0;
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.RowFormat.Height = 30.0;
builder.RowFormat.HeightRule = HeightRule.Auto;

builder. InsertCell();
builder.Font.Size = 12;
builder.Font.Bold = false;
builder.Write("Content Line 1, Cell 1");

builder. InsertCell();
builder.Write("Content Line 1, Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Content Line 1, Cell

3");

builder. EndRow();

builder. InsertCell();
builder.CellFormat.Width = 100.0;
builder.Write("Content Line 2, Cell 1");

builder. InsertCell();
builder.Write("Content Line 2, Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Content Line 2, Cell 3");

builder. EndRow();

//配列構築の終了
builder. EndTable();
```

ここではドキュメントビルダーを使用して、テーブルを段階的に構築します。まず、`StartTable()`テーブルを初期化します。次に`InsertCell()`セルを挿入し、`Write()`各セルにコンテンツを追加します。また、さまざまな書式設定プロパティを使用して、表の行、セル、テキストの書式を定義します。

## ステップ4: ドキュメントを保存する
最後に、フォーマットされた表を含むドキュメントを保存する必要があります。次のコードを使用します。

```csharp
//文書を保存する
doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

出力ドキュメントの正しいパスとファイル名を必ず指定してください。

### Aspose.Words for .NET を使用した書式設定された表のサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	//テーブル全体の書式設定は、テーブルに少なくとも 1 つの行が存在した後に適用する必要があります。
	table.LeftIndent = 20.0;
	//高さを設定し、ヘッダー行の高さルールを定義します。
	builder.RowFormat.Height = 40.0;
	builder.RowFormat.HeightRule = HeightRule.AtLeast;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Font.Size = 16;
	builder.Font.Name = "Arial";
	builder.Font.Bold = true;
	builder.CellFormat.Width = 100.0;
	builder.Write("Header Row,\n Cell 1");
	//このセルの幅は前のセルから継承されるため、指定する必要はありません。
	builder.InsertCell();
	builder.Write("Header Row,\n Cell 2");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Header Row,\n Cell 3");
	builder.EndRow();
	builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
	builder.CellFormat.Width = 100.0;
	builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
	//高さをリセットし、テーブル本体に異なる高さルールを定義します。
	builder.RowFormat.Height = 30.0;
	builder.RowFormat.HeightRule = HeightRule.Auto;
	builder.InsertCell();
	//フォントの書式をリセットします。
	builder.Font.Size = 12;
	builder.Font.Bold = false;
	builder.Write("Row 1, Cell 1 Content");
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Row 1, Cell 3 Content");
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.Width = 100.0;
	builder.Write("Row 2, Cell 1 Content");
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Row 2, Cell 3 Content.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書に書式設定された表を作成する方法を学習しました。このステップバイステップ ガイドに従い、提供されている C# コードを実装することで、Word 文書に特定の書式でカスタム表をプログラム的に作成できます。この機能を使用すると、視覚的に魅力的で整理された方法でデータを表示および構造化できます。