---
title: 内部のテキストを無視する リビジョンを挿入する
linktitle: 内部のテキストを無視する リビジョンを挿入する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET の「挿入リビジョン内のテキストを無視」機能を使用して、Word 文書内の挿入リビジョンを操作する方法を学習します。
type: docs
weight: 10
url: /ja/net/find-and-replace-text/ignore-text-inside-insert-revisions/
---

この記事では、上記の C# ソース コードを調べて、Aspose.Words for .NET ライブラリの Ignore Text Inside Insert Revisions 機能の使用方法を理解します。この機能は、ドキュメントの操作中に挿入リビジョン内のテキストを無視する場合に便利です。

## 前提条件

- C# 言語に関する基本的な知識。
- Aspose.Words ライブラリがインストールされた .NET 開発環境。

## ステップ1: 新しいドキュメントを作成する

挿入リビジョン内のテキストを操作する前に、Aspose.Words for .NETを使用して新しいドキュメントを作成する必要があります。これは、`Document`物体：

```csharp
Document doc = new Document();
```

## ステップ2: 変更履歴付きのテキストを挿入する

文書ができたら、`DocumentBuilder`オブジェクト。たとえば、リビジョントラッキング付きの「挿入済み」テキストを挿入するには、`StartTrackRevisions`, `Writeln`そして`StopTrackRevisions`方法:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

## ステップ3: 未確認のテキストを挿入する

改訂履歴付きのテキストに加えて、`DocumentBuilder`オブジェクト。たとえば、「Text」というテキストを修正せずに挿入するには、`Write`方法：

```csharp
builder.Write("Text");
```

## ステップ4: 挿入リビジョン内のテキストを無視する機能を使用する

以降の操作で挿入リビジョン内のテキストを無視するには、`FindReplaceOptions`オブジェクトを設定し、`IgnoreInserted`財産に`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
```

## ステップ5: 検索と置換に正規表現を使用する

文書テキストの検索と置換を実行するには、正規表現を使用します。この例では、文字「e」のすべての出現を検索し、アスタリスク「*「.NETの`Regex`このクラス:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## ステップ6: 変更されたドキュメント出力の表示

検索と置換を適用した後、`GetText`方法：

```csharp
Console.WriteLine(doc.GetText());
```

## ステップ 7: 挿入リビジョンを含めるようにオプションを変更する

挿入リビジョン内のテキストを出力結果に含めたい場合は、挿入リビジョンを無視しないようにオプションを変更することができます。そのためには、`IgnoreInserted`財産に`false`:

```csharp
options.IgnoreInserted = false;
```

## ステップ 8: 修正を挿入して変更されたドキュメントを表示する

オプションを変更した後、再度検索と置換を実行して、挿入リビジョン内のテキストが含まれた結果を取得できます。

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```


### Aspose.Words for .NET を使用して、挿入リビジョン内のテキストを無視するサンプル ソース コード

以下は、Aspose.Words for .NET で「挿入リビジョン内のテキストを無視」機能を使用する方法を示す完全なサンプル ソース コードです。


```csharp
       
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	//追跡リビジョン付きのテキストを挿入します。
	doc.StartTrackRevisions("author", DateTime.Now);
	builder.Writeln("Inserted");
	doc.StopTrackRevisions();

	//修正されていないテキストを挿入します。
	builder.Write("Text");

	FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };

	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());

	options.IgnoreInserted = false;
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());
   
```

## 結論

この記事では、C# ソース コードを調べて、Aspose.Words for .NET の Ignore Text Inside Insert Revisions 機能の使用方法を理解しました。ドキュメントの作成、追跡リビジョン付きテキストと未修正テキストの挿入、Ignore Text Inside Insert Revisions 機能の使用、正規表現を使用した検索および置換操作の実行、変更されたドキュメントの表示について、ステップ バイ ステップ ガイドに従いました。

### よくある質問

#### Q: Aspose.Words for .NET の「挿入リビジョン内のテキストを無視する」機能とは何ですか?

A: Aspose.Words for .NET の「挿入リビジョン内のテキストを無視」機能を使用すると、テキストの検索や置換などの特定の操作中に挿入リビジョン内のテキストを無視するかどうかを指定できます。この機能を有効にすると、操作中に挿入リビジョン内のテキストは考慮されません。

#### Q: Aspose.Words for .NET を使用して新しいドキュメントを作成するにはどうすればよいですか?

 A: Aspose.Words for .NETを使用して新しいドキュメントを作成するには、`Document`オブジェクト。新しいドキュメントを作成する C# コードの例を次に示します。

```csharp
Document doc = new Document();
```

#### Q: Aspose.Words for .NET でリビジョン追跡付きのテキストを挿入するにはどうすればよいですか?

A: 文書ができたら、`DocumentBuilder`オブジェクト。たとえば、リビジョン追跡機能付きで「挿入済み」テキストを挿入するには、`StartTrackRevisions`, `Writeln` 、 そして`StopTrackRevisions`方法:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

#### Q: Aspose.Words for .NET に未修正のテキストを挿入するにはどうすればよいですか?

 A: 修正履歴のあるテキストに加えて、`DocumentBuilder`オブジェクト。たとえば、「テキスト」というテキストを修正せずに挿入するには、`Write`方法：

```csharp
builder.Write("Text");
```

#### Q: Aspose.Words for .NET で挿入リビジョン内のテキストを無視するにはどうすればよいですか?

 A: 以降の操作で挿入リビジョン内のテキストを無視するには、`FindReplaceOptions`オブジェクトを設定し、`IgnoreInserted`財産に`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
```

#### Q: Aspose.Words for .NET で正規表現を使用して検索と置換を実行するにはどうすればよいですか?

 A: 正規表現を使用して文書のテキストを検索および置換するには、.NETを使用します。`Regex`クラス。たとえば、文字「e」のすべての出現を検索し、それらをアスタリスク「* 「」を作成することができます`Regex`オブジェクトとそれを使用して`Replace`方法：

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### Q: Aspose.Words for .NET でドキュメントの変更された出力を表示するにはどうすればよいでしょうか?

 A: 検索と置換操作を適用した後、`GetText`方法：

```csharp
Console.WriteLine(doc.GetText());
```

#### Q: Aspose.Words for .NET の出力結果に挿入リビジョンを含めるにはどうすればよいですか?

 A: 挿入リビジョン内のテキストを出力結果に含めるには、挿入リビジョンを無視しないようにオプションを変更します。そのためには、`IgnoreInserted`の財産`FindReplaceOptions`反対する`false`:

```csharp
options.IgnoreInserted = false;
```

#### Q: Aspose.Words for .NET で、挿入リビジョンを含む変更されたドキュメントを表示するにはどうすればよいでしょうか?

A: 挿入リビジョンを含めるようにオプションを変更した後、再度検索と置換を実行して、挿入リビジョン内のテキストが含まれた結果を取得できます。

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```