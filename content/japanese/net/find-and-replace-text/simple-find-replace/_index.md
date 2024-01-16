---
title: Word での単純なテキストの検索と置換
linktitle: Word での単純なテキストの検索と置換
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内で単純なテキストの検索と置換を実行する方法を学びます。
type: docs
weight: 10
url: /ja/net/find-and-replace-text/simple-find-replace/
---
この記事では、上記の C# ソース コードを調べて、Word での単純なテキストの検索と置換、Aspose.Words for .NET ライブラリの使用方法を理解します。この機能を使用すると、Word 文書内で特定の文字列を検索し、別の文字列に置換することで、単純なテキスト置換を実行できます。

## 前提条件

- C# 言語の基本的な知識。
- Aspose.Words ライブラリがインストールされた .NET 開発環境。

## ステップ 1: 新しいドキュメントの作成

単純な検索と置換を使用する前に、Aspose.Words for .NET を使用して新しいドキュメントを作成する必要があります。これは、`Document`物体：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## ステップ 2: 文書にテキストを挿入する

ドキュメントを取得したら、`DocumentBuilder`物体。この例では、`Writeln` 「こんにちは」というフレーズを挿入するメソッド_CustomerName_、":

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello _CustomerName_,");
```

## ステップ 3: 単純なテキストの置換

私たちが使用するのは、`Range.Replace`単純なテキスト置換を実行するメソッド。この例では、文字列 " の出現箇所をすべて置き換えます。_ClientName_を使用して「ジェームズ・ボンド」と`FindReplaceOptions`オプション付き`FindReplaceDirection.Forward`検索方向:

```csharp
doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## ステップ 4: 編集したドキュメントを保存する

最後に、変更したドキュメントを指定したディレクトリに保存します。`Save`方法：

```csharp
doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");
```

### Aspose.Words for .NET を使用した簡易検索置換のソース コード例

Aspose.Words for .NET による単純な検索と置換の使用法を示す完全なソース コード例を次に示します。

```csharp

	//ドキュメントディレクトリへのパス。
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

この記事では、C# ソース コードを調べて、Aspose.Words for .NET の Simple Find Replace 関数の使用方法を理解しました。ステップバイステップのガイドに従って、ドキュメントを作成し、テキストを挿入し、単純なテキスト置換を実行し、編集したドキュメントを保存しました。

### よくある質問

#### Q: Aspose.Words for .NET の単純なテキストの検索と置換機能とは何ですか?

A: Aspose.Words for .NET の単純なテキスト検索と置換機能を使用すると、Word 文書内で単純なテキスト置換を実行できます。特定の文字列を検索し、別の文字列に置換できます。これは、名前、日付、その他の情報を置き換えるなど、ドキュメントに全体的な変更を加える場合に便利です。

#### Q: Aspose.Words for .NET で新しいドキュメントを作成するにはどうすればよいですか?

 A: 単純なテキストの検索と置換機能を使用する前に、Aspose.Words for .NET を使用して新しいドキュメントを作成する必要があります。これは、`Document`物体。新しいドキュメントを作成するサンプルコードは次のとおりです。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### Q: Aspose.Words for .NET を使用してドキュメントにテキストを挿入するにはどうすればよいですか?

 A: ドキュメントを作成したら、`DocumentBuilder`物体。この例では、`Writeln` 「こんにちは」というフレーズを挿入するメソッド_CustomerName_:":

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello _CustomerName_:");
```

#### Q: Aspose.Words for .NET を使用してドキュメント内の単純なテキスト置換を実行するにはどうすればよいですか?

 A: 単純なテキスト置換を実行するには、`Range.Replace`方法。この例では、文字列 " の出現箇所をすべて置き換えます。_ClientName_を使用して「ジェームズ・ボンド」と`FindReplaceOptions`オプション付き`FindReplaceDirection.Forward`検索方向:

```csharp
doc.Range.Replace("_CustomerName_", "James Bond", new FindReplaceOptions(FindReplaceDirection.Forward));
```

#### Q: Aspose.Words for .NET で編集したドキュメントを保存するにはどうすればよいですか?

 A: テキストの置換を完了したら、次のコマンドを使用して、変更したドキュメントを指定したディレクトリに保存できます。`Save`方法：

```csharp
doc.Save(dataDir + "FindAndReplace.SimpleFindReplace.docx");
```