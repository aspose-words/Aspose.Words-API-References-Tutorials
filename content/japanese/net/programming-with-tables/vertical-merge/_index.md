---
title: 垂直結合
linktitle: 垂直結合
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書内の表のセルを垂直に結合する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-tables/vertical-merge/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の表のセルを垂直に結合する方法を学習します。ステップ バイ ステップ ガイドに従ってコードを理解し、この機能を実装します。このチュートリアルの最後には、Word 文書内の表のセルを垂直に結合することができるようになります。

## ステップ1: プロジェクトのセットアップ
1. Visual Studio を起動し、新しい C# プロジェクトを作成します。
2. Aspose.Words for .NET ライブラリへの参照を追加します。

## ステップ2: ドキュメントの読み込み
ドキュメントで Words Processing を開始するには、次の手順に従います。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//新しいドキュメントを作成する
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

「YOUR DOCUMENTS DIRECTORY」を、ドキュメント ディレクトリへの実際のパスに置き換えてください。

## ステップ3: セルを垂直に結合する
次に、表内のセルを垂直に結合します。次のコードを使用します。

```csharp
//セルを挿入する
builder. InsertCell();

//最初のセルに垂直結合を適用する
builder.CellFormat.VerticalMerge = CellMerge.First;
builder.Write("Text in merged cells.");

//別のセルを挿入
builder. InsertCell();

//セルに垂直結合を適用しない
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in a cell");
builder. EndRow();

//セルを挿入する
builder. InsertCell();

//前のセルとの垂直結合を適用する
builder.CellFormat.VerticalMerge = CellMerge.Previous;

//別のセルを挿入
builder. InsertCell();

//セルに垂直結合を適用しない
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in another cell");
builder. EndRow();

//テーブルの作成を終了する
builder. EndTable();
```

このコードでは、DocumentBuilder コンストラクターを使用してテーブルにセルを挿入します。 CellFormat.VerticalMerge プロパティを使用して、セルに垂直結合を適用します。 最初のセル結合には CellMerge.First を使用し、前のセルと結合するには CellMerge.Previous を使用し、垂直結合しない場合は CellMerge.None を使用します。

## ステップ4: 変更したドキュメントを保存する
最後に、結合されたセルを含む変更されたドキュメントを保存する必要があります。次のコードを使用します。

```csharp
doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

出力ドキュメントの正しいパスとファイル名を必ず指定してください。

### Aspose.Words for .NET を使用した垂直結合のサンプル ソース コード 
```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in one cell");
	builder.EndRow();
	builder.InsertCell();
	//このセルは上のセルに垂直に結合されており、空である必要があります。
	builder.CellFormat.VerticalMerge = CellMerge.Previous;
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in another cell");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の表のセルを垂直に結合する方法を学習しました。このステップバイステップ ガイドに従い、提供されている C# コードを実装することで、表内のセルを垂直に簡単に結合できます。