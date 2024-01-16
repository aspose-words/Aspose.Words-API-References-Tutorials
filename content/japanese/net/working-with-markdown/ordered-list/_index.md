---
title: 順序付きリスト
linktitle: 順序付きリスト
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して順序付きリストを作成する方法について説明するステップバイステップ ガイドです。
type: docs
weight: 10
url: /ja/net/working-with-markdown/ordered-list/
---

この例では、Aspose.Words for .NET で順序付きリスト機能を使用する方法を説明します。順序付きリストを使用すると、項目を番号で順番に整理できます。

## ステップ 1: ドキュメント ジェネレーターを使用する

まず、ドキュメント ジェネレーターを使用して新しいドキュメントを作成します。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ 2: 順序付きリスト形式を適用する

ドキュメントビルダーのを使用して順序付きリスト形式を適用します。`ApplyBulletDefault`方法。リスト レベルに移動して必要な形式を設定することで、番号付け形式をカスタマイズすることもできます。

```csharp
builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = $"{(char) 0}.";
builder.ListFormat.List.ListLevels[1].NumberFormat = $"{(char) 1}.";
```

## ステップ 3: リストに項目を追加する

ドキュメント ジェネレーターを使用してリストに項目を追加できます。`Writeln`方法。

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## ステップ 4: リストをインデントする

ドキュメントジェネレーターを使用してリストをインデントできます。`ListIndent`方法。

```csharp
builder.ListFormat.ListIndent();
builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

## ステップ 5: ドキュメントを保存する

最後に、ドキュメントを希望の形式で保存できます。

### Aspose.Words for .NET を使用した順序付きリストのソース コードの例

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

おめでとうございます！これで、Aspose.Words for .NET で順序付きリスト機能を使用する方法を学習しました。


### よくある質問

#### Q: Markdown で順序付きリストを作成するにはどうすればよいですか?

A: Markdown で順序付きリストを作成するには、各リスト項目を数字で始め、その後にピリオド (`1.`, `2.`, `3.`)、その後にスペースが続きます。

#### Q: Markdown で順序付きリストをネストできますか?

A: はい。Markdown では、ネストされたリストの各項目の前に 4 つのオフセット スペースを追加することで、順序付きリストをネストすることができます。

#### Q: 順序付きリストの番号付けをカスタマイズするにはどうすればよいですか?

A: 標準の Markdown では、順序付きリストの番号付けが自動的に生成されます。ただし、一部の Markdown エディターでは、特定の拡張機能を使用してカスタマイズできます。

#### Q: Markdown の順序付きリストはインデントをサポートしていますか?

A: はい、Markdown の順序付きリストはインデントをサポートしています。スペースまたはタブを使用して左シフトを追加できます。

#### Q: リンクまたはインライン テキストをリスト アイテムに追加できますか?

A: はい、適切な Markdown 構文を使用して、リスト項目にリンクまたはインライン テキストを追加できます。