---
title: シンプルなテーブルを作成する
linktitle: シンプルなテーブルを作成する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書に簡単な表を作成する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-tables/create-simple-table/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書に簡単な表を作成する方法を学習します。ステップ バイ ステップ ガイドに従ってコードを理解し、この機能を実装します。このチュートリアルの最後には、Word 文書にプログラムでカスタム表を作成できるようになります。

## ステップ1: プロジェクトのセットアップ
1. Visual Studio を起動し、新しい C# プロジェクトを作成します。
2. Aspose.Words for .NET ライブラリへの参照を追加します。

## ステップ2: ドキュメントの作成とドキュメントジェネレータの初期化
テーブルの構築を開始するには、新しいドキュメントを作成し、ドキュメント ビルダーを初期化する必要があります。次の手順に従います。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//ドキュメントを作成し、ドキュメントジェネレーターを初期化します
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

「YOUR DOCUMENTS DIRECTORY」を、ドキュメント ディレクトリへの実際のパスに置き換えてください。

## ステップ3: 配列の構築
次に、ドキュメント ビルダーが提供するメソッドを使用してテーブルを構築します。次のコードを使用します。

```csharp
//配列の構築を開始する
builder. StartTable();

//最初の行の最初のセルの構築
builder. InsertCell();
builder.Write("Contents of cell 1 of row 1.");

//最初の行の2番目のセルの構築
builder. InsertCell();
builder.Write("Contents of cell 2 of row 1.");

//最初の行を終了し、新しい行を開始するには、次のメソッドを呼び出します。
builder. EndRow();

// 2行目の最初のセルの構築
builder. InsertCell();
builder.Write("Contents of cell 1 of row 2.");

//2行目の2番目のセルの構築
builder. InsertCell();
builder.Write("Contents of cell 2 of row 2.");

//2行目を終了するには次のメソッドを呼び出します
builder. EndRow();

//テーブルの構築が完了したことを示す表示
builder. EndTable();
```

ここではドキュメントビルダーを使用して、テーブルを段階的に構築します。まず、`StartTable()`テーブルを初期化するには、`InsertCell()`セルを挿入し、`Write()`各セルにコンテンツを追加するには、`EndRow()`行を終了し、新しい行を開始します。最後に、`EndTable()`テーブルの構築が完了したことを示します。

## ステップ4: ドキュメントを保存する
最後に、保存する必要がある

  作成されたテーブルを含むドキュメント。次のコードを使用します。

```csharp
//文書を保存する
doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

出力ドキュメントの正しいパスとファイル名を必ず指定してください。

### Aspose.Words for .NET を使用してシンプルなテーブルを作成するためのサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	//テーブルの構築を開始します。
	builder.StartTable();
	builder.InsertCell();
	builder.Write("Row 1, Cell 1 Content.");
	// 2番目のセルを構築します。
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content.");
	//行を終了し、新しい行を開始するには、次のメソッドを呼び出します。
	builder.EndRow();
	// 2 行目の最初のセルを作成します。
	builder.InsertCell();
	builder.Write("Row 2, Cell 1 Content");
	// 2番目のセルを構築します。
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content.");
	builder.EndRow();
	//テーブルの構築が完了したことを知らせます。
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書に簡単な表を作成する方法を学習しました。このステップバイステップ ガイドに従い、提供されている C# コードを実装することで、Word 文書にプログラムでカスタム表を作成できます。この機能を使用すると、データを構造化され明確な方法でフォーマットおよび整理できます。