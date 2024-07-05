---
title: ネストされたテーブル
linktitle: ネストされたテーブル
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書に入れ子になったテーブルを作成する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-tables/nested-table/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書にネストされたテーブルを作成する方法を学習します。ステップ バイ ステップ ガイドに従ってコードを理解し、この機能を実装します。このチュートリアルを終了すると、Word 文書にプログラムでネストされたテーブルを作成できるようになります。

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

## ステップ3: ネストされたテーブルの構築
次に、外側のテーブルにセルを挿入し、最初のセル内に新しいテーブルを作成して、ネストされたテーブルを構築します。次のコードを使用します。

```csharp
//外側の表の最初のセルを挿入します
Cell cell = builder. InsertCell();
builder.Writeln("Cell 1 of the outer table");

//外側の表の2番目のセルを挿入します
builder. InsertCell();
builder.Writeln("Cell 2 of the outer table");

//外部テーブルの終了
builder. EndTable();

//外側のテーブルの最初のセルに移動する
builder.MoveTo(cell.FirstParagraph);

//内部テーブルを構築する
builder. InsertCell();
builder.Writeln("Cell 1 of inner table");
builder. InsertCell();
builder.Writeln("Cell 2 of the inner table");

//内部テーブルの終了
builder. EndTable();
```

ここでは、ドキュメント ビルダーを使用して、外側の表にセルとコンテンツを挿入します。次に、ドキュメント ビルダーのカーソルを外側の表の最初のセルに移動し、セルとコンテンツを挿入して内部に新しい表を構築します。

## ステップ4: 変更したドキュメントを保存する
最後に、ネストされたテーブルを含む変更されたドキュメントを保存する必要があります。次のコードを使用します。

```csharp
doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

出力ドキュメントの正しいパスとファイル名を必ず指定してください。

### Aspose.Words for .NET を使用したネストされたテーブルのサンプル ソース コード 

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
	//この呼び出しを行わないと、下に挿入されたセルは外側のテーブルに追加されます。
	builder.EndTable();
	//外側の表の最初のセルに移動します。
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
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書にネストされたテーブルを作成する方法を学習しました。このステップバイステップ ガイドに従い、提供されている C# コードを実装することで、Word 文書で特定のニーズに合わせてプログラム的にネストされたテーブルを作成できます。
