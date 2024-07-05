---
title: Word での簡単なテキスト検索と置換
linktitle: Word での簡単なテキスト検索と置換
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書内で簡単なテキストの検索と置換を実行する方法を学習します。
type: docs
weight: 10
url: /ja/net/find-and-replace-text/simple-find-replace/
---
この記事では、上記の C# ソース コードを調べて、Aspose.Words for .NET ライブラリの Word でシンプルなテキストの検索と置換を使用する方法を理解します。この機能を使用すると、Word 文書内で特定の文字列を検索し、それを別の文字列に置き換えることで、シンプルなテキスト置換を実行できます。

## 前提条件

- C# 言語に関する基本的な知識。
- Aspose.Words ライブラリがインストールされた .NET 開発環境。

## ステップ1: 新しいドキュメントを作成する

簡単な検索と置換を使用する前に、Aspose.Words for .NETを使用して新しいドキュメントを作成する必要があります。これは、`Document`物体：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## ステップ2: 文書にテキストを挿入する

文書ができたら、`DocumentBuilder`オブジェクトです。例では、`Writeln` 「Hello」というフレーズを挿入する方法_CustomerName_、":

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello _CustomerName_,");
```

## ステップ3: 簡単なテキストの置換

私たちは`Range.Replace`単純なテキスト置換を実行するメソッド。この例では、文字列「_ClientName_ 「ジェームズ・ボンド」と`FindReplaceOptions`オプション`FindReplaceDirection.Forward`検索方向:

```csharp
doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## ステップ4: 編集した文書を保存する

最後に、変更したドキュメントを指定されたディレクトリに保存します。`Save`方法：

```csharp
doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");
```

### Aspose.Words for .NET を使用したシンプルな検索置換のサンプル ソース コード

以下は、Aspose.Words for .NET を使用した簡単な検索と置換の使用方法を示す完全なサンプル ソース コードです。

```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Writeln("Hello _CustomerName_,");
	Console.WriteLine("Original document text: " + doc.Range.Text);

	doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));

	Console.WriteLine("Document text after replace: " + doc.Range.Text);

	//変更したドキュメントを保存する
	doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");

```

## 結論

この記事では、C# ソース コードを調べて、Aspose.Words for .NET の Simple Find Replace 機能の使用方法を理解しました。ドキュメントの作成、テキストの挿入、簡単なテキスト置換の実行、編集したドキュメントの保存について、ステップ バイ ステップ ガイドに従って説明しました。

### よくある質問

#### Q: Aspose.Words for .NET のシンプルなテキスト検索と置換機能とは何ですか?

A: Aspose.Words for .NET のシンプルなテキスト検索と置換機能を使用すると、Word 文書内でシンプルなテキスト置換を実行できます。特定の文字列を検索し、別の文字列に置き換えることができます。これは、名前、日付、その他の情報を置き換えるなど、文書全体に変更を加えたい場合に便利です。

#### Q: Aspose.Words for .NET で新しいドキュメントを作成するにはどうすればよいですか?

 A: シンプルテキスト検索と置換機能を使用する前に、Aspose.Words for .NETを使用して新しいドキュメントを作成する必要があります。これは、`Document`オブジェクト。新しいドキュメントを作成するサンプル コードは次のとおりです。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### Q: Aspose.Words for .NET を使用してドキュメントにテキストを挿入するにはどうすればよいですか?

 A: 文書を作成したら、`DocumentBuilder`オブジェクトです。例では、`Writeln` 「Hello」というフレーズを挿入する方法_CustomerName_:":

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello _CustomerName_:");
```

#### Q: Aspose.Words for .NET を使用してドキュメント内で簡単なテキスト置換を実行するにはどうすればよいですか?

 A: 単純なテキスト置換を実行するには、`Range.Replace`メソッド。例では、文字列「_ClientName_ 「ジェームズ・ボンド」と`FindReplaceOptions`オプション`FindReplaceDirection.Forward`検索方向:

```csharp
doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));
```

#### Q: Aspose.Words for .NET で編集したドキュメントを保存するにはどうすればよいですか?

 A: テキストの置換が完了したら、変更した文書を指定されたディレクトリに保存することができます。`Save`方法：

```csharp
doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");
```