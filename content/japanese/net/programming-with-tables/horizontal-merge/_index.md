---
title: 水平結合
linktitle: 水平結合
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 表内のセルを水平に結合する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-tables/horizontal-merge/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の表のセルを水平に結合する方法を学習します。ステップ バイ ステップ ガイドに従ってコードを理解し、この機能を実装します。このチュートリアルの最後には、Word 表のセルをプログラムで水平に結合することができるようになります。

## ステップ1: プロジェクトのセットアップ
1. Visual Studio を起動し、新しい C# プロジェクトを作成します。
2. Aspose.Words for .NET ライブラリへの参照を追加します。

## ステップ2: ドキュメントの作成とドキュメントジェネレータの初期化
表とセルを使用して Words Processing を開始するには、新しいドキュメントを作成し、ドキュメント ジェネレーターを初期化する必要があります。次の手順に従います。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントを作成し、ドキュメントジェネレーターを初期化します
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

「YOUR DOCUMENTS DIRECTORY」を、ドキュメント ディレクトリへの実際のパスに置き換えてください。

## ステップ3: セルを水平に結合して表を作成する
次に、Aspose.Words for .NET が提供するプロパティを使用して、テーブルを作成し、水平方向のセル結合を適用します。次のコードを使用します。

```csharp
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.First;
builder.Write("Text in merged cells.");
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.Previous;
//このセルは前のセルと結合されており、空である必要があります。
builder. EndRow();

builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.None;
builder.Write("Text in a cell.");
builder. InsertCell();
builder.Write("Text in another cell.");
builder. EndRow();
builder. EndTable();
```

ここでは、ドキュメントビルダーを使用して表を作成し、セルの水平結合プロパティを設定します。`HorizontalMerge`の財産`CellFormat`オブジェクトを使用して、各セルに適用する水平方向の結合の種類を指定します。`CellMerge.First`最初のセルを次のセルと結合し、`CellMerge.Previous`現在のセルを前のセルと結合します。`CellMerge.None`セルを結合しないことを示します。

## ステップ4: 変更したドキュメントを保存する
最後に、セルを水平方向に結合した変更済みのドキュメントを保存する必要があります。次のコードを使用します。

```csharp
doc.Save(data

Dir + "WorkingWithTables.HorizontalMerge.docx");
```

出力ドキュメントの正しいパスとファイル名を必ず指定してください。

### Aspose.Words for .NET を使用した水平結合のサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	//このセルは前のセルに結合されており、空である必要があります。
	builder.CellFormat.HorizontalMerge = CellMerge.Previous;
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.None;
	builder.Write("Text in one cell.");
	builder.InsertCell();
	builder.Write("Text in another cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.HorizontalMerge.docx");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の表のセルを水平に結合する方法を学習しました。このステップバイステップ ガイドに従い、提供されている C# コードを実装することで、Word 表に水平セル結合をプログラムで適用できます。この機能により、より複雑な表レイアウトを作成し、データをより適切に整理できます。