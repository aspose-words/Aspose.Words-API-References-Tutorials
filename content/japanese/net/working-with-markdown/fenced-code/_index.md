---
title: フェンスコード
linktitle: フェンスコード
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET でフェンス コード機能を使用する方法をステップ バイ ステップ ガイドで学習します。
type: docs
weight: 10
url: /ja/net/working-with-markdown/fenced-code/
---

この例では、Aspose.Words for .NET でフェンス コード機能を使用する方法について説明します。フェンス コードは、特定の書式でコード ブロックを表すために使用されます。

## ステップ1: ドキュメントジェネレーターの使用

まず、ドキュメント ジェネレーターを使用してドキュメントにコンテンツを追加します。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## ステップ2: フェンスコードにスタイルを追加する

フェンスコードにカスタムスタイルを追加するには、`Styles.Add`方法の`Document`オブジェクト。この例では、フェンス コード用に「FencedCode」というスタイルを作成しています。

```csharp
Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
```

## ステップ3: 情報なしでフェンスコードを追加する

これで、「FencedCode」カスタム スタイルを使用して、情報文字列のないフェンス コード ブロックを追加できるようになりました。

```csharp
builder.Writeln("This is an fenced code");
```

## ステップ4: 情報文字列を含むフェンスコードを追加する

別のカスタム スタイルを使用して、情報の文字列を含むフェンス コード ブロックを追加することもできます。この例では、C# コードのブロックを表す「FencedCode.C#」というスタイルを作成しています。

```csharp
Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### Aspose.Words for .NET を使用したフェンス コードのサンプル ソース コード

```csharp
//ドキュメント ビルダーを使用してドキュメントにコンテンツを追加します。
DocumentBuilder builder = new DocumentBuilder();

Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
builder.Writeln("This is an fenced code");

Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### よくある質問

#### Q: Markdown の区切りコードとは何ですか?

A: Markdown の区切りコードは、Markdown ドキュメントでコードを表示するために使用される書式設定方法です。特定の区切り文字を使用してコードを囲みます。

#### Q: Markdown での区切りコードの利点は何ですか?

A: Markdown で区切られたコードを使用すると、コードの可読性が向上し、読者が理解しやすくなります。また、一部の Markdown エディターで構文の強調表示を維持することもできます。

#### Q: Markdown における区切りコードとインデントコードの違いは何ですか?

A: 区切りコードでは特定の区切り文字を使用してコードを囲みますが、インデントコードでは各コード行をスペースまたはタブでインデントします。

#### Q: Markdown の区切りコードはすべての Markdown エディターでサポートされていますか?

A: Markdown での区切りコードのサポートは、Markdown エディターによって異なる場合があります。発行元の特定のドキュメントを確認してください。

