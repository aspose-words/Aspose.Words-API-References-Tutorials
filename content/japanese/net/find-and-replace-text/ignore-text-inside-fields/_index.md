---
title: フィールド内のテキストを無視する
linktitle: フィールド内のテキストを無視する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET の「フィールド内のテキストを無視」機能の使用方法を学習します。
type: docs
weight: 10
url: /ja/net/find-and-replace-text/ignore-text-inside-fields/
---
この記事では、上記の C# ソース コードを調べて、Aspose.Words for .NET ライブラリのフィールド内のテキストを無視する関数の使用方法を理解します。この機能は、ドキュメントを操作するときにフィールド内のテキストを無視したい場合に便利です。

## 前提条件

- C# 言語の基本的な知識。
- Aspose.Words ライブラリがインストールされた .NET 開発環境。

## ステップ 1: 新しいドキュメントの作成

フィールド内のテキストの操作を開始する前に、Aspose.Words for .NET を使用して新しいドキュメントを作成する必要があります。これは、`Document`物体：

```csharp
Document doc = new Document();
```

## ステップ 2: テキストを含むフィールドを挿入する

ドキュメントを取得したら、`DocumentBuilder`物体。たとえば、「フィールド内のテキスト」というテキストを含む「INCLUDETEXT」フィールドを挿入するには、`InsertField`方法：

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertField("INCLUDETEXT", "Text in field");
```

## ステップ 3: フィールド内のテキストを無視機能を使用する

後続の操作でフィールド内のテキストを無視するには、`FindReplaceOptions`オブジェクトを設定して、`IgnoreFields`財産を`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
```

## ステップ 4: 正規表現を使用した検索と置換

ドキュメントのテキストに対して検索および置換操作を実行するには、正規表現を使用します。この例では、文字「e」が出現するすべての文字を検索し、アスタリスク「」に置き換えます。*".NET を使用します。`Regex`このクラス:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## ステップ 5: 変更されたドキュメント出力の表示

検索と置換を適用した後、ドキュメントの変更されたコンテンツを表示できます。`GetText`方法：

```csharp
Console.WriteLine(doc.GetText());
```

## ステップ 6: フィールドを含めるようにオプションを変更する

出力結果のフィールド内のテキストを含めます。フィールドを無視しないようにオプションを変更できます。このために、`IgnoreFields`財産を`false`:

```csharp
options.IgnoreFields = false;
```

## ステップ 7: フィールドを含む変更されたドキュメントを表示する

オプションを変更した後、検索と置換を再度実行して、含まれているフィールド内のテキストを含む結果を取得できます。

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### Aspose.Words for .NET を使用したフィールド内のテキストを無視するソース コードの例

Aspose.Words for .NET での Ignore Text Inside Fields 関数の使用を示す完全なサンプル ソース コードを次に示します。

```csharp
    
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	//中にテキストを含むフィールドを挿入します。
	builder.InsertField("INCLUDETEXT", "Text in field");
	
	FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
	
	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());

	options.IgnoreFields = false;
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());
  
```

## 結論

この記事では、C# ソース コードを調べて、Aspose.Words for .NET のフィールド内のテキストを無視する関数の使用方法を理解しました。ステップバイステップのガイドに従って、ドキュメントを作成し、テキストを含むフィールドを挿入し、フィールド内のテキストを無視機能を使用し、正規表現を使用して検索と置換操作を実行し、変更されたドキュメントを表示しました。

### よくある質問

#### Q: Aspose.Words for .NET の「フィールド内のテキストを無視」機能とは何ですか?

A: Aspose.Words for .NET の「フィールド内のテキストを無視」機能を使用すると、テキストの検索や置換などの特定の操作中にフィールド内のテキストを無視するかどうかを指定できます。この機能が有効な場合、フィールド内のテキストは操作中に考慮されません。

#### Q: Aspose.Words for .NET を使用して新しいドキュメントを作成するにはどうすればよいですか?

 A: Aspose.Words for .NET を使用して新しいドキュメントを作成するには、`Document`物体。新しいドキュメントを作成する C# コードの例を次に示します。

```csharp
Document doc = new Document();
```

#### Q: Aspose.Words for .NET を使用してドキュメント内にテキストを含むフィールドを挿入するにはどうすればよいですか?

 A: ドキュメントを作成したら、`DocumentBuilder`物体。たとえば、「フィールド内のテキスト」というテキストを含む「INCLUDETEXT」フィールドを挿入するには、`InsertField`方法：

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertField("INCLUDETEXT", "Text in field");
```

#### Q: Aspose.Words for .NET のフィールド内のテキストを無視するにはどうすればよいですか?

 A: 後続の操作中にフィールド内のテキストを無視するには、`FindReplaceOptions`オブジェクトを設定して、`IgnoreFields`財産を`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
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

#### Q: Aspose.Words for .NET の出力結果にフィールドを含めるにはどうすればよいですか?

 A: フィールド内のテキストを出力結果に含めるには、フィールドを無視しないようにオプションを変更できます。このために、次のように設定できます。`IgnoreFields`の財産`FindReplaceOptions`に反対する`false`:

```csharp
options.IgnoreFields = false;
```

#### Q: Aspose.Words for .NET のフィールドを含む変更されたドキュメントを表示するにはどうすればよいですか?

A: フィールドを含めるようにオプションを変更した後、再度検索と置換を実行すると、フィールド内のテキストが含まれた結果を取得できます。

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```