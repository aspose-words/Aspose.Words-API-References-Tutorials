---
title: 推奨幅設定
linktitle: 推奨幅設定
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書で推奨される表のセル幅を設定する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-tables/preferred-width-settings/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、Word 文書内の表のセルの推奨幅を設定する方法を学習します。ステップ バイ ステップ ガイドに従ってコードを理解し、この機能を実装します。このチュートリアルの最後には、Word 文書内の表のセルにさまざまな推奨幅を指定できるようになります。

## ステップ1: プロジェクトのセットアップ
1. Visual Studio を起動し、新しい C# プロジェクトを作成します。
2. Aspose.Words for .NET ライブラリへの参照を追加します。

## ステップ2: ドキュメントの作成とドキュメントジェネレータの初期化
ドキュメントとドキュメント ジェネレーターを使用して Words Processing を開始するには、次の手順に従います。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメント作成
Document doc = new Document();

//ドキュメントジェネレータを初期化する
DocumentBuilder builder = new DocumentBuilder(doc);
```

「YOUR DOCUMENTS DIRECTORY」を、ドキュメント ディレクトリへの実際のパスに置き換えてください。

## ステップ3: 好みの幅でテーブルを構築する
次に、異なる推奨幅を持つ 3 つのセルを含むテーブルを作成します。次のコードを使用します。

```csharp
//表の始まり
builder. StartTable();

//絶対サイズのセルを挿入する
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln("Cell with a width of 40 points");

//相対的なサイズのセルを挿入します（パーセンテージ）
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln("Cell with 20% width");

//自動サイズ調整セルを挿入する
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Auto-size cell. The size of this cell is calculated from the preferred width of the table. In this case, the cell will fill the rest of the available space.");

//表の終わり
builder. EndTable();
```

ここでは、ドキュメントビルダーを使用して3つのセルを持つ表を作成します。最初のセルの推奨幅は40ポイント、2番目のセルの推奨幅は表の幅の20%、3番目のセルの推奨幅は自動的に調整されます。

  利用可能なスペースに応じて異なります。

## ステップ4: 変更したドキュメントを保存する
最後に、テーブル セルに定義された推奨幅設定を使用して、変更したドキュメントを保存する必要があります。次のコードを使用します。

```csharp
doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

出力ドキュメントの正しいパスとファイル名を必ず指定してください。

### Aspose.Words for .NET を使用した推奨幅設定のサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	//異なる推奨幅を持つ 3 つのセルで構成されるテーブル行を挿入します。
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
	//自動サイズ調整されたセルを挿入します。
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
	builder.Writeln(
		"Cell automatically sized. The size of this cell is calculated from the table preferred width.");
	builder.Writeln("In this case the cell will fill up the rest of the available space.");
	doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して、Word 文書内の表のセルの推奨幅設定を設定する方法を学習しました。このステップバイステップ ガイドに従い、提供されている C# コードを実装することで、Word 文書内の表のセルの幅を特定のニーズに合わせてカスタマイズできます。