---
title: 検索パターンのメタ文字
linktitle: 検索パターンのメタ文字
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET の検索パターンでメタキャラクターを使用して Word ドキュメントを操作する方法を学びます。
type: docs
weight: 10
url: /ja/net/find-and-replace-text/meta-characters-in-search-pattern/
---
この記事では、Aspose.Words for .NET ライブラリの検索パターン関数のメタ文字の使用方法を理解するために、上記の C# ソース コードを調べます。この機能を使用すると、特別なメタキャラクタを使用して、Word 文書内で高度な検索と置換を実行できます。

## 前提条件

- C# 言語の基本的な知識。
- Aspose.Words ライブラリがインストールされた .NET 開発環境。

## ステップ 1: 新しいドキュメントの作成

検索パターンでメタキャラクターの使用を開始する前に、Aspose.Words for .NET を使用して新しいドキュメントを作成する必要があります。これは、`Document`物体：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## ステップ 2: 文書にテキストを挿入する

ドキュメントを取得したら、`DocumentBuilder`物体。この例では、`Writeln`そして`Write` 2 行のテキストを挿入するメソッド:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

## ステップ 3: テキストを検索してメタキャラクターで置換する

ここで使用するのは、`Range.Replace`特殊なメタキャラクターを含む検索パターンを使用してテキストを検索および置換する関数。この例では、`&p`段落区切りを表すメタキャラクター:

```csharp
doc.Range.Replace("This is row 1&pThis is line 2", "This line is replaced");
```

## ステップ 4: 文書に改ページを挿入する

別のメタキャラクターの使用を説明するために、次のコマンドを使用して文書に改ページを挿入します。`InsertBreak`を使用したメソッド`BreakType.PageBreak`パラメーター。まずカーソルを`DocumentBuilder`文書の最後に改ページと新しいテキスト行を挿入します。

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

## ステップ 5: 別のメタキャラクターを検索して置換する

次に、次のコマンドを使用して別の検索と置換を実行します。`&m`ページ区切りを表すメタキャラクター。 「これは 1 行目&m これは 2 行目です」というフレーズを「改ページは新しいテキストに置き換えられます」に置き換えます。 :

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

## ステップ 6: 編集したドキュメントを保存する

最後に、変更したドキュメントを指定したディレクトリに保存します。`Save`方法：

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```

### Aspose.Words for .NET を使用した検索パターンのメタ文字のソース コード例

Aspose.Words for .NET の検索パターンでのメタキャラクターの使用を示す完全なサンプル ソース コードを次に示します。

```csharp

	/* meta-characters
	&p - paragraph break
	&b - section break
	&m - page break
	&l - manual line break
	*/

	//ドキュメントディレクトリへのパス。
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

この記事では、C# ソース コードを調べて、Aspose.Words for .NET の検索パターンでメタキャラクターを使用する方法を理解しました。ステップバイステップのガイドに従って、ドキュメントの作成、テキストの挿入、特殊なメタキャラクターを使用した検索と置換の実行、改ページの挿入、編集したドキュメントの保存を行いました。

### よくある質問

#### Q: Aspose.Words for .NET の検索パターンのメタ文字機能とは何ですか?

A: Aspose.Words for .NET の検索パターンのメタ文字機能を使用すると、特殊なメタ文字を使用して Word 文書内で高度な検索と置換を実行できます。これらのメタキャラクターを使用すると、検索パターン内の段落区切り、セクション区切り、ページ区切り、その他の特別な要素を表すことができます。

#### Q: Aspose.Words for .NET で新しいドキュメントを作成するにはどうすればよいですか?

 A: 検索テンプレートでメタキャラクターを使用する前に、Aspose.Words for .NET を使用して新しいドキュメントを作成する必要があります。これは、`Document`物体。新しいドキュメントを作成するサンプルコードは次のとおりです。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### Q: Aspose.Words for .NET を使用してドキュメントにテキストを挿入するにはどうすればよいですか?

 A: ドキュメントを作成したら、`DocumentBuilder`物体。この例では、`Writeln`そして`Write` 2 行のテキストを挿入するメソッド:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("This is line 1");
builder.Writeln("This is line 2");
```

#### Q: Aspose.Words for .NET を使用してドキュメント内のテキストを検索し、メタキャラクターで置換するにはどうすればよいですか?

 A: テキストを検索してメタキャラクターで置換するには、`Range.Replace`方法。この例では、`&p`段落区切りを表すメタキャラクター:

```csharp
doc.Range.Replace("This is row 1&pThis is row 2", "This row is replaced");
```

#### Q: Aspose.Words for .NET を使用してドキュメントに改ページを挿入するにはどうすればよいですか?

A: 別のメタキャラクターの使用を説明するために、次のコマンドを使用して文書に改ページを挿入します。`InsertBreak`を使用したメソッド`BreakType.PageBreak`パラメーター。まずカーソルを`DocumentBuilder`文書の最後に改ページと新しいテキスト行を挿入します。

```csharp
builder. MoveToDocumentEnd();
builder.Write("This is line 1");
builder. InsertBreak(BreakType.PageBreak);
builder.Writeln("This is line 2");
```

#### Q: Aspose.Words for .NET を使用してドキュメント内の別のメタキャラクターを検索して置換するにはどうすればよいですか?

 A: ここで、次の検索と置換を実行します。`&m`ページ区切りを表すメタキャラクター。 「これは 1 行目&m これは 2 行目です」というフレーズを「改ページは新しいテキストに置き換えられます」に置き換えます。 :

```csharp
doc.Range.Replace("This is line 1&mThis is line 2", "The page break is replaced with new text.");
```

#### Q: Aspose.Words for .NET で編集したドキュメントを保存するにはどうすればよいですか?

 A: ドキュメントに変更を加えたら、次のコマンドを使用して指定したディレクトリにドキュメントを保存できます。`Save`方法：

```csharp
doc.Save(dataDir + "SearchAndReplace.MetaCharactersInSearchPattern.docx");
```