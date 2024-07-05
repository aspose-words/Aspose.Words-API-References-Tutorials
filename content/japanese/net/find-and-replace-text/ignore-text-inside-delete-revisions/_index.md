---
title: 内部のテキストを無視してリビジョンを削除
linktitle: 内部のテキストを無視してリビジョンを削除
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET の「削除リビジョン内のテキストを無視する」機能の使用方法を学習します。
type: docs
weight: 10
url: /ja/net/find-and-replace-text/ignore-text-inside-delete-revisions/
---

この記事では、上記の C# ソース コードを調べて、Aspose.Words for .NET ライブラリの「削除リビジョン内のテキストを無視」機能の使用方法を理解します。この機能は、ドキュメントで Words 処理を実行するときに、削除リビジョン内のテキストを無視する場合に便利です。

## Aspose.Words for .NET ライブラリの概要

コードの詳細に入る前に、Aspose.Words for .NET ライブラリについて簡単に紹介します。これは、.NET アプリケーションで Word 文書を作成、変更、変換できる強力なライブラリです。リビジョン管理など、文書での Words 処理に多くの高度な機能を提供します。

## 「削除リビジョン内のテキストを無視」機能について

Aspose.Words for .NET の「削除リビジョン内のテキストを無視」機能を使用すると、テキストの検索や置換などの特定の操作中に、削除リビジョン内のテキストを無視するかどうかを指定できます。この機能を有効にすると、操作中にリビジョン内の削除されたテキストは考慮されません。

## ステップ 1: Aspose.Words for .NET を使用して新しいドキュメントを作成する

文書内のテキストを操作する前に、Aspose.Words for .NETを使用して新しい文書を作成する必要があります。`Document`物体：

```csharp
Document doc = new Document();
```

## ステップ2: 修正されていないテキストを文書に挿入する

文書ができたら、未確認のテキストを挿入することができます。`DocumentBuilder`オブジェクト。例えば、「削除されたテキスト」というテキストを挿入するには、`Writeln`そして`Write`方法:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. Writen("Deleted");
builder. Write("Text");
```

## ステップ3: 変更履歴を追跡しながら段落を削除する

「リビジョン削除時にテキストを無視」機能の使用方法を説明するために、リビジョン追跡を使用してドキュメントから段落を削除します。これにより、この機能が後続の操作にどのように影響するかを確認できます。

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

## ステップ 4: 「削除リビジョン内のテキストを無視」機能の適用

段落を削除して文書を準備したので、次の方法で「削除リビジョン内のテキストを無視」機能を有効にできます。`FindReplaceOptions`オブジェクトを設定します。`IgnoreDeleted`財産に`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

## ステップ5: 検索と置換に正規表現を使用する

文書のテキストに対して検索と置換を実行するには、正規表現を使用します。この例では、文字「e」のすべての出現を検索し、アスタリスク「* 「. .NET」`Regex`クラスは次の目的で使用されます:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## ステップ6: 変更されたドキュメント出力を表示する

検索と置換を適用した後、`GetText`方法：

```csharp
Console.WriteLine(doc.GetText());
```

## ステップ7: 削除したテキストを含めるようにオプションを変更する

削除されたテキストを出力結果に含めたい場合は、削除されたテキストを無視しないようにオプションを変更することができます。そのためには、`IgnoreDeleted`財産に`false`:

```csharp
options. IgnoreDeleted = false;
```

## ステップ8: テキストを削除した変更されたドキュメントを出力する

オプションを変更した後、再度検索と置換を実行して、削除されたテキストが含まれた結果を取得できます。

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### Aspose.Words for .NET を使用して、削除リビジョン内のテキストを無視するサンプル ソース コード

以下は、Aspose.Words for .NET の「削除リビジョン内のテキストを無視」機能の使用方法を示す完全なサンプル ソース コードです。

```csharp
        
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	//修正されていないテキストを挿入します。
	builder.Writeln("Deleted");
	builder.Write("Text");

	//追跡リビジョンを使用して最初の段落を削除します。
	doc.StartTrackRevisions("author", DateTime.Now);
	doc.FirstSection.Body.FirstParagraph.Remove();
	doc.StopTrackRevisions();

	FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };

	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);

	Console.WriteLine(doc.GetText());

	options.IgnoreDeleted = false;
	doc.Range.Replace(regex, "*", options);

	Console.WriteLine(doc.GetText());
    
```

## 結論

この記事では、C# ソース コードを調べて、Aspose.Words for .NET の「削除リビジョン内のテキストを無視」機能の使用方法を理解しました。この機能は、ドキュメントを操作するときに削除リビジョン内のテキストを無視するのに役立ちます。ドキュメントの作成、テキストの挿入、リビジョン追跡による段落の削除、「削除リビジョン内のテキストを無視」機能の適用、検索と置換操作の実行について、ステップ バイ ステップ ガイドに従って説明しました。

### よくある質問

#### Q: Aspose.Words for .NET の「削除リビジョン内のテキストを無視」機能とは何ですか?

A: Aspose.Words for .NET の「削除リビジョン内のテキストを無視」機能を使用すると、テキストの検索や置換などの特定の操作中に、削除リビジョン内のテキストを無視するかどうかを指定できます。この機能を有効にすると、操作中にリビジョン内の削除されたテキストは考慮されません。

#### Q: Aspose.Words for .NET とは何ですか?

A: Aspose.Words for .NET は、Word 文書を作成、編集し、.NET アプリケーションに変換するための強力なライブラリです。リビジョン管理など、文書の Words 処理に高度な機能を多数提供します。

#### Q: Aspose.Words for .NET で新しいドキュメントを作成するにはどうすればよいですか?

 A: 文書内のテキストを操作する前に、Aspose.Words for .NETを使用して新しい文書を作成する必要があります。これは、`Document`オブジェクト。新しいドキュメントを作成するサンプル コードは次のとおりです。

```csharp
Document doc = new Document();
```

#### Q: Aspose.Words for .NET を使用して、編集されていないテキストをドキュメントに挿入するにはどうすればよいですか?

 A: 文書ができたら、未確認のテキストを挿入するには`DocumentBuilder`オブジェクト。たとえば、「削除されたテキスト」というテキストを挿入するには、`Writeln`そして`Write`方法:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writen("Deleted");
builder.Write("Text");
```

#### Q: Aspose.Words for .NET でリビジョン追跡付きの段落を削除するにはどうすればよいですか?

A: 「リビジョン削除時のテキストを無視」機能の使い方を説明するために、リビジョン追跡を使用してドキュメントから段落を削除します。これにより、この機能が後続の操作にどのように影響するかを確認できます。

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

#### Q: Aspose.Words for .NET で「削除リビジョン内のテキストを無視」機能を有効にする方法を教えてください。

 A: 段落を削除して文書を準備したので、`FindReplaceOptions`オブジェクトを設定します。`IgnoreDeleted`財産に`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

#### Q: Aspose.Words for .NET で正規表現を使用して検索および置換するにはどうすればよいですか?

A: 文書のテキストに対して検索と置換を実行するには、正規表現を使用します。この例では、文字「e」のすべての出現を検索し、アスタリスク「* 「.NETを使用します`Regex`このクラス:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### Q: Aspose.Words for .NET で変更されたドキュメント コンテンツを表示するにはどうすればよいですか?

A: 検索と置換を適用した後、`GetText`方法：

```csharp
Console.WriteLine(doc.GetText());
```

#### Q: Aspose.Words for .NET で削除されたテキストを出力結果に含めるにはどうすればよいですか?

 A: 削除されたテキストを出力結果に含めたい場合は、削除されたテキストを無視しないようにオプションを変更することができます。そのためには、`IgnoreDeleted`財産に`false`:

```csharp
options. IgnoreDeleted = false;
```

#### Q: Aspose.Words for .NET でテキストを削除した編集済みドキュメントを表示するにはどうすればよいですか?

A: オプションを変更した後、新しい検索と置換を実行して、削除されたテキストが含まれた結果を取得できます。

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```
