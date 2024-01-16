---
title: フォーマットされたテーブル
linktitle: フォーマットされたテーブル
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内に書式設定された表を作成する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-tables/formatted-table/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内に書式設定された表を作成する方法を学習します。ステップバイステップのガイドに従ってコードを理解し、この機能を実装していきます。このチュートリアルを終えると、プログラムを使用して Word 文書内にカスタム書式を使用した表を作成できるようになります。

## ステップ 1: プロジェクトのセットアップ
1. Visual Studio を起動し、新しい C# プロジェクトを作成します。
2. Aspose.Words for .NET ライブラリへの参照を追加します。

## ステップ 2: ドキュメントの作成とドキュメント ジェネレーターの初期化
フォーマットされたテーブルの構築を開始するには、新しいドキュメントを作成し、ドキュメント ジェネレーターを初期化する必要があります。次の手順を実行します：

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントを作成し、ドキュメント ジェネレーターを初期化する
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

必ず「YOUR DOCUMENTS DIRECTORY」をドキュメント ディレクトリへの実際のパスに置き換えてください。

## ステップ 3: フォーマットされたテーブルの構築
次に、ドキュメント ビルダーが提供するメソッドを使用して、書式設定されたテーブルを作成します。次のコードを使用します。

```csharp
//アレイの構築を開始する
Table table = builder. StartTable();

//テーブルヘッダー行の構成
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

//アレイ構築の終了
builder. EndTable();
```

ここでは、ドキュメント ビルダーを使用して、段階的にテーブルを作成します。まずは電話することから始めます`StartTable()`テーブルを初期化します。次に、使用します`InsertCell()`セルを挿入し、`Write()`各セルにコンテンツを追加します。また、さまざまな書式設定プロパティを使用して、テーブルの行、セル、テキストの書式設定を定義します。

## ステップ 4: ドキュメントを保存する
最後に、書式設定された表を含むドキュメントを保存する必要があります。次のコードを使用します。

```csharp
//文書を保存する
doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

出力ドキュメントの正しいパスとファイル名を必ず指定してください。

### Aspose.Words for .NET を使用したフォーマット済みテーブルのサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	//テーブル全体の書式設定は、テーブルに少なくとも 1 行が存在した後に適用する必要があります。
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
	//高さをリセットし、テーブル本体に別の高さルールを定義します。
	builder.RowFormat.Height = 30.0;
	builder.RowFormat.HeightRule = HeightRule.Auto;
	builder.InsertCell();
	//フォントの書式設定をリセットします。
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
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内に書式設定された表を作成する方法を学びました。このステップバイステップ ガイドに従い、提供されている C# コードを実装すると、プログラムを使用して Word 文書内に特定の書式を使用したカスタム表を作成できます。この機能を使用すると、視覚的に魅力的で整理された方法でデータを表示および構造化できます。