---
title: 単純なテーブルの作成
linktitle: 単純なテーブルの作成
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内に簡単な表を作成する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-tables/create-simple-table/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内に簡単な表を作成する方法を学習します。ステップバイステップのガイドに従ってコードを理解し、この機能を実装していきます。このチュートリアルを終えると、プログラムを使用して Word 文書内にカスタム表を作成できるようになります。

## ステップ 1: プロジェクトのセットアップ
1. Visual Studio を起動し、新しい C# プロジェクトを作成します。
2. Aspose.Words for .NET ライブラリへの参照を追加します。

## ステップ 2: ドキュメントの作成とドキュメント ジェネレーターの初期化
テーブルの構築を開始するには、新しいドキュメントを作成し、ドキュメント ビルダーを初期化する必要があります。次の手順を実行します：

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントを作成し、ドキュメント ジェネレーターを初期化する
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

必ず「YOUR DOCUMENTS DIRECTORY」をドキュメント ディレクトリへの実際のパスに置き換えてください。

## ステップ 3: アレイの構築
次に、ドキュメント ビルダーが提供するメソッドを使用してテーブルを作成します。次のコードを使用します。

```csharp
//アレイの構築を開始する
builder. StartTable();

//最初の行の最初のセルの構築
builder. InsertCell();
builder.Write("Contents of cell 1 of row 1.");

//1列目の2番目のセルの構築
builder. InsertCell();
builder.Write("Contents of cell 2 of row 1.");

//次のメソッドを呼び出して最初の行を終了し、新しい行を開始します。
builder. EndRow();

// 2行目の最初のセルの構築
builder. InsertCell();
builder.Write("Contents of cell 1 of row 2.");

//2列目の2番目のセルの構築
builder. InsertCell();
builder.Write("Contents of cell 2 of row 2.");

//next メソッドを呼び出して 2 行目を終了します
builder. EndRow();

//テーブルの構築が完了したことを示します
builder. EndTable();
```

ここでは、ドキュメント ビルダーを使用して、段階的にテーブルを作成します。まずは電話することから始めます`StartTable()`テーブルを初期化してから使用します`InsertCell()`セルを挿入し、`Write()`各セルにコンテンツを追加します。私たちも使っています`EndRow()`行を終了して新しい行を開始します。最後に、呼び出します`EndTable()`テーブルの構築が完了したことを示します。

## ステップ 4: ドキュメントを保存する
最後に、保存する必要があります

  作成されたテーブルを含むドキュメント。次のコードを使用します。

```csharp
//文書を保存する
doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

出力ドキュメントの正しいパスとファイル名を必ず指定してください。

### Aspose.Words for .NET を使用して単純なテーブルを作成するためのサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	//テーブルの作成を開始します。
	builder.StartTable();
	builder.InsertCell();
	builder.Write("Row 1, Cell 1 Content.");
	// 2 番目のセルを構築します。
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content.");
	//次のメソッドを呼び出して行を終了し、新しい行を開始します。
	builder.EndRow();
	// 2 行目の最初のセルを構築します。
	builder.InsertCell();
	builder.Write("Row 2, Cell 1 Content");
	// 2 番目のセルを構築します。
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content.");
	builder.EndRow();
	//テーブルの構築が完了したことを知らせます。
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内に単純な表を作成する方法を学びました。このステップバイステップ ガイドに従い、提供されている C# コードを実装すると、Word 文書内にプログラムでカスタム テーブルを作成できます。この機能を使用すると、構造的かつ明確な方法でデータをフォーマットおよび整理できます。