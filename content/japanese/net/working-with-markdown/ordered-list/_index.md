---
title: 順序付きリスト
linktitle: 順序付きリスト
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して順序付きリストを作成する方法をステップバイステップ ガイドで学習します。
type: docs
weight: 10
url: /ja/net/working-with-markdown/ordered-list/
---

この例では、Aspose.Words for .NET で順序付きリスト機能を使用する方法について説明します。順序付きリストを使用すると、番号を使用して項目を順番に整理できます。

## ステップ1: ドキュメントジェネレーターの使用

まず、ドキュメント ジェネレーターを使用して新しいドキュメントを作成します。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ2: 順序付きリスト形式を適用する

ドキュメントビルダーの`ApplyBulletDefault`メソッド。リスト レベルに移動して必要な形式を設定することで、番号付け形式をカスタマイズすることもできます。

```csharp
builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";
```

## ステップ3: リストにアイテムを追加する

ドキュメントジェネレーターの`Writeln`方法。

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## ステップ4: リストをインデントする

ドキュメントジェネレーターの`ListIndent`方法。

```csharp
builder.ListFormat.ListIndent();
builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

## ステップ5: ドキュメントを保存する

最後に、ドキュメントを希望の形式で保存できます。

### Aspose.Words for .NET を使用した順序付きリストのサンプル ソース コード

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";

builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

おめでとうございます。これで、Aspose.Words for .NET で順序付きリスト機能を使用する方法を学習しました。


### よくある質問

#### Q: Markdown で順序付きリストを作成するにはどうすればよいですか?

A: Markdownで順序付きリストを作成するには、各リスト項目を数字とそれに続くピリオド（`1.`, `2.`, `3.`）の後にスペースを入れます。

#### Q: Markdown で順序付きリストをネストできますか?

A: はい、ネストされた各リスト項目の前に 4 つのオフセットスペースを追加することで、Markdown で順序付きリストをネストすることができます。

#### Q: 順序付きリストの番号付けをカスタマイズするにはどうすればよいですか?

A: 標準の Markdown では、順序付きリストの番号付けは自動的に生成されます。ただし、一部の Markdown エディターでは、特定の拡張機能を使用してカスタマイズできます。

#### Q: Markdown の順序付きリストはインデントをサポートしていますか?

A: はい、Markdown の順序付きリストはインデントをサポートしています。スペースまたはタブを使用して左シフトを追加できます。

#### Q: リスト項目にリンクやインラインテキストを追加できますか?

A: はい、適切な Markdown 構文を使用して、リスト項目にリンクまたはインライン テキストを追加できます。