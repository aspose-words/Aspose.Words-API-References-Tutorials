---
title: 水平マージ
linktitle: 水平マージ
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word テーブル内のセルを水平方向に結合する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-tables/horizontal-merge/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書の表内のセルを水平方向に結合する方法を学習します。ステップバイステップのガイドに従ってコードを理解し、この機能を実装していきます。このチュートリアルを終えると、Word の表内のセルをプログラムで水平方向に結合できるようになります。

## ステップ 1: プロジェクトのセットアップ
1. Visual Studio を起動し、新しい C# プロジェクトを作成します。
2. Aspose.Words for .NET ライブラリへの参照を追加します。

## ステップ 2: ドキュメントの作成とドキュメント ジェネレーターの初期化
表とセルを使用して Word Processing を開始するには、新しい文書を作成し、文書ジェネレーターを初期化する必要があります。次の手順を実行します：

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントを作成し、ドキュメント ジェネレーターを初期化する
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

必ず「YOUR DOCUMENTS DIRECTORY」をドキュメント ディレクトリへの実際のパスに置き換えてください。

## ステップ 3: セルを水平方向に結合してテーブルを作成する
次に、テーブルを構築し、Aspose.Words for .NET が提供するプロパティを使用して水平方向のセル結合を適用します。次のコードを使用します。

```csharp
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.First;
builder.Write("Text in merged cells.");
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.Previous;
//このセルは前のセルとマージされており、空になっている必要があります。
builder. EndRow();

builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.None;
builder.Write("Text in a cell.");
builder. InsertCell();
builder.Write("Text in another cell.");
builder. EndRow();
builder. EndTable();
```

ここでは、ドキュメント ビルダーを使用してテーブルを作成し、セルの水平結合プロパティを設定します。私たちが使用するのは、`HorizontalMerge`の財産`CellFormat`オブジェクトを使用して、各セルに適用する水平結合のタイプを指定します。使用する`CellMerge.First`次のセルを使用しながら、最初のセルを次のセルとマージします。`CellMerge.Previous`現在のセルを前のセルとマージします。`CellMerge.None`セルを結合しないことを示します。

## ステップ 4: 変更したドキュメントを保存する
最後に、セルを水平方向に結合して変更したドキュメントを保存する必要があります。次のコードを使用します。

```csharp
doc.Save(data

Dir + "WorkingWithTables.HorizontalMerge.docx");
```

出力ドキュメントの正しいパスとファイル名を必ず指定してください。

### Aspose.Words for .NET を使用した水平マージのサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	//このセルは前のセルにマージされているため、空になっている必要があります。
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
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書の表内のセルを水平方向に結合する方法を学習しました。このステップバイステップ ガイドに従い、提供されている C# コードを実装すると、Word の表に水平セルの結合をプログラム的に適用できます。この機能を使用すると、より複雑なテーブル レイアウトを作成し、データをより適切に整理できます。