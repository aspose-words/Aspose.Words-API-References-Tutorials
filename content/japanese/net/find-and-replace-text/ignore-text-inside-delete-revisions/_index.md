---
title: リビジョンの削除内のテキストを無視する
linktitle: リビジョンの削除内のテキストを無視する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET の「リビジョンの削除内のテキストを無視」機能の使用方法を学習します。
type: docs
weight: 10
url: /ja/net/find-and-replace-text/ignore-text-inside-delete-revisions/
---

この記事では、Aspose.Words for .NET ライブラリの「削除リビジョン内のテキストを無視」機能の使用方法を理解するために、上記の C# ソース コードを調べます。この機能は、文書をワードプロセッサで処理するときに、削除リビジョン内のテキストを無視したい場合に便利です。

## Aspose.Words for .NET ライブラリの概要

コードの詳細に入る前に、Aspose.Words for .NET ライブラリについて簡単に紹介します。これは、.NET アプリケーションで Word 文書を作成、変更、変換できる強力なライブラリです。リビジョン管理など、文書のワープロ処理に多くの高度な機能を提供します。

## 「リビジョン削除内のテキストを無視」機能について

Aspose.Words for .NET の「削除リビジョン内のテキストを無視」機能を使用すると、テキストの検索や置換などの特定の操作中に、削除リビジョン内のテキストを無視するかどうかを指定できます。この機能が有効な場合、リビジョン内の削除されたテキストは操作中に考慮されません。

## ステップ 1: Aspose.Words for .NET を使用して新しいドキュメントを作成する

ドキュメント内のテキストの操作を開始する前に、Aspose.Words for .NET を使用して新しいドキュメントを作成する必要があります。それはインスタンス化することで実行できます`Document`物体：

```csharp
Document doc = new Document();
```

## ステップ 2: 改訂されていないテキストを文書に挿入する

ドキュメントを取得したら、`DocumentBuilder`物体。たとえば、「削除されたテキスト」というテキストを挿入するには、`Writeln`そして`Write`メソッド:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. Writen("Deleted");
builder. Write("Text");
```

## ステップ 3: リビジョンを追跡して段落を削除する

「リビジョン削除内のテキストを無視」機能の使用法を説明するために、リビジョン追跡を使用して文書から段落を削除します。これにより、この機能が後続の操作にどのような影響を与えるかを確認できるようになります。

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

## ステップ 4: 「リビジョン削除内のテキストを無視」機能を適用する

段落を削除して文書を準備したので、次は、`FindReplaceOptions`物体。を設定します。`IgnoreDeleted`財産を`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

## ステップ 5: 正規表現を使用した検索と置換

ドキュメントのテキストに対して検索および置換操作を実行するには、正規表現を使用します。この例では、文字「e」が出現するすべての文字を検索し、アスタリスク「」に置き換えます。* 「..NET」`Regex`クラスはこれに使用されます。

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## ステップ 6: 変更されたドキュメント出力の表示

検索と置換を適用した後、ドキュメントの変更されたコンテンツを表示できます。`GetText`方法：

```csharp
Console.WriteLine(doc.GetText());
```

## ステップ 7: 削除されたテキストを含めるようにオプションを変更する

出力結果に削除されたテキストを含めたい場合は、削除されたテキストを無視しないようにオプションを変更できます。このために、`IgnoreDeleted`財産を`false`:

```csharp
options. IgnoreDeleted = false;
```

## ステップ 8: テキストを削除して変更したドキュメントを出力する

オプションを変更した後、検索と置換を再度実行すると、削除されたテキストが含まれた結果が得られます。

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### Aspose.Words for .NET を使用したリビジョン内のテキストを無視するためのソース コードの例

以下は、Aspose.Words for .NET での「リビジョンの削除内のテキストを無視」機能の使用を示す完全なサンプル ソース コードです。

```csharp
        
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	//改訂されていないテキストを挿入します。
	builder.Writeln("Deleted");
	builder.Write("Text");

	//リビジョンを追跡して最初の段落を削除します。
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

この記事では、Aspose.Words for .NET の「削除リビジョン内のテキストを無視」機能の使用方法を理解するために C# ソース コードを調査しました。この機能は、ドキュメントを操作するときに削除リビジョン内のテキストを無視する場合に便利です。ステップバイステップのガイドに従って、ドキュメントの作成、テキストの挿入、リビジョン追跡による段落の削除、「リビジョン削除内のテキストを無視」機能の適用、検索と置換操作の実行を行いました。

### よくある質問

#### Q: Aspose.Words for .NET の「リビジョンの削除内のテキストを無視」機能とは何ですか?

A: Aspose.Words for .NET の「削除リビジョン内のテキストを無視」機能を使用すると、テキストの検索や置換などの特定の操作中に、削除リビジョン内のテキストを無視するかどうかを指定できます。この機能が有効な場合、リビジョン内の削除されたテキストは操作中に考慮されません。

#### Q: Aspose.Words for .NET とは何ですか?

A: Aspose.Words for .NET は、Word ドキュメントを作成、編集し、.NET アプリケーションに変換するための強力なライブラリです。リビジョン管理など、文書のワープロ処理に多くの高度な機能を提供します。

#### Q: Aspose.Words for .NET で新しいドキュメントを作成するにはどうすればよいですか?

 A: ドキュメント内のテキストの操作を開始する前に、Aspose.Words for .NET を使用して新しいドキュメントを作成する必要があります。これは、`Document`物体。新しいドキュメントを作成するサンプルコードは次のとおりです。

```csharp
Document doc = new Document();
```

#### Q: Aspose.Words for .NET を使用して未編集のテキストをドキュメントに挿入するにはどうすればよいですか?

 A: ドキュメントを作成したら、`DocumentBuilder`物体。たとえば、「削除されたテキスト」というテキストを挿入するには、`Writeln`そして`Write`メソッド:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writen("Deleted");
builder.Write("Text");
```

#### Q: Aspose.Words for .NET でリビジョン追跡を使用して段落を削除するにはどうすればよいですか?

A: 「リビジョン削除内のテキストを無視」機能の使用方法を説明するために、リビジョン追跡を使用してドキュメントから段落を削除します。これにより、この関数が後続の操作にどのような影響を与えるかを確認できるようになります。

```csharp
doc.StartTrackRevisions("author", DateTime.Now);
doc.FirstSection.Body.FirstParagraph.Remove();
doc.StopTrackRevisions();
```

#### Q: Aspose.Words for .NET で「リビジョンの削除内のテキストを無視」機能を有効にするにはどうすればよいですか?

 A: 段落を削除して文書を準備したので、次は、`FindReplaceOptions`物体。を設定します。`IgnoreDeleted`財産を`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreDeleted = true };
```

#### Q: Aspose.Words for .NET で正規表現を使用して検索および置換するにはどうすればよいですか?

A: ドキュメントのテキストに対して検索および置換操作を実行するには、正規表現を使用します。この例では、文字「e」が出現するすべての文字を検索し、アスタリスク「」に置き換えます。* ".NET を使用します。`Regex`このクラス:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### Q: Aspose.Words for .NET で変更されたドキュメント コンテンツを表示するにはどうすればよいですか?

A: 検索と置換を適用した後、`GetText`方法：

```csharp
Console.WriteLine(doc.GetText());
```

#### Q: Aspose.Words for .NET の出力結果に削除されたテキストを含めるにはどうすればよいですか?

 A: 削除されたテキストを出力結果に含めたい場合は、削除されたテキストを無視しないようにオプションを変更できます。このために、`IgnoreDeleted`財産を`false`:

```csharp
options. IgnoreDeleted = false;
```

#### Q: Aspose.Words for .NET でテキストが削除された編集済みドキュメントを表示するにはどうすればよいですか?

A: オプションを変更した後、新しい検索と置換を実行して、削除されたテキストを含む結果を取得できます。

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```
