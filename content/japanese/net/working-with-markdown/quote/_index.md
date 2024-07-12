---
title: 引用
linktitle: 引用
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET で quote を使用する方法をステップバイステップ ガイドで学習します。
type: docs
weight: 10
url: /ja/net/working-with-markdown/quote/
---

この例では、Aspose.Words for .NET の引用機能を使用する方法について説明します。引用機能は、テキストのセクションを特別な境界線で囲んで強調表示するために使用されます。

## ステップ1: ドキュメントジェネレーターの使用

まず、ドキュメント ジェネレーターを使用してドキュメントにコンテンツを追加します。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## ステップ2: デフォルトの引用スタイルを使用する

「引用」というデフォルトの段落スタイルを使用して、テキストに引用書式を適用します。

```csharp
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");
```

## ステップ3: ネストされたレベルのスタイルを作成する

ネストされたレベルのスタイルを作成するには、`Styles.Add`方法の`Document`オブジェクト。この例では、ネストされた引用レベルを表す「Quote1」というスタイルを作成しています。

```csharp
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

### Aspose.Words for .NET を使用した引用のサンプル ソース コード


```csharp
//ドキュメント ビルダーを使用してドキュメントにコンテンツを追加します。
DocumentBuilder builder = new DocumentBuilder();

//デフォルトでは、ドキュメントは最初のレベルに blockquote スタイルを保存します。
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");

//スタイルの継承を通じてネストされたレベルのスタイルを作成します。
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

おめでとうございます。これで、Aspose.Words for .NET で引用機能を使用する方法を学習しました。


### よくある質問

#### Q: Markdown における引用とは何ですか?

A: Markdown での引用は、他のソースからのテキストの一部を強調表示したり、有名な引用を参照したりするための方法です。

#### Q: Markdown で引用符を使用するにはどうすればいいですか?

A: Markdownで引用符を使用するには、引用符のテキストを山括弧（`>`）。引用の各行は必ずシェブロンで始まる必要があります。

#### Q: Markdown 引用符は属性をサポートしていますか?

A: Markdown 引用では特定の属性はサポートされません。引用されたテキストの書式によって強調表示されるだけです。

#### Q: Markdown に引用符を埋め込むことはできますか?

A: はい、Markdownでは山括弧を追加することで引用符をネストすることが可能です（`>`）。