---
title: 文字列で置換
linktitle: 文字列で置換
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書内のテキストを文字列に置き換える方法を学習します。
type: docs
weight: 10
url: /ja/net/find-and-replace-text/replace-with-string/
---
この記事では、上記の C# ソース コードを調べて、Aspose.Words for .NET ライブラリの Replace With String 関数の使用方法を理解します。この機能を使用すると、Word 文書内の特定の文字列に基づいてテキストを置換できます。

## 前提条件

- C# 言語の基本的な知識。
- Aspose.Words ライブラリがインストールされた .NET 開発環境。

## ステップ 1: 新しいドキュメントの作成

文字列置換の使用を開始する前に、Aspose.Words for .NET を使用して新しいドキュメントを作成する必要があります。これは、`Document`物体：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## ステップ 2: 文書にテキストを挿入する

ドキュメントを取得したら、`DocumentBuilder`物体。この例では、`Writeln` 「悲しい、クレイジー、悪い」というフレーズを挿入する方法:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("sad mad bad");
```

## ステップ 3: 文字列に置き換える

私たちが使用するのは、`Range.Replace`テキストを文字列に置き換えるメソッド。この例では、次のコマンドを使用して、「sad」という単語が出現するすべてを「bad」に置き換えます。`FindReplaceOptions`オプション付き`FindReplaceDirection.Forward`検索方向:

```csharp
doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## ステップ 4: 編集したドキュメントを保存する

最後に、変更したドキュメントを指定したディレクトリに保存します。`Save`方法：

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
```

### Aspose.Words for .NET を使用した Replace With String のソース コード例

Aspose.Words for .NET での文字列への置換の使用法を示す完全なサンプル ソース コードを次に示します。

```csharp

	//ドキュメントディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.Writeln("sad mad bad");

	doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));

	doc.Save(dataDir + "FindAndReplace.ReplaceWithString.docx");
  
```

## 結論

この記事では、C# ソース コードを調べて、Aspose.Words for .NET の Replace With String 関数の使用方法を理解しました。ステップバイステップのガイドに従って、ドキュメントを作成し、テキストを挿入し、文字列に置き換えて、変更したドキュメントを保存しました。

### よくある質問

#### Q: Aspose.Words for .NET の「文字列で置換」機能とは何ですか?

A: Aspose.Words for .NET の「文字列で置換」機能を使用すると、Word 文書内の特定の文字列に基づいてテキストを置換できます。これにより、特定の文字列の出現を検索し、それらを別の指定された文字列に置き換えることができます。

#### Q: Aspose.Words for .NET を使用して新しいドキュメントを作成するにはどうすればよいですか?

 A: Aspose.Words for .NET を使用して新しいドキュメントを作成するには、`Document`物体。新しいドキュメントを作成する C# コードの例を次に示します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

#### Q: Aspose.Words for .NET を使用してドキュメントにテキストを挿入するにはどうすればよいですか?

 A: ドキュメントを作成したら、`DocumentBuilder`物体。 Aspose.Words for .NET では、`DocumentBuilder`別の場所にテキストを挿入するクラス。たとえば、次のように使用できます。`Writeln`新しい行にテキストを挿入するメソッド。以下に例を示します。

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("sad mad bad");
```

#### Q: Aspose.Words for .NET でテキストを文字列に置換するにはどうすればよいですか?

 A: Aspose.Words for .NET でテキストを文字列に置換するには、`Range.Replace`メソッドを使用して、置換する文字列と置換後の文字列を指定します。このメソッドは、単純なテキストの一致を実行し、指定された文字列のすべての出現を置き換えます。以下に例を示します。

```csharp
doc.Range.Replace("sad", "bad", new FindReplaceOptions(FindReplaceDirection.Forward));
```

#### Q: Aspose.Words for .NET の「文字列で置換」機能を使用して、大文字と小文字を区別するテキスト置換を実行できますか?

A: はい、デフォルトでは、Aspose.Words for .NET の「文字列で置換」関数は大文字と小文字を区別します。これは、指定された文字列と大文字小文字の区別が完全に一致するテキストのみを置換することを意味します。大文字と小文字を区別しない置換を実行する場合は、置換するテキストと置換文字列を大文字と小文字が同じになるように変更するか、正規表現などの他の手法を使用できます。

#### Q: Aspose.Words for .NET の「文字列で置換」機能を使用して、ドキュメント内で複数出現する文字列を置換できますか?

 A: はい、Aspose.Words for .NET の「文字列で置換」機能を使用すると、ドキュメント内で複数出現する文字列を置換できます。の`Range.Replace`このメソッドは、ドキュメントのコンテンツ内に出現する指定された文字列をすべて置き換えます。

#### Q: Aspose.Words for .NET の「文字列で置換」機能を使用する場合、制限や考慮事項はありますか?

A: Aspose.Words for .NET で「文字列に置換」機能を使用する場合は、コンテキストを認識し、意図した場所にのみ置換が適用されるようにすることが重要です。検索文字列が、他の単語内や特殊な書式設定の一部など、不要な場所に表示されないように注意してください。さらに、大きな文書や頻繁な置換を伴うワード処理を行う場合のパフォーマンスへの影響を考慮してください。

#### Q: Aspose.Words for .NET の「文字列で置換」機能を使用して、異なる長さの文字列を置換できますか?

A: はい、Aspose.Words for .NET の「文字列で置換」機能を使用して、異なる長さの文字列を置換できます。置換文字列は任意の長さにすることができ、検索文字列の完全一致を置換します。新しい文字列の長さに合わせてドキュメントが調整されます。