---
title: Word文書にブックマークを作成する
linktitle: Word文書にブックマークを作成する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書にブックマークを作成し、PDF でブックマークのプレビュー レベルを指定する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-bookmarks/create-bookmark/
---

この記事では、上記の C# ソース コードを調べて、Aspose.Words for .NET ライブラリの Create Bookmark 関数の使用方法を理解します。この機能を使用すると、ドキュメントにブックマークを作成し、出力 PDF ファイルでブックマークのプレビュー レベルを指定できます。

## 前提条件

- C# 言語に関する基本的な知識。
- Aspose.Words ライブラリがインストールされた .NET 開発環境。

## ステップ1: ドキュメントとジェネレーターの作成

ブックマークを作成する前に、`Document`そして`DocumentBuilder`オブジェクト:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ2: メインブックマークの作成

私たちは`StartBookmark`メインブックマークを開始する方法と`EndBookmark`メソッドを使用して終了します。その間に、テキストやその他のブックマークを追加できます。

```csharp
builder. StartBookmark("My Bookmark");
builder.Writeln("Text inside a bookmark.");

//ここにブックマークまたはテキストを追加します。

builder. EndBookmark("My Bookmark");
```

## ステップ3: ネストされたブックマークを作成する

メインのブックマークの中にネストされたブックマークを作成することもできます。`StartBookmark`そして`EndBookmark`ネストされたブックマークを作成および終了するメソッド:

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

## ステップ4: 出力PDFファイルでブックマークのプレビューレベルを指定する

私たちは`PdfSaveOptions`オブジェクトを使用して、出力PDFファイルのブックマークプレビューレベルを指定します。`BookmarksOutlineLevels`財産

  メインのブックマークとネストされたブックマークをそれぞれのレベルとともに追加するには:

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save(dataDir + "WorkingWithBookmarks.CreateBookmark.pdf", options);
```

### Aspose.Words for .NET を使用してブックマークを作成するためのサンプル ソース コード

Aspose.Words for .NET を使用してブックマークを作成する方法を示す完全なサンプル ソース コードを以下に示します。

```csharp

	//ドキュメント ディレクトリへのパス。
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

この記事では、C# ソース コードを調べて、Aspose.Words for .NET のブックマーク作成機能の使用方法を理解しました。ドキュメントにブックマークを作成し、出力 PDF ファイルでブックマークのプレビュー レベルを指定する手順ガイドに従いました。

### よくある質問

#### Q: Aspose.Words for .NET の「ブックマークの作成」機能を使用するための前提条件は何ですか?

A: Aspose.Words for .NET の「ブックマークの作成」機能を使用するには、C# 言語の基本的な知識が必要です。また、Aspose.Words ライブラリがインストールされた .NET 開発環境も必要です。

#### Q: Aspose.Words for .NET でドキュメントを作成するにはどうすればよいですか?

 A: Aspose.Words for .NETでドキュメントを作成するには、`Document`クラス。サンプルコードは次のとおりです。

```csharp
Document doc = new Document();
```

#### Q: Aspose.Words for .NET を使用してドキュメントにマスター ブックマークを作成するにはどうすればよいですか?

 A: Aspose.Words for .NETを使用してドキュメントにメインブックマークを作成するには、`StartBookmark`ブックマークを開始する方法、テキストや他のブックマークを内部に追加し、` EndBookmark`終了します。サンプルコードは次のとおりです。

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### Q: Aspose.Words for .NET を使用してメイン ブックマーク内にネストされたブックマークを作成するにはどうすればよいですか?

 A: Aspose.Words for .NETを使用してメインブックマーク内にネストされたブックマークを作成するには、同じ`StartBookmark`そして`EndBookmark`ネストされたブックマークを開始および終了するメソッド。サンプル コードは次のとおりです。

```csharp
builder.StartBookmark("Embedded bookmark");
builder.Writeln("Text inside nested bookmark.");
builder.EndBookmark("Embedded bookmark");
```

#### Q: Aspose.Words for .NET を使用して出力 PDF でブックマークのプレビュー レベルを指定する方法を教えてください。

 A: Aspose.Words for .NETを使用して出力PDFのブックマークプレビューレベルを指定するには、`PdfSaveOptions`クラスと`BookmarksOutlineLevels`プロパティ。それぞれのレベルでメイン ブックマークとネストされたブックマークを追加できます。サンプル コードは次のとおりです。

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
```

#### Q: Aspose.Words for .NET を使用してブックマークを作成した後、ドキュメントを保存するにはどうすればよいですか?

 A: Aspose.Words for .NETを使用してブックマークを作成した後にドキュメントを保存するには、`Save`方法の`Document`宛先ファイル パスを指定するオブジェクト。サンプル コードは次のとおりです。

```csharp
doc.Save("path/to/your/output-document.docx");
```

#### Q: Aspose.Words for .NET を使用して出力 PDF でブックマークのプレビュー レベルを指定する方法を教えてください。

 A: Aspose.Words for .NETを使用して出力PDFのブックマークプレビューレベルを指定するには、`PdfSaveOptions`クラスと`BookmarksOutlineLevels`プロパティ。それぞれのレベルでメイン ブックマークとネストされたブックマークを追加できます。サンプル コードは次のとおりです。

```csharp
PdfSaveOptions options = new PdfSaveOptions();
options.OutlineOptions.BookmarksOutlineLevels.Add("My Bookmark", 1);
options.OutlineOptions.BookmarksOutlineLevels.Add("Embedded bookmark", 2);
doc.Save("path/to/your/output-pdf-file.pdf", options);
```

#### Q: Aspose.Words for .NET を使用してメイン ブックマーク内にネストされたブックマークを作成するにはどうすればよいですか?

 A: Aspose.Words for .NETを使用してメインブックマーク内にネストされたブックマークを作成するには、同じ`StartBookmark`そして`EndBookmark`ネストされたブックマークを開始および終了するメソッド。呼び出すときは、必ず親ブックマークをパラメータとして指定してください。`StartBookmark`メソッド。サンプルコードは次のとおりです。

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

 A: Aspose.Words for .NETを使用してブックマーク内にテキストを追加するには、`Write`方法の`DocumentBuilder`追加するテキストを指定するオブジェクト。サンプルコードは次のとおりです。

```csharp
builder.StartBookmark("My Bookmark");
builder.Write("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```

#### Q: Aspose.Words for .NET を使用してドキュメントにマスター ブックマークを作成するにはどうすればよいですか?

 A: Aspose.Words for .NETを使用してドキュメントにメインブックマークを作成するには、`StartBookmark`ブックマークを開始する方法と`EndBookmark`終了する方法です。サンプルコードは次のとおりです。

```csharp
builder.StartBookmark("My Bookmark");
builder.Writeln("Text inside bookmark.");
builder.EndBookmark("My Bookmark");
```