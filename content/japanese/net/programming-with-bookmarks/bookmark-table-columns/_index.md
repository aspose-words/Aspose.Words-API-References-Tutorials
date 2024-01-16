---
title: Word 文書の表の列をブックマークする
linktitle: Word 文書の表の列をブックマークする
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内の表の列をブックマークする方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-bookmarks/bookmark-table-columns/
---

この記事では、Aspose.Words for .NET ライブラリの Bookmark Table Columns 関数の使用方法を理解するために、上記の C# ソース コードを調べます。この機能を使用すると、Word 文書内の表の特定の列をブックマークし、その列のコンテンツにアクセスできます。

## 前提条件

- C# 言語の基本的な知識。
- Aspose.Words ライブラリがインストールされた .NET 開発環境。

## ステップ 1: テーブルの作成

テーブル列にブックマークを作成する前に、まず、`DocumentBuilder`物体。この例では、2 行 2 列のテーブルを作成します。

```csharp
builder. StartTable();

builder. InsertCell();

builder. StartBookmark("MyBookmark");

builder.Write("This is cell 1 of row 1");

builder. InsertCell();
builder.Write("This is cell 2 of row 1");

builder. EndRow();

builder. InsertCell();
builder.Writeln("This is cell 1 of row 2");

builder. InsertCell();
builder.Writeln("This is cell 2 of row 2");

builder. EndRow();
builder. EndTable();
```

## ステップ 2: 列ブックマークの作成

私たちが使用するのは、`StartBookmark`テーブルの特定の列にブックマークを作成するメソッド。この例では、ブックマークに「MyBookmark」という名前を使用します。

```csharp
builder. StartBookmark("MyBookmark");
```

## ステップ 3: 列のコンテンツにアクセスする

ドキュメント内のすべてのブックマークを調べて、その名前を表示します。ブックマークが列の場合、列インデックスと`GetText`方法：

```csharp
foreach (Bookmark

  bookmark in doc.Range.Bookmarks)
{
Console.WriteLine("Bookmark: {0}{1}", bookmark.Name, bookmark.IsColumn?" (Column)": "");

if (bookmark.IsColumn)
{
if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
Console.WriteLine(row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar));
}
}
```

### Aspose.Words for .NET を使用したブックマーク テーブル列のソース コードの例

Aspose.Words for .NET を使用してテーブル列にブックマークを作成する方法を示す完全なサンプル ソース コードを次に示します。

```csharp

	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartTable();
	
	builder.InsertCell();

	builder.StartBookmark("MyBookmark");

	builder.Write("This is row 1 cell 1");

	builder.InsertCell();
	builder.Write("This is row 1 cell 2");

	builder.EndRow();

	builder.InsertCell();
	builder.Writeln("This is row 2 cell 1");

	builder.InsertCell();
	builder.Writeln("This is row 2 cell 2");

	builder.EndRow();
	builder.EndTable();
	
	builder.EndBookmark("MyBookmark");
	

	
	foreach (Bookmark bookmark in doc.Range.Bookmarks)
	{
		Console.WriteLine("Bookmark: {0}{1}", bookmark.Name, bookmark.IsColumn ? " (Column)" : "");

		if (bookmark.IsColumn)
		{
			if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
				Console.WriteLine(row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar));
		}
	}
	
        
```

## 結論

この記事では、C# ソース コードを調べて、Aspose.Words for .NET の Bookmark Table Columns 関数の使用方法を理解しました。ステップバイステップのガイドに従って、Word 文書内の表の特定の列をブックマークし、その列のコンテンツにジャンプしました。

### Word 文書のブックマーク表の列に関する FAQ

#### Q: Aspose.Words for .NET の「テーブル列のブックマーク」機能を使用するための前提条件は何ですか?

A: Aspose.Words for .NET の「テーブル列のブックマーク」機能を使用するには、C# 言語の基本的な知識が必要です。 Aspose.Words ライブラリがインストールされた .NET 開発環境も必要です。

#### Q: Aspose.Words for .NET を使用して Word 文書内に列を含むテーブルを作成するにはどうすればよいですか?

 A: Aspose.Words for .NET を使用して Word 文書内に列を含むテーブルを作成するには、`DocumentBuilder`オブジェクトを使用してセルとコンテンツをテーブルに挿入します。サンプルコードは次のとおりです。

```csharp
builder. StartTable();

builder. InsertCell();
builder.Write("Contents of cell 1 of column 1");

builder. InsertCell();
builder.Write("Contents of cell 2 of column 2");

builder. EndRow();

builder. InsertCell();
builder.Write("Contents of cell 1 of column 2");

builder. InsertCell();
builder.Write("Contents of cell 2 of column 2");

builder. EndRow();

builder. EndTable();
```

#### Q: Aspose.Words for .NET を使用してテーブル列をブックマークするにはどうすればよいですか?

 A: Aspose.Words for .NET を使用してテーブル列にブックマークを作成するには、`StartBookmark`の方法`DocumentBuilder`オブジェクトを使用して、特定のテーブル列でブックマークを開始します。サンプルコードは次のとおりです。

```csharp
builder.StartBookmark("MyBookmark");
```

#### Q: Aspose.Words for .NET を使用してブックマークからテーブル列のコンテンツにアクセスするにはどうすればよいですか?

A: Aspose.Words for .NET を使用してブックマークからテーブル列のコンテンツにアクセスするには、ドキュメント内のすべてのブックマークをループし、ブックマークが列であるかどうかを確認し、列のインデックスを使用してそのコンテンツにアクセスします。そのコラム。サンプルコードは次のとおりです。

```csharp
foreach(Bookmark bookmark in doc.Range.Bookmarks)
{
     if (bookmark.IsColumn)
     {
         if (bookmark.BookmarkStart.GetAncestor(NodeType.Row) is Row row && bookmark.FirstColumn < row.Cells.Count)
         {
             string content = row.Cells[bookmark.FirstColumn].GetText().TrimEnd(ControlChar.CellChar);
             //列の内容を何とかしてください...
         }
     }
}
```

#### Q: 列ブックマークを使用してテーブルに作成できる列の数に制限はありますか?

A: Aspose.Words for .NET を使用して列ブックマークを持つテーブルに作成できる列の数に特に制限はありません。この制限は主に、システムで利用可能なリソースと、使用している Word ファイル形式の仕様によって異なります。ただし、最終ドキュメントのパフォーマンスと読みやすさに影響を与える可能性があるため、過度に多くの列を作成しないことをお勧めします。