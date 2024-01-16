---
title: テーブルを直接挿入
linktitle: テーブルを直接挿入
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書に表を直接挿入する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-tables/insert-table-directly/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書に表を直接挿入する方法を学習します。ステップバイステップのガイドに従ってコードを理解し、この機能を実装していきます。このチュートリアルを完了すると、プログラムを使用して Word 文書に表を直接挿入できるようになります。

## ステップ 1: プロジェクトのセットアップ
1. Visual Studio を起動し、新しい C# プロジェクトを作成します。
2. Aspose.Words for .NET ライブラリへの参照を追加します。

## ステップ 2: ドキュメントとテーブルの作成
配列を使用して Word Processing を開始するには、新しいドキュメントを作成し、配列を初期化する必要があります。次の手順を実行します：

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//書類作成
Document doc = new Document();

//配列を作成する
Table table = new Table(doc);
doc.FirstSection.Body.AppendChild(table);
```

必ず「YOUR DOCUMENTS DIRECTORY」をドキュメント ディレクトリへの実際のパスに置き換えてください。

## ステップ 3: アレイの構築
次に、行とセルを追加してテーブルを作成します。例として次のコードを使用します。

```csharp
//最初の行を作成する
Row row = new Row(doc);
row.RowFormat.AllowBreakAcrossPages = true;
table.AppendChild(row);

//最初のセルを作成する
Cell cell = new Cell(doc);
cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
cell.CellFormat.Width = 80;
cell.AppendChild(new Paragraph(doc));
cell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 1"));
row.AppendChild(cell);

//行の 2 番目のセルのセルを複製します。
row.AppendChild(cell.Clone(false));
row.LastCell.AppendChild(new Paragraph(doc));
row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 2"));
```

ここでは、次の行を作成します。`AllowBreakAcrossPages`に設定されたプロパティ`true`行間で改ページできるようにします。次に、色付きの背景、固定幅、指定されたテキスト内容を持つセルを作成します。次に、このセルを複製して、行に 2 番目のセルを作成します。

## ステップ 4: 自動フィットテーブル
テーブルに自動調整を適用して、テーブルを正しくフォーマットすることができます。次のコードを使用します。

```csharp
table. AutoFit(AutoFitBehavior.FixedColumnWidths);
```

このコード行は、固定列幅に基づいて自動調整を適用します。

## ステップ 5: の登録

  変更された文書
最後に、テーブルを直接挿入して、変更したドキュメントを保存する必要があります。次のコードを使用します。

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

出力ドキュメントの正しいパスとファイル名を必ず指定してください。

### Aspose.Words for .NET を使用してテーブルを直接挿入するためのサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	//まず、テーブル オブジェクトを作成します。 document オブジェクトを渡す必要があることに注意してください
	//各ノードのコンストラクターに。これは、作成したすべてのノードが属する必要があるためです。
	//ある書類に。
	Table table = new Table(doc);
	doc.FirstSection.Body.AppendChild(table);
	//ここで、EnsureMinimum を呼び出して行とセルを作成できます。この方法が使われています
	//指定されたノードが有効であることを確認します。この場合、有効なテーブルには少なくとも 1 つの行と 1 つのセルが必要です。
	//代わりに、行とテーブルの作成を自分で処理します。
	//アルゴリズム内でテーブルを作成する場合、これが最適な方法です。
	Row row = new Row(doc);
	row.RowFormat.AllowBreakAcrossPages = true;
	table.AppendChild(row);
	//これで、自動フィット設定を適用できるようになりました。
	table.AutoFit(AutoFitBehavior.FixedColumnWidths);
	Cell cell = new Cell(doc);
	cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	cell.CellFormat.Width = 80;
	cell.AppendChild(new Paragraph(doc));
	cell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 1 Text"));
	row.AppendChild(cell);
	//次に、テーブル内の他のセルと行に対してこのプロセスを繰り返します。
	//既存のセルと行を複製することで処理を高速化することもできます。
	row.AppendChild(cell.Clone(false));
	row.LastCell.AppendChild(new Paragraph(doc));
	row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 2 Text"));
	doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書に表を直接挿入する方法を学びました。このステップバイステップ ガイドに従い、提供されている C# コードを実装すると、プログラムで Word 文書に表を直接挿入できます。この機能を使用すると、特定のニーズに応じてテーブルを作成およびカスタマイズできます。