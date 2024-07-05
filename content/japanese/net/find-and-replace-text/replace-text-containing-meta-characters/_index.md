---
title: メタ文字を含むテキストを置換する
linktitle: メタ文字を含むテキストを置換する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書内のメタ文字を含むテキストを置換する方法を学習します。
type: docs
weight: 10
url: /ja/net/find-and-replace-text/replace-text-containing-meta-characters/
---
この記事では、上記の C# ソース コードを調べて、Aspose.Words for .NET ライブラリの Word のメタ文字を含むテキストの置換機能の使用方法を理解します。この機能を使用すると、特定のメタ文字を含むドキュメント内のテキストの一部を置換できます。

## 前提条件

- C# 言語に関する基本的な知識。
- Aspose.Words ライブラリがインストールされた .NET 開発環境。

## ステップ1: 新しいドキュメントを作成する

メタ文字テキスト置換を使用する前に、Aspose.Words for .NETを使用して新しいドキュメントを作成する必要があります。これは、`Document`物体：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## ステップ2: 文書にテキストを挿入する

文書ができたら、`DocumentBuilder`オブジェクトです。例では、`Writeln`複数の段落のテキストを異なるセクションに挿入する方法:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Arial";
builder.Writeln("First section");
builder.Writeln("1st paragraph");
builder.Writeln("2nd paragraph");
builder. Writen("{insert-section}");
builder.Writeln("Second section");
builder.Writeln("1st paragraph");
```

## ステップ3: 検索と置換のオプションの設定

ここで、検索と置換のオプションを設定します。`FindReplaceOptions`オブジェクト。例では、置換された段落の配置を「中央揃え」に設定します。

```csharp
FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;
```

## ステップ4: メタ文字を含むテキストの置換

私たちは`Range.Replace`メタ文字を含むテキストの置換を実行する方法。 この例では、段落区切りが続く単語「section」の各出現を、同じ単語の後に複数のダッシュと新しい段落区切りが続くものに置き換えます。

```csharp
int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);
```

## ステップ5: カスタムテキストタグの置き換え

また、`Range.Replace`カスタムを置き換える方法 "{insert-section}「」テキストタグをセクション区切りで置き換えます。この例では、「{insert-section}セクション区切りを挿入するには、「&b」を使用します。

```csharp
count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);
```

## ステップ6: 編集した文書を保存する

最後に、変更したドキュメントを指定されたディレクトリに保存します。`Save`方法：

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
```

### Aspose.Words for .NET を使用してメタ文字を含むテキストを置換するためのサンプル ソース コード

以下は、Aspose.Words for .NET でメタ文字を含むテキスト置換を使用する方法を示す完全なサンプル ソース コードです。

```csharp

	//ドキュメント ディレクトリへのパス。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.Font.Name = "Arial";
	builder.Writeln("First section");
	builder.Writeln("  1st paragraph");
	builder.Writeln("  2nd paragraph");
	builder.Writeln("{insert-section}");
	builder.Writeln("Second section");
	builder.Writeln("  1st paragraph");

	FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
	findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;

	// 「section」という単語の後の各段落区切りを二重にし、下線のようなものを追加して中央に配置します。
	int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);

	//カスタム テキスト タグの代わりにセクション区切りを挿入します。
	count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);

	doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
  
```

## 結論

この記事では、C# ソース コードを調べて、Aspose.Words for .NET のメタ文字を含むテキストの置換機能の使用方法を理解しました。ドキュメントの作成、テキストの挿入、メタ文字を含むテキストの置換、変更したドキュメントの保存という手順をステップ バイ ステップで説明しました。

### よくある質問

#### Q: Aspose.Words for .NET のメタ文字を含むテキストの置換機能とは何ですか?

A: Aspose.Words for .NET のメタ文字を含むテキストの置換機能を使用すると、特定のメタ文字を含むドキュメント内のテキストの一部を置換できます。この機能を使用すると、メタ文字を考慮したドキュメント内で高度な置換を実行できます。

#### Q: Aspose.Words for .NET で新しいドキュメントを作成するにはどうすればよいですか?

 A: メタ文字を含むテキストの置換機能を使用する前に、Aspose.Words for .NETを使用して新しいドキュメントを作成する必要があります。これは、`Document`オブジェクト。新しいドキュメントを作成するサンプル コードは次のとおりです。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### Q: Aspose.Words for .NET を使用してドキュメントにテキストを挿入するにはどうすればよいですか?

 A: 文書を作成したら、`DocumentBuilder`オブジェクトです。例では、`Writeln`複数の段落のテキストを異なるセクションに挿入する方法:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Arial";
builder.Writeln("First section");
builder.Writeln("1st paragraph");
builder.Writeln("2nd paragraph");
builder.Writen("{insert-section}");
builder.Writeln("Second section");
builder.Writeln("1st paragraph");
```

#### Q: Aspose.Words for .NET で検索および置換オプションを構成するにはどうすればよいでしょうか?

 A: 次に、検索と置換のオプションを設定します。`FindReplaceOptions`オブジェクト。例では、置換された段落の配置を「中央揃え」に設定します。

```csharp
FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;
```

#### Q: Aspose.Words for .NET を使用してドキュメント内のメタ文字を含むテキストを置き換える方法を教えてください。

 A: 私たちは`Range.Replace`メタ文字を含むテキストの置換を実行する方法。 この例では、「section」という単語の後に段落区切りが続く部分を、同じ単語の後に複数のダッシュと新しい段落区切りが続くものに置き換えます。

```csharp
int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);
```

#### Q: Aspose.Words for .NET を使用して、ドキュメント内のメタ文字を含むカスタム テキスト タグを置き換える方法を教えてください。

 A: 私たちはまた、`Range.Replace`カスタムを置き換える方法 "{insert-section}「」テキストタグをセクション区切りで置き換えます。この例では、「{insert-section}セクション区切りを挿入するには、「&b」を使用します。

```csharp
count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);
```

#### Q: Aspose.Words for .NET で編集したドキュメントを保存するにはどうすればよいですか?

 A: ドキュメントに変更を加えたら、`Save`方法：

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
```