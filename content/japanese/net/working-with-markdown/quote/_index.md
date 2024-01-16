---
title: 引用
linktitle: 引用
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET で引用符を使用する方法については、ステップバイステップ ガイドをご覧ください。
type: docs
weight: 10
url: /ja/net/working-with-markdown/quote/
---

この例では、Aspose で引用機能を使用する方法を説明します。Words for .NET 引用は、テキストのセクションを特別な境界線で囲んで強調表示するために使用されます。

## ステップ 1: ドキュメント ジェネレーターを使用する

まず、ドキュメント ジェネレーターを使用してドキュメントにコンテンツを追加します。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## ステップ 2: デフォルトの引用スタイルの使用

「引用」というデフォルトの段落スタイルを使用して、テキストに引用の書式設定を適用します。

```csharp
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");
```

## ステップ 3: ネストされたレベルのスタイルを作成する

を使用して、ネストされたレベルのスタイルを作成できます。`Styles.Add`の方法`Document`物体。この例では、ネストされた見積レベルを表す「Quote1」というスタイルを作成しています。

```csharp
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

### Aspose.Words for .NET を使用した引用のソース コードの例


```csharp
//ドキュメント ビルダーを使用してドキュメントにコンテンツを追加します。
DocumentBuilder builder = new DocumentBuilder();

//デフォルトでは、ドキュメントには第 1 レベルのブロック引用スタイルが保存されます。
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");

//スタイルの継承を通じて、ネストされたレベルのスタイルを作成します。
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

おめでとうございます！ Aspose.Words for .NET で引用機能を使用する方法を学習しました。


### よくある質問

#### Q: Markdown における引用とは何ですか?

A: Markdown での引用は、他のソースからのテキストの一節を強調表示したり、有名な引用を参照したりする方法です。

#### Q: Markdown で引用符を使用するにはどうすればよいですか?

A: Markdown で引用を使用するには、引用のテキストを山括弧 (`>`）。引用の各行は山形文字で始める必要があります。

#### Q: マークダウン引用符は属性をサポートしていますか?

A: マークダウン引用は特定の属性をサポートしません。これらは、引用されたテキストの書式設定によって単に強調表示されます。

#### Q: Markdown に引用符を埋め込むことはできますか?

A: はい、追加レベルの山括弧 (`>`）。