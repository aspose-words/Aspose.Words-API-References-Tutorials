---
title: 文字列で置換
linktitle: 文字列で置換
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内のテキストを文字列に置き換える方法を学習します。
type: docs
weight: 10
url: /ja/net/find-and-replace-text/replace-with-string/
---
この記事では、上記の C# ソース コードを調べて、Aspose.Words for .NET ライブラリの Replace With String 関数の使用方法を理解します。この機能を使用すると、Word 文書内の特定の文字列に基づいてテキストの置換を実行できます。

## 前提条件

- C# 言語に関する基本的な知識。
- Aspose.Words ライブラリがインストールされた .NET 開発環境。

## ステップ1: 新しいドキュメントを作成する

文字列置換を使用する前に、Aspose.Words for .NETを使用して新しいドキュメントを作成する必要があります。これは、`Document`物体：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## ステップ2: 文書にテキストを挿入する

文書ができたら、`DocumentBuilder`オブジェクトです。例では、`Writeln` 「sad crazy bad」というフレーズを挿入する方法:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("sad mad bad");
```

## ステップ3: 文字列に置き換える

私たちは`Range.Replace`テキストを文字列に置き換えるメソッド。この例では、"sad"という単語をすべて"bad"に置き換えます。`FindReplaceOptions`オプション`FindReplaceDirection.Forward`検索方向:

```csharp
doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## ステップ4: 編集した文書を保存する

最後に、変更したドキュメントを指定されたディレクトリに保存します。`Save`方法：

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
```

### Aspose.Words for .NET を使用した文字列置換のサンプル ソース コード

以下は、Aspose.Words for .NET を使用して文字列に置き換える方法を示す完全なサンプル ソース コードです。

```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("sad mad bad");

	doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));

	doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
  
```

## 結論

この記事では、C# ソース コードを調べて、Aspose.Words for .NET の文字列置換機能の使用方法を理解しました。ドキュメントの作成、テキストの挿入、文字列への置換、変更したドキュメントの保存という手順をステップ バイ ステップで説明しました。

### よくある質問

#### Q: Aspose.Words for .NET の「文字列で置換」機能とは何ですか?

A: Aspose.Words for .NET の「文字列で置換」機能を使用すると、Word 文書内の特定の文字列に基づいてテキスト置換を実行できます。特定の文字列の出現箇所を検索し、別の指定した文字列に置換できます。

#### Q: Aspose.Words for .NET を使用して新しいドキュメントを作成するにはどうすればよいですか?

 A: Aspose.Words for .NETを使用して新しいドキュメントを作成するには、`Document`オブジェクト。新しいドキュメントを作成する C# コードの例を次に示します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

#### Q: Aspose.Words for .NET を使用してドキュメントにテキストを挿入するにはどうすればよいですか?

 A: 文書を作成したら、`DocumentBuilder`オブジェクト。Aspose.Words for .NETでは、`DocumentBuilder`クラスを使用して、さまざまな場所にテキストを挿入できます。たとえば、`Writeln`新しい行にテキストを挿入するメソッド。次に例を示します。

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("sad mad bad");
```

#### Q: Aspose.Words for .NET で文字列によるテキスト置換を実行するにはどうすればよいですか?

 A: Aspose.Words for .NETで文字列によるテキスト置換を実行するには、`Range.Replace`メソッドを使用して、置換する文字列と置換後の文字列を指定します。このメソッドは単純なテキスト一致を実行し、指定された文字列のすべての出現箇所を置き換えます。次に例を示します。

```csharp
doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));
```

#### Q: Aspose.Words for .NET の「文字列で置換」関数を使用して、大文字と小文字を区別したテキスト置換を実行できますか?

A: はい、デフォルトでは、Aspose.Words for .NET の「文字列で置換」関数は大文字と小文字を区別します。つまり、大文字と小文字の点で指定された文字列と完全に一致するテキストのみが置換されます。大文字と小文字を区別しない置換を実行する場合は、置換するテキストと置換文字列の大文字と小文字が同じになるように変更するか、正規表現などの他の手法を使用することができます。

#### Q: Aspose.Words for .NET の「文字列で置換」機能を使用して、ドキュメント内の文字列の複数の出現箇所を置換できますか?

 A: はい、Aspose.Words for .NETの「文字列で置換」機能を使用して、ドキュメント内の文字列の複数の出現箇所を置換できます。`Range.Replace`メソッドは、ドキュメントのコンテンツ内の指定された文字列のすべての出現を置き換えます。

#### Q: Aspose.Words for .NET で「文字列に置換」機能を使用する場合、制限や考慮事項はありますか?

A: Aspose.Words for .NET で「文字列で置換」機能を使用する場合は、コンテキストに注意し、置換が意図した場所にのみ適用されるようにすることが重要です。検索文字列が、他の単語内や特殊な書式設定の一部など、不要な場所に表示されないようにしてください。また、大きなドキュメントや頻繁な置換で Words Processing を実行する場合は、パフォーマンスへの影響を考慮してください。

#### Q: Aspose.Words for .NET の「文字列に置換」機能を使用して、長さの異なる文字列を置換できますか?

A: はい、Aspose.Words for .NET の「文字列で置換」機能を使用して、異なる長さの文字列を置換できます。置換文字列は任意の長さにすることができ、検索文字列と完全に一致する文字列を置換します。ドキュメントは、新しい文字列の長さに合わせて調整されます。