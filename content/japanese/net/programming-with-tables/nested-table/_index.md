---
title: ネストされたテーブル
linktitle: ネストされたテーブル
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内に入れ子になったテーブルを作成する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-tables/nested-table/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内に入れ子になったテーブルを作成する方法を学習します。ステップバイステップのガイドに従ってコードを理解し、この機能を実装していきます。このチュートリアルを完了すると、Word 文書内にネストされたテーブルをプログラムで作成できるようになります。

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

## ステップ 3: ネストしたテーブルの構築
次に、外側のテーブルにセルを挿入し、最初のセル内に新しいテーブルを作成することで、ネストされたテーブルを構築します。次のコードを使用します。

```csharp
//外部テーブルの最初のセルを挿入します
Cell cell = builder. InsertCell();
builder.Writeln("Cell 1 of the outer table");

//外部テーブルの 2 番目のセルを挿入します
builder. InsertCell();
builder.Writeln("Cell 2 of the outer table");

//外部表の終了
builder. EndTable();

//外部テーブルの最初のセルに移動します
builder.MoveTo(cell.FirstParagraph);

//内部テーブルを構築する
builder. InsertCell();
builder.Writeln("Cell 1 of inner table");
builder. InsertCell();
builder.Writeln("Cell 2 of the inner table");

//内部テーブルの終わり
builder. EndTable();
```

ここでは、ドキュメント ビルダーを使用してセルとコンテンツを外部テーブルに挿入します。次に、ドキュメント ビルダーのカーソルを外側のテーブルの最初のセルに移動し、セルとコンテンツを挿入して内側に新しいテーブルを構築します。

## ステップ 4: 変更したドキュメントを保存する
最後に、変更したドキュメントをネストされたテーブルとともに保存する必要があります。次のコードを使用します。

```csharp
doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

出力ドキュメントの正しいパスとファイル名を必ず指定してください。

### Aspose.Words for .NET を使用したネストしたテーブルのサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Cell cell = builder.InsertCell();
	builder.Writeln("Outer Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Outer Table Cell 2");
	//この呼び出しは、最初のテーブル内にネストされたテーブルを作成するために重要です。
	//この呼び出しがないと、下に挿入されたセルは外部テーブルに追加されます。
	builder.EndTable();
	//外部テーブルの最初のセルに移動します。
	builder.MoveTo(cell.FirstParagraph);
	//内部テーブルを構築します。
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 2");
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内に入れ子になったテーブルを作成する方法を学びました。このステップバイステップ ガイドに従い、提供されている C# コードを実装すると、特定のニーズに応じて入れ子になったテーブルを Word 文書内にプログラム的に作成できます。
