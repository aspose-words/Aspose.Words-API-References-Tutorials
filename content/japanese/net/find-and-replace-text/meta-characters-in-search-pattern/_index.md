---
title: 検索パターンのメタ文字
linktitle: 検索パターンのメタ文字
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して検索パターンでメタ文字を使用し、Word 文書を操作する方法を学習します。
type: docs
weight: 10
url: /ja/net/find-and-replace-text/meta-characters-in-search-pattern/
---
この記事では、上記の C# ソース コードを調べて、Aspose.Words for .NET ライブラリの Meta Characters In Search Pattern 関数の使用方法を理解します。この機能を使用すると、特殊なメタ文字を使用して、Word 文書で高度な検索と置換を実行できます。

## 前提条件

- C# 言語に関する基本的な知識。
- Aspose.Words ライブラリがインストールされた .NET 開発環境。

## ステップ1: 新しいドキュメントを作成する

検索パターンでメタ文字を使用する前に、Aspose.Words for .NETを使用して新しいドキュメントを作成する必要があります。これは、`Document`物体：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## ステップ2: 文書にテキストを挿入する

文書ができたら、`DocumentBuilder`オブジェクトです。例では、`Writeln`そして`Write` 2行のテキストを挿入する方法:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

## ステップ3: メタ文字を含むテキストを検索して置換する

ここで、`Range.Replace`関数は、特殊なメタ文字を含む検索パターンを使用してテキストを検索および置換します。例では、「これは行 1 です&pこれは行 2 です」というフレーズを「この行は置き換えられます」に置き換えます。`&p`段落区切りを表すメタ文字:

```csharp
doc.Range.Replace("This is row 1&pThis is line 2", "This line is replaced");
```

## ステップ4: 文書に改ページを挿入する

別のメタ文字の使用法を説明するために、`InsertBreak`方法`BreakType.PageBreak`パラメータを設定します。まずカーソルを`DocumentBuilder`文書の末尾に、改ページと新しいテキスト行を挿入します。

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

## ステップ5: 別のメタ文字を検索して置換する

ここで、別の検索と置換を実行します。`&m`改ページを表すメタ文字。「これは行 1 です。これは行 2 です」というフレーズを「改ページは新しいテキストに置き換えられます」に置き換えます。

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

## ステップ6: 編集した文書を保存する

最後に、変更したドキュメントを指定されたディレクトリに保存します。`Save`方法：

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```

### Aspose.Words for .NET を使用した検索パターンのメタ文字のサンプル ソース コード

以下は、Aspose.Words for .NET を使用した検索パターンでのメタ文字の使用を示す完全なサンプル ソース コードです。

```csharp

	/* meta-characters
	&p - paragraph break
	&b - section break
	&m - page break
	&l - manual line break
	*/

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("This is Line 1");
	builder.Writeln("This is Line 2");

	doc.Range.Replace("This is Line 1&pThis is Line 2", "This is replaced line");

	builder.MoveToDocumentEnd();
	builder.Write("This is Line 1");
	builder.InsertBreak(BreakType.PageBreak);
	builder.Writeln("This is Line 2");

	doc.Range.Replace("This is Line 1&mThis is Line 2", "Page break is replaced with new text.");

	doc.Save(dataDir + "FindAndReplace.MetaCharactersInSearchPattern.docx");

```

## 結論

この記事では、C# ソース コードを調べて、Aspose.Words for .NET の検索パターンでメタ文字を使用する方法を理解しました。ドキュメントの作成、テキストの挿入、特殊なメタ文字を使用した検索と置換の実行、改ページの挿入、編集したドキュメントの保存を行う手順をステップ バイ ステップで説明しました。

### よくある質問

#### Q: Aspose.Words for .NET の検索パターンのメタ文字機能とは何ですか?

A: Aspose.Words for .NET の検索パターンのメタ文字機能を使用すると、特殊なメタ文字を使用して、Word 文書内で高度な検索や置換を実行できます。これらのメタ文字を使用すると、検索パターン内で段落区切り、セクション区切り、ページ区切り、その他の特殊要素を表すことができます。

#### Q: Aspose.Words for .NET で新しいドキュメントを作成するにはどうすればよいですか?

 A: 検索テンプレートでメタ文字を使用する前に、Aspose.Words for .NETを使用して新しいドキュメントを作成する必要があります。これは、`Document`オブジェクト。新しいドキュメントを作成するサンプル コードは次のとおりです。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### Q: Aspose.Words for .NET を使用してドキュメントにテキストを挿入するにはどうすればよいですか?

 A: 文書を作成したら、`DocumentBuilder`オブジェクトです。例では、`Writeln`そして`Write` 2行のテキストを挿入する方法:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

#### Q: Aspose.Words for .NET を使用してドキュメント内のメタ文字を含むテキストを検索および置換するにはどうすればよいですか?

 A: メタ文字を含むテキストを検索して置換するには、`Range.Replace`方法。例では、「これは1行目です&pこれは2行目です」というフレーズを「この行は置き換えられます」に置き換えます。`&p`段落区切りを表すメタ文字:

```csharp
doc.Range.Replace("This is row 1&pThis is row 2", "This row is replaced");
```

#### Q: Aspose.Words for .NET を使用してドキュメントに改ページを挿入するにはどうすればよいですか?

A: 別のメタ文字の使用法を説明するために、`InsertBreak`方法`BreakType.PageBreak`パラメータを設定します。まずカーソルを`DocumentBuilder`文書の末尾に、改ページと新しいテキスト行を挿入します。

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

#### Q: Aspose.Words for .NET を使用してドキュメント内の別のメタ文字を検索し、置換するにはどうすればよいですか?

 A: ここでもう一度検索と置換を実行します。`&m`改ページを表すメタ文字。「これは行 1 です。これは行 2 です」というフレーズを「改ページは新しいテキストに置き換えられます」に置き換えます。

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

#### Q: Aspose.Words for .NET で編集したドキュメントを保存するにはどうすればよいですか?

 A: ドキュメントに変更を加えたら、`Save`方法：

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```