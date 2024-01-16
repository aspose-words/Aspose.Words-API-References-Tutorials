---
title: 箇条書きリスト
linktitle: 箇条書きリスト
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET のステップバイステップ ガイドを使用して箇条書きリストを作成する方法を学びます。
type: docs
weight: 10
url: /ja/net/working-with-markdown/bulleted-list/
---

このチュートリアルでは、Aspose.Words for .NET を使用して箇条書きリストを作成する方法を説明します。箇条書きリストは、番号を使用せずに項目をリストするために使用されます。

## ステップ 1: ドキュメント ジェネレーターを使用する

まず、ドキュメント ジェネレーターを使用してドキュメントにコンテンツを追加します。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## ステップ 2: デフォルトの箇条書きリストを適用する

ドキュメントビルダーの機能を使用して、デフォルトの箇条書きリストを適用できます。`ApplyBulletDefault`方法。

```csharp
builder.ListFormat.ApplyBulletDefault();
```

## ステップ 3: 箇条書きの形式をカスタマイズする

のプロパティにアクセスして箇条書き形式をカスタマイズできます。`ListFormat.List.ListLevels[0]`。この例では、ダッシュ「-」を箇条書きとして使用します。

```csharp
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";
```

## ステップ 4: リストに項目を追加する

これで、ドキュメントビルダーを使用して箇条書きリストに項目を追加できるようになりました。`Writeln`方法。

```csharp
builder. Writen("Element 1");
builder. Writen("Element 2");
```

## ステップ 5: リストからインデントを削除する

サブリストを作成したい場合は、`ListFormat.ListIndent()`方法。この例では、アイテム 2a と 2b にサブリストを追加しています。

```csharp
builder.ListFormat.ListIndent();
builder. Writeln("Element 2a");
builder.Writeln("Element 2b");
```
### Aspose.Words for .NET を使用した箇条書きリストのソース コード例


```csharp
//ドキュメント ビルダーを使用してドキュメントにコンテンツを追加します。
DocumentBuilder builder = new DocumentBuilder();

builder.ListFormat.ApplyBulletDefault();
builder.ListFormat.List.ListLevels[0].NumberFormat = "-";

builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();

builder.Writeln("Item 2a");
builder.Writeln("Item 2b");
```

おめでとうございます！ Aspose.Words for .NET を使用して箇条書きリストを作成する方法を学習しました。

### よくある質問

#### Q: Markdown で箇条書きリストを作成するにはどうすればよいですか?

A: Markdown で箇条書きリストを作成するには、各リスト項目を箇条書き記号 (`-`, `*` 、 または`+`)、その後にスペースが続きます。

#### Q: Markdown で箇条書きリストをネストできますか?

A: はい、マークダウンで箇条書きリストをネストするには、ネストされた各リスト項目の前に 4 つのオフセット スペースを追加します。

#### Q: 箇条書き記号をカスタマイズするにはどうすればよいですか?

A: 標準の Markdown では、箇条書き記号が事前に定義されています。ただし、一部の Markdown エディターでは、特定の拡張機能を使用してカスタマイズできます。

#### Q: Markdown の箇条書きリストはインデントをサポートしていますか?

A: はい、Markdown の箇条書きリストはインデントをサポートしています。スペースまたはタブを使用して左シフトを追加できます。

#### Q: リンクまたはインライン テキストをリスト アイテムに追加できますか?

A: はい、適切な Markdown 構文を使用して、リスト項目にリンクまたはインライン テキストを追加できます。
