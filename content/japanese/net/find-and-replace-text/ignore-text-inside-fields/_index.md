---
title: フィールド内のテキストを無視
linktitle: フィールド内のテキストを無視
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET の「フィールド内のテキストを無視」機能の使用方法を学習します。
type: docs
weight: 10
url: /ja/net/find-and-replace-text/ignore-text-inside-fields/
---
この記事では、上記の C# ソース コードを調べて、Aspose.Words for .NET ライブラリの Ignore Text Inside Fields 関数の使用方法を理解します。この機能は、ドキュメントを操作するときにフィールド内のテキストを無視する場合に便利です。

## 前提条件

- C# 言語に関する基本的な知識。
- Aspose.Words ライブラリがインストールされた .NET 開発環境。

## ステップ1: 新しいドキュメントを作成する

フィールド内のテキストを操作する前に、Aspose.Words for .NETを使用して新しいドキュメントを作成する必要があります。これは、`Document`物体：

```csharp
Document doc = new Document();
```

## ステップ2: テキストを含むフィールドを挿入する

文書ができたら、その中にテキストを含むフィールドを挿入することができます。`DocumentBuilder`オブジェクト。たとえば、「フィールド内のテキスト」というテキストを含む「INCLUDETEXT」フィールドを挿入するには、`InsertField`方法：

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertField("INCLUDETEXT", "Text in field");
```

## ステップ3: フィールド内のテキストを無視する機能を使用する

後続の操作でフィールド内のテキストを無視するには、`FindReplaceOptions`オブジェクトを設定し、`IgnoreFields`財産に`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
```

## ステップ4: 検索と置換に正規表現を使用する

文書のテキストに対して検索と置換を実行するには、正規表現を使用します。この例では、文字「e」のすべての出現を検索し、アスタリスク「*「.NETの`Regex`このクラス:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## ステップ5: 変更されたドキュメント出力の表示

検索と置換を適用した後、`GetText`方法：

```csharp
Console.WriteLine(doc.GetText());
```

## ステップ6: フィールドを含めるためのオプションの変更

出力結果にフィールド内のテキストを含めたい場合は、フィールドを無視しないようにオプションを変更することができます。そのためには、`IgnoreFields`財産に`false`:

```csharp
options.IgnoreFields = false;
```

## ステップ7: フィールドを含む変更されたドキュメントを表示する

オプションを変更した後、再度検索と置換を実行して、含まれているフィールド内のテキストを含む結果を取得できます。

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### Aspose.Words for .NET を使用してフィールド内のテキストを無視するサンプル ソース コード

以下は、Aspose.Words for .NET でフィールド内のテキストを無視する機能の使用方法を示す完全なサンプル ソース コードです。

```csharp
    
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	//テキストが入ったフィールドを挿入します。
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

この記事では、C# ソース コードを調べて、Aspose.Words for .NET の Ignore Text Inside Fields 機能の使用方法を理解しました。ドキュメントの作成、テキストを含むフィールドの挿入、Ignore Text Inside Fields 機能の使用、正規表現を使用した検索および置換操作の実行、変更されたドキュメントの表示について、ステップ バイ ステップ ガイドに従いました。

### よくある質問

#### Q: Aspose.Words for .NET の「フィールド内のテキストを無視」機能とは何ですか?

A: Aspose.Words for .NET の「フィールド内のテキストを無視」機能を使用すると、テキストの検索や置換などの特定の操作中にフィールド内のテキストを無視するかどうかを指定できます。この機能を有効にすると、操作中にフィールド内のテキストは考慮されません。

#### Q: Aspose.Words for .NET を使用して新しいドキュメントを作成するにはどうすればよいですか?

 A: Aspose.Words for .NETを使用して新しいドキュメントを作成するには、`Document`オブジェクト。新しいドキュメントを作成する C# コードの例を次に示します。

```csharp
Document doc = new Document();
```

#### Q: Aspose.Words for .NET を使用してドキュメント内にテキストを含むフィールドを挿入するにはどうすればよいですか?

 A: 文書を作成したら、テキストフィールドを挿入することができます。`DocumentBuilder`オブジェクト。たとえば、「フィールド内のテキスト」というテキストを含む「INCLUDETEXT」フィールドを挿入するには、`InsertField`方法：

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertField("INCLUDETEXT", "Text in field");
```

#### Q: Aspose.Words for .NET のフィールド内のテキストを無視するにはどうすればよいですか?

 A: 後続の操作でフィールド内のテキストを無視するには、`FindReplaceOptions`オブジェクトを設定し、`IgnoreFields`財産に`true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
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

#### Q: Aspose.Words for .NET の出力結果にフィールドを含めるにはどうすればよいでしょうか?

 A: フィールド内のテキストを出力結果に含めるには、フィールドを無視しないようにオプションを変更します。そのためには、`IgnoreFields`の財産`FindReplaceOptions`反対する`false`:

```csharp
options.IgnoreFields = false;
```

#### Q: Aspose.Words for .NET のフィールドを使用して変更されたドキュメントを表示するにはどうすればよいでしょうか?

A: フィールドを含めるようにオプションを変更した後、再度検索と置換を実行して、フィールド内のテキストが含まれた結果を取得できます。

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```