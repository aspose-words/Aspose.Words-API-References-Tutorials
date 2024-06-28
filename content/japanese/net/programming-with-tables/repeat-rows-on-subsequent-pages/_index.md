---
title: 後続のページで行を繰り返す
linktitle: 後続のページで行を繰り返す
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書の後続のページで表の行を繰り返す方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-tables/repeat-rows-on-subsequent-pages/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、Word 文書の後続のページで表の行を繰り返す方法を学習します。ステップバイステップのガイドに従ってコードを理解し、この機能を実装していきます。このチュートリアルを終えると、Word 文書内の表の後続ページで繰り返す行を指定できるようになります。

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

## ステップ 3: 繰り返し行を含むテーブルを構築する
次に、後続のページに繰り返し行を含むテーブルを作成します。次のコードを使用します。

```csharp
//テーブルの始まり
builder. StartTable();

// 1行目のパラメータ（ヘッダ行）の設定
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;

//最初の行の最初のセルを挿入します
builder. InsertCell();
builder.Writeln("Header line 1");
builder. EndRow();

//1行目の2番目のセルを挿入
builder. InsertCell();
builder.Writeln("Header line 2");
builder. EndRow();

//次の行のパラメータを設定します
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();

//ループして次の行にセルを挿入します
for (int i = 0; i < 50; i++)
{
builder. InsertCell();
builder.RowFormat.HeadingFormat = false;
builder.Write("Text column 1");
builder. InsertCell();
builder.Write("Text column 2");
builder. EndRow();
}

//テーブルの終わり
builder. EndTable();
```

ここでは、ドキュメント ビルダーを使用して、2 つのヘッダー行と複数のデータ行を含むテーブルを作成します。の`RowFormat.HeadingFormat`パラメータは、後続のページで繰り返されるヘッダー行をマークするために使用されます。

## ステップ 4: 変更したドキュメントを保存する
ついに米国

  表の後続のページにヘッダー行が繰り返されるように変更したドキュメントを保存する必要があります。次のコードを使用します。

```csharp
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

出力ドキュメントの正しいパスとファイル名を必ず指定してください。

### Aspose.Words for .NET を使用した後続のページで行を繰り返すサンプル ソース コード 

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.StartTable();
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;
builder.InsertCell();
builder.Writeln("Heading row 1");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Heading row 2");
builder.EndRow();
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();
for (int i = 0; i < 50; i++)
{
	builder.InsertCell();
	builder.RowFormat.HeadingFormat = false;
	builder.Write("Column 1 Text");
	builder.InsertCell();
	builder.Write("Column 2 Text");
	builder.EndRow();
}
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して、Word 文書の後続のページで表の行を繰り返す方法を学習しました。このステップバイステップ ガイドに従い、提供されている C# コードを実装すると、Word 文書内で特定のニーズに応じて繰り返す行を指定できます。