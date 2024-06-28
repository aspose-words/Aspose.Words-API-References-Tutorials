---
title: リビジョンを挿入内のテキストを無視
linktitle: リビジョンを挿入内のテキストを無視
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET の「挿入リビジョン内のテキストを無視」機能を使用して、Word 文書内の挿入リビジョンを操作する方法を説明します。
type: docs
weight: 10
url: /ja/net/find-and-replace-text/ignore-text-inside-insert-revisions/
---

この記事では、上記の C# ソース コードを調べて、Aspose.Words for .NET ライブラリの [Insert Revisions 内のテキストを無視] 関数の使用方法を理解します。この機能は、ドキュメントの操作中に挿入リビジョン内のテキストを無視したい場合に便利です。

## 前提条件

- C# 言語の基本的な知識。
- Aspose.Words ライブラリがインストールされた .NET 開発環境。

## ステップ 1: 新しいドキュメントの作成

挿入リビジョン内のテキストの操作を開始する前に、Aspose.Words for .NET を使用して新しいドキュメントを作成する必要があります。これは、`Document`物体：

```csharp
Document doc = new Document();
```

## ステップ 2: リビジョン追跡を使用してテキストを挿入する

ドキュメントを取得したら、`DocumentBuilder`物体。たとえば、リビジョン追跡を使用して「挿入」テキストを挿入するには、`StartTrackRevisions`, `Writeln`そして`StopTrackRevisions`メソッド:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

## ステップ 3: 未レビューのテキストを挿入する

リビジョン追跡付きのテキストに加えて、`DocumentBuilder`物体。たとえば、「Text」というテキストを修正せずに挿入するには、`Write`方法：

```csharp
builder.Write("Text");
```

## ステップ 4: リビジョン挿入機能内のテキストを無視するの使用

後続の操作で挿入リビジョン内のテキストを無視するには、`FindReplaceOptions`オブジェクトを設定して、`IgnoreInserted`財産を`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
```

## ステップ 5: 検索と置換に正規表現を使用する

文書テキストの検索操作と置換を実行するには、正規表現を使用します。この例では、文字「e」が出現するすべての文字を検索し、アスタリスク「」に置き換えます。*".NET を使用します。`Regex`このクラス:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## ステップ 6: 変更されたドキュメント出力の表示

検索と置換を適用した後、ドキュメントの変更されたコンテンツを表示できます。`GetText`方法：

```csharp
Console.WriteLine(doc.GetText());
```

## ステップ 7: リビジョンの挿入を含めるようにオプションを変更する

出力結果に挿入リビジョン内のテキストを含めたい場合は、挿入リビジョンを無視しないようにオプションを変更できます。このために、`IgnoreInserted`財産を`false`:

```csharp
options.IgnoreInserted = false;
```

## ステップ 8: リビジョンを挿入して変更されたドキュメントを表示する

オプションを変更した後、検索と置換を再度実行して、挿入リビジョン内のテキストを含む結果を取得できます。

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```


### Aspose.Words for .NET を使用したリビジョンの挿入内のテキストを無視するソース コードの例

以下は、Aspose.Words for .NET での Ignore Text Inside Insert Revisions 関数の使用を示す完全なサンプル ソース コードです。


```csharp
       
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	//リビジョンを追跡してテキストを挿入します。
	doc.StartTrackRevisions("author", DateTime.Now);
	builder.Writeln("Inserted");
	doc.StopTrackRevisions();

	//改訂されていないテキストを挿入します。
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

この記事では、C# ソース コードを調べて、Aspose.Words for .NET の [リビジョンの挿入] 内のテキストを無視する機能の使用方法を理解しました。ステップバイステップのガイドに従い、ドキュメントを作成し、リビジョンを追跡するテキストと未改訂のテキストを挿入し、リビジョンの挿入機能内のテキストを無視する機能を使用し、正規表現を使用した検索と置換操作を実行し、変更されたドキュメントを表示しました。

### よくある質問

#### Q: Aspose.Words for .NET の「リビジョンの挿入内のテキストを無視」機能とは何ですか?

A: Aspose.Words for .NET の「挿入リビジョン内のテキストを無視」機能を使用すると、テキストの検索や置換などの特定の操作中に、挿入リビジョン内のテキストを無視するかどうかを指定できます。この機能が有効な場合、挿入リビジョン内のテキストは操作中に考慮されません。

#### Q: Aspose.Words for .NET を使用して新しいドキュメントを作成するにはどうすればよいですか?

 A: Aspose.Words for .NET を使用して新しいドキュメントを作成するには、`Document`物体。新しいドキュメントを作成する C# コードの例を次に示します。

```csharp
Document doc = new Document();
```

#### Q: Aspose.Words for .NET でリビジョン追跡を使用してテキストを挿入するにはどうすればよいですか?

A: ドキュメントを作成したら、`DocumentBuilder`物体。たとえば、リビジョン追跡を使用して「挿入」テキストを挿入するには、`StartTrackRevisions`, `Writeln` 、 そして`StopTrackRevisions`メソッド:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

#### Q: Aspose.Words for .NET に未修正のテキストを挿入するにはどうすればよいですか?

 A: リビジョン追跡付きのテキストに加えて、`DocumentBuilder`物体。たとえば、「Text」というテキストを修正せずに挿入するには、`Write`方法：

```csharp
builder.Write("Text");
```

#### Q: Aspose.Words for .NET で挿入リビジョン内のテキストを無視するにはどうすればよいですか?

 A: 後続の操作中に挿入リビジョン内のテキストを無視するには、`FindReplaceOptions`オブジェクトを設定して、`IgnoreInserted`財産を`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
```

#### Q: Aspose.Words for .NET で正規表現を使用して検索と置換を実行するにはどうすればよいですか?

 A: 正規表現を使用してドキュメントのテキストに対して検索および置換操作を実行するには、.NET`Regex`クラス。たとえば、文字「e」が出現するすべての文字を検索し、アスタリスク「」に置き換えます。* 」を作成できます。`Regex`オブジェクトを使用して、`Replace`方法：

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### Q: Aspose.Words for .NET でドキュメントの変更された出力を表示するにはどうすればよいですか?

 A: 検索および置換操作を適用した後、`GetText`方法：

```csharp
Console.WriteLine(doc.GetText());
```

#### Q: Aspose.Words for .NET の出力結果に挿入リビジョンを含めるにはどうすればよいですか?

 A: 出力結果に挿入リビジョン内のテキストを含めるには、挿入リビジョンを無視しないようにオプションを変更できます。このために、次のように設定できます。`IgnoreInserted`の財産`FindReplaceOptions`に反対する`false`:

```csharp
options.IgnoreInserted = false;
```

#### Q: Aspose.Words for .NET で、リビジョンを挿入して変更されたドキュメントを表示するにはどうすればよいですか?

A: 挿入リビジョンを含めるようにオプションを変更した後、再度検索と置換を実行して、挿入リビジョン内のテキストを含む結果を取得できます。

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```