---
title: メタ文字を含むテキストを Word で置換
linktitle: メタ文字を含むテキストを Word で置換
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書内のメタキャラクターを含むテキストを単語置換する方法を学びます。
type: docs
weight: 10
url: /ja/net/find-and-replace-text/replace-text-containing-meta-characters/
---
この記事では、Aspose.Words for .NET ライブラリの Word のメタ文字を含むテキストの置換機能の使用方法を理解するために、上記の C# ソース コードを調べます。この機能を使用すると、特定のメタ文字を含むドキュメント内のテキストの一部を置換できます。

## 前提条件

- C# 言語の基本的な知識。
- Aspose.Words ライブラリがインストールされた .NET 開発環境。

## ステップ 1: 新しいドキュメントの作成

メタキャラクター テキスト置換の使用を開始する前に、Aspose.Words for .NET を使用して新しいドキュメントを作成する必要があります。これは、`Document`物体：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## ステップ 2: 文書にテキストを挿入する

ドキュメントを取得したら、`DocumentBuilder`物体。この例では、`Writeln`複数の段落のテキストを異なるセクションに挿入するメソッド:

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

## ステップ 3: 検索と置換のオプションを構成する

次に、`FindReplaceOptions`物体。この例では、置換された段落の配置を「中央揃え」に設定します。

```csharp
FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;
```

## ステップ 4: メタキャラクターを含むテキストを置換する

私たちが使用するのは、`Range.Replace`メタキャラクターを含むテキストの置換を実行するメソッド。この例では、単語「section」の後に段落区切りが続く各単語を、複数のダッシュと新しい段落区切りが続く同じ単語に置き換えます。

```csharp
int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);
```

## ステップ 5: カスタム テキスト タグを置換する

私たちはまた、`Range.Replace`カスタムを置き換えるメソッド「{insert-section}" セクション区切りのあるテキスト タグ。この例では、 " を置き換えます。{insert-section}" と "&b" を組み合わせてセクション区切りを挿入します。

```csharp
count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);
```

## ステップ 6: 編集したドキュメントを保存する

最後に、変更したドキュメントを指定したディレクトリに保存します。`Save`方法：

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
```

### Aspose.Words for .NET を使用したメタ文字を含むテキストの置換のソース コード例

Aspose.Words for .NET でメタキャラクターを含むテキスト置換を使用する方法を示す完全なソース コード例を次に示します。

```csharp

	//ドキュメントディレクトリへのパス。
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

	// 「セクション」という単語の後の段落区切りを 2 倍にし、下線を追加して中央揃えにします。
	int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);

	//カスタム テキスト タグの代わりにセクション区切りを挿入します。
	count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);

	doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
  
```

## 結論

この記事では、C# ソース コードを調べて、Aspose.Words for .NET のメタ文字を含むテキストの置換機能の使用方法を理解しました。ステップバイステップのガイドに従って、ドキュメントを作成し、テキストを挿入し、メタキャラクターを含むテキストを置換し、変更したドキュメントを保存しました。

### よくある質問

#### Q: Aspose.Words for .NET のメタ文字を含むテキストの置換機能とは何ですか?

A: Aspose.Words for .NET のメタ キャラクターを含むテキストの置換機能を使用すると、特定のメタ キャラクターを含むドキュメント内のテキストの一部を置換できます。この機能を使用すると、メタキャラクターを考慮してドキュメント内で高度な置換を実行できます。

#### Q: Aspose.Words for .NET で新しいドキュメントを作成するにはどうすればよいですか?

 A: メタ文字を含むテキストの置換機能を使用する前に、Aspose.Words for .NET を使用して新しいドキュメントを作成する必要があります。これは、`Document`物体。新しいドキュメントを作成するサンプルコードは次のとおりです。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

#### Q: Aspose.Words for .NET を使用してドキュメントにテキストを挿入するにはどうすればよいですか?

 A: ドキュメントを作成したら、`DocumentBuilder`物体。この例では、`Writeln`複数の段落のテキストを異なるセクションに挿入するメソッド:

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

#### Q: Aspose.Words for .NET で検索および置換のオプションを構成するにはどうすればよいですか?

 A: 次に、`FindReplaceOptions`物体。この例では、置換された段落の配置を「中央揃え」に設定します。

```csharp
FindReplaceOptions findReplaceOptions = new FindReplaceOptions();
findReplaceOptions.ApplyParagraphFormat.Alignment = ParagraphAlignment.Center;
```

#### Q: Aspose.Words for .NET を使用して、ドキュメント内のメタキャラクターを含むテキストを置換するにはどうすればよいですか?

 A: を使用します。`Range.Replace`メタ文字を含むテキストの置換を実行するメソッド。この例では、単語「section」の後に段落区切りが続く各単語を、複数のダッシュと新しい段落区切りが続く同じ単語に置き換えます。

```csharp
int count = doc.Range.Replace("section&p", "section&p----------------------&p", findReplaceOptions);
```

#### Q: Aspose.Words for .NET を使用して、ドキュメント内のメタ文字を含むカスタム テキスト タグを置き換えるにはどうすればよいですか?

 A: も使用しています。`Range.Replace`カスタムを置き換えるメソッド「{insert-section}" セクション区切りのあるテキスト タグ。この例では、 " を置き換えます。{insert-section}" と "&b" を組み合わせてセクション区切りを挿入します。

```csharp
count = doc.Range.Replace("{insert-section}", "&b", findReplaceOptions);
```

#### Q: Aspose.Words for .NET で編集したドキュメントを保存するにはどうすればよいですか?

 A: ドキュメントに変更を加えたら、次のコマンドを使用して指定したディレクトリにドキュメントを保存できます。`Save`方法：

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextContainingMetaCharacters.docx");
```