---
title: Word文書にブックマークを作成する
linktitle: Word文書にブックマークを作成する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書でブックマークを作成し、PDF でブックマークのプレビュー レベルを指定する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-bookmarks/create-bookmark/
---

この記事では、上記の C# ソース コードを調べて、Aspose.Words for .NET ライブラリの Create Bookmark 関数の使用方法を理解します。この機能を使用すると、ドキュメント内にブックマークを作成し、出力 PDF ファイル内でブックマークのプレビュー レベルを指定できます。

## 前提条件

- C# 言語の基本的な知識。
- Aspose.Words ライブラリがインストールされた .NET 開発環境。

## ステップ 1: ドキュメントとジェネレーターの作成

ブックマークを作成する前に、`Document`そして`DocumentBuilder`オブジェクト:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ 2: メインブックマークの作成

私たちが使用するのは、`StartBookmark`メインブックマークを開始するメソッドと`EndBookmark`終わらせる方法。その間に、テキストやその他のブックマークを追加できます。

```csharp
builder. StartBookmark("My Bookmark");
builder.Writeln("Text inside a bookmark.");

//ここにブックマークやテキストを追加します。

builder. EndBookmark("My Bookmark");
```

## ステップ 3: ネストされたブックマークの作成

メインブックマーク内にネストされたブックマークを作成することもできます。私たちも同じものを使っています`StartBookmark`そして`EndBookmark`ネストされたブックマークを作成および終了するメソッド:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

## ステップ 4: 出力 PDF ファイルのブックマークのプレビュー レベルを指定する

私たちが使用するのは、`PdfSaveOptions`オブジェクトを使用して、出力 PDF ファイルのブックマークのプレビュー レベルを指定します。私たちが使用するのは、`BookmarksOutlineLevels`財産

  メインブックマークとネストされたブックマークをそれぞれのレベルで追加するには、次のようにします。

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
```

### Aspose.Words for .NET を使用したブックマークの作成のソース コード例

Aspose.Words for .NET を使用してブックマークを作成する方法を示す完全なソース コード例を次に示します。

```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.StartBookmark("My Bookmark");
	builder.Writeln("Text inside a bookmark.");

	builder.StartBookmark("Nested Bookmark");
	builder.Writeln("Text inside a NestedBookmark.");
	builder.EndBookmark("Nested Bookmark");

	builder.Writeln("Text after Nested Bookmark.");
	builder.EndBookmark("My Bookmark");

	PdfSaveOptions options = new PdfSaveOptions();
	options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
	options.OutlineOptions.BookmarksOutlineLevels.Add("Nested Bookmark", 2);

	doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
  
```

## 結論

この記事では、C# ソース コードを調べて、Aspose.Words for .NET のブックマークの作成機能の使用方法を理解しました。ステップバイステップのガイドに従って、文書内にブックマークを作成し、出力 PDF ファイル内でブックマークのプレビュー レベルを指定しました。

### よくある質問

#### Q: Aspose.Words for .NET の「ブックマークの作成」機能を使用するための前提条件は何ですか?

A: Aspose.Words for .NET の「ブックマークの作成」機能を使用するには、C# 言語の基本的な知識が必要です。 Aspose.Words ライブラリがインストールされた .NET 開発環境も必要です。

#### Q: Aspose.Words for .NET でドキュメントを作成するにはどうすればよいですか?

 A: Aspose.Words for .NET でドキュメントを作成するには、`Document`クラス。サンプルコードは次のとおりです。

```csharp
Document doc = new Document();
```

#### Q: Aspose.Words for .NET を使用してドキュメント内にマスター ブックマークを作成するにはどうすればよいですか?

 A: Aspose.Words for .NET を使用してドキュメントにメイン ブックマークを作成するには、`StartBookmark`メソッドを使用してブックマークを開始し、内部にテキストまたは他のブックマークを追加してから、` EndBookmark`それを終わらせるために。サンプルコードは次のとおりです。

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### Q: Aspose.Words for .NET を使用してメイン ブックマーク内にネストされたブックマークを作成するにはどうすればよいですか?

 A: Aspose.Words for .NET を使用してメイン ブックマーク内にネストされたブックマークを作成するには、同じものを使用できます。`StartBookmark`そして`EndBookmark`ネストされたブックマークを開始および終了するメソッド。サンプルコードは次のとおりです。

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

#### Q: Aspose.Words for .NET を使用して出力 PDF のブックマーク プレビュー レベルを指定するにはどうすればよいですか?

 A: Aspose.Words for .NET を使用して出力 PDF のブックマーク プレビュー レベルを指定するには、`PdfSaveOptions`クラスと`BookmarksOutlineLevels`財産。メインブックマークとネストされたブックマークをそれぞれのレベルで追加できます。サンプルコードは次のとおりです。

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
```

#### Q: Aspose.Words for .NET を使用してブックマークを作成した後にドキュメントを保存するにはどうすればよいですか?

 A: Aspose.Words for .NET を使用してブックマークを作成した後にドキュメントを保存するには、`Save`の方法`Document`宛先ファイルのパスを指定するオブジェクト。サンプルコードは次のとおりです。

```csharp
doc.Save("path/to/your/output-document.docx");
```

#### Q: Aspose.Words for .NET を使用して出力 PDF のブックマーク プレビュー レベルを指定するにはどうすればよいですか?

 A: Aspose.Words for .NET を使用して出力 PDF のブックマーク プレビュー レベルを指定するには、`PdfSaveOptions`クラスと`BookmarksOutlineLevels`財産。メインブックマークとネストされたブックマークをそれぞれのレベルで追加できます。サンプルコードは次のとおりです。

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save("path/to/your/output-pdf-file.pdf", options);
```

#### Q: Aspose.Words for .NET を使用してメイン ブックマーク内にネストされたブックマークを作成するにはどうすればよいですか?

 A: Aspose.Words for .NET を使用してメイン ブックマーク内にネストされたブックマークを作成するには、同じものを使用できます。`StartBookmark`そして`EndBookmark`ネストされたブックマークを開始および終了するメソッド。を呼び出すときは、必ず親ブックマークをパラメータとして指定してください。`StartBookmark`方法。サンプルコードは次のとおりです。

```csharp
builder.StartBookmark("Main bookmark");
builder.Writeln("Text inside main bookmark.");

builder.StartBookmark("Nested bookmark 1");
builder.Writeln("Text inside first nested bookmark.");
builder.EndBookmark("Nested bookmark 1");

builder.StartBookmark("Nested bookmark 2");
builder.Writeln("Text inside second nested bookmark.");
builder.EndBookmark("Nested bookmark 2");

builder.EndBookmark("Main bookmark");
```

#### Q: Aspose.Words for .NET を使用してブックマーク内にテキストを追加するにはどうすればよいですか?

 A: Aspose.Words for .NET を使用してブックマーク内にテキストを追加するには、`Write`の方法`DocumentBuilder`追加するテキストを指定するオブジェクト。サンプルコードは次のとおりです。

```csharp
builder.StartBookmark("My Bookmark");
builder.Write("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### Q: Aspose.Words for .NET を使用してドキュメント内にマスター ブックマークを作成するにはどうすればよいですか?

 A: Aspose.Words for .NET を使用してドキュメントにメイン ブックマークを作成するには、`StartBookmark`ブックマークを開始するメソッドと`EndBookmark`終わらせる方法。サンプルコードは次のとおりです。

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```