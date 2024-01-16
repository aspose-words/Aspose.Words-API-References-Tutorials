---
title: 推奨される幅の設定
linktitle: 推奨される幅の設定
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書で優先される表のセル幅を設定する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-tables/preferred-width-settings/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の表のセルに優先幅を設定する方法を学習します。ステップバイステップのガイドに従ってコードを理解し、この機能を実装していきます。このチュートリアルを終えると、Word 文書内の表のセルにさまざまな推奨幅を指定できるようになります。

## ステップ 1: プロジェクトのセットアップ
1. Visual Studio を起動し、新しい C# プロジェクトを作成します。
2. Aspose.Words for .NET ライブラリへの参照を追加します。

## ステップ 2: ドキュメントの作成とドキュメント ジェネレーターの初期化
ドキュメントおよびドキュメント ジェネレーターを使用して Word Processing を開始するには、次の手順に従います。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//書類作成
Document doc = new Document();

//ドキュメントジェネレーターを初期化する
DocumentBuilder builder = new DocumentBuilder(doc);
```

必ず「YOUR DOCUMENTS DIRECTORY」をドキュメント ディレクトリへの実際のパスに置き換えてください。

## ステップ 3: 好みの幅でテーブルを作成する
次に、異なる推奨幅を持つ 3 つのセルを含むテーブルを作成します。次のコードを使用します。

```csharp
//テーブルの始まり
builder. StartTable();

//絶対サイズのセルを挿入する
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln("Cell with a width of 40 points");

//相対的なサイズ (パーセント単位) のセルを挿入します。
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln("Cell with 20% width");

//自動サイズ調整されたセルを挿入する
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Auto-size cell. The size of this cell is calculated from the preferred width of the table. In this case, the cell will fill the rest of the available space.");

//テーブルの終わり
builder. EndTable();
```

ここでは、ドキュメント ビルダーを使用して 3 つのセルからなる表を作成します。最初のセルの優先幅は 40 ポイント、2 番目のセルの優先幅はテーブル幅の 20%、3 番目のセルの優先幅は自動調整されます。

  利用可能なスペースに応じて。

## ステップ 4: 変更したドキュメントを保存する
最後に、表のセルに定義された推奨幅設定を使用して、変更したドキュメントを保存する必要があります。次のコードを使用します。

```csharp
doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

出力ドキュメントの正しいパスとファイル名を必ず指定してください。

### Aspose.Words for .NET を使用した優先幅設定のサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	//異なる推奨幅を持つ 3 つのセルで構成される表の行を挿入します。
	builder.StartTable();
	//絶対サイズのセルを挿入します。
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
	builder.Writeln("Cell at 40 points width");
	//相対（パーセント）サイズのセルを挿入します。
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	builder.Writeln("Cell at 20% width");
	//自動サイズ調整セルを挿入します。
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
	builder.Writeln(
		"Cell automatically sized. The size of this cell is calculated from the table preferred width.");
	builder.Writeln("In this case the cell will fill up the rest of the available space.");
	doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の表のセルに優先幅を設定する方法を学びました。このステップバイステップ ガイドに従い、提供されている C# コードを実装することで、Word 文書の特定のニーズに合わせて表のセル幅をカスタマイズできます。