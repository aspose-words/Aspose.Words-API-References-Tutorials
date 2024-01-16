---
title: Word 文書での複数レベルのリストの書式設定
linktitle: Word 文書での複数レベルのリストの書式設定
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して複数レベルのリストを作成し、Word 文書にカスタム書式設定を適用する方法を学びます。
type: docs
weight: 10
url: /ja/net/document-formatting/multilevel-list-formatting/
---
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書機能のマルチレベル リストの書式設定を使用する方法を説明します。以下の手順に従ってソース コードを理解し、変更を適用します。

## ステップ 1: ドキュメントの作成と構成

まず、新しいドキュメントと関連する DocumentBuilder オブジェクトを作成します。その方法は次のとおりです。

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ 2: マルチレベルリストのフォーマットを設定する

次に、DocumentBuilder オブジェクトで使用できるメソッドを使用して、マルチレベルのリストの書式設定を適用します。その方法は次のとおりです。

```csharp
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder. Writen("Element 2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.1");
builder.Writeln("Element 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.2.1");
builder.Writeln("Element 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 3");

builder.ListFormat.RemoveNumbers();
```

## ステップ 3: ドキュメントを保存する

テキスト入力フォームフィールドを挿入した後、`Save`方法。必ず適切なファイル パスを指定してください。

```csharp
doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");
```

### Aspose.Words for .NET を使用したマルチレベル リストのフォーマットのソース コード例

Aspose.Words for .NET を使用したマルチレベル リストの書式設定機能の完全なソース コードを次に示します。


```csharp

//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyNumberDefault();
builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();
builder.Writeln("Item 2.1");
builder.Writeln("Item 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Item 2.2.1");
builder.Writeln("Item 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Item 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Item 3");

builder.ListFormat.RemoveNumbers();

doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");

```

このコードを使用すると、Aspose.Words for .NET を使用してマルチレベルのリストを作成し、各レベルに適切な書式設定を適用できます。


## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書でマルチレベル リストの書式設定機能を利用するプロセスについて説明しました。概要を示した手順に従うことで、複数のレベルでよく整理されたリストを作成し、ドキュメントの構造と読みやすさを向上させることができます。

### よくある質問

#### Q: Word 文書の複数レベルのリストとは何ですか?

A: Word 文書のマルチレベル リストは、項目をさまざまなレベルのサブ項目に整理できる階層リストです。情報を構造化して表示するのに役立ち、読者が内容を理解しやすくなります。

#### Q: マルチレベルリストの外観をカスタマイズできますか?

A: はい、Word 文書内の複数レベルのリストの外観をカスタマイズできます。箇条書き、数字、文字などのさまざまなスタイルを適用し、インデントや間隔を調整することで、視覚的に魅力的で整理されたリストを作成できます。

#### Q: Aspose.Words for .NET は他のリスト書式設定オプションをサポートしていますか?

A: はい、Aspose.Words for .NET は、リストの書式設定のための包括的な機能セットを提供します。箇条書きリスト、番号付きリスト、マルチレベルリストなど、さまざまなタイプのリストをサポートしています。リストの書式設定を操作したり、項目を追加または削除したり、外観をカスタマイズしたりできます。

#### Q: Aspose.Words for .NET を使用して他のドキュメント要素を操作できますか?

A: はい、Aspose.Words for .NET は、段落、表、画像などのさまざまなドキュメント要素を操作するための広範な機能を提供します。 Word 文書をプログラムで作成、変更、変換できるため、文書処理タスクが合理化されます。