---
title: フェンスで囲まれたコード
linktitle: フェンスで囲まれたコード
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET のステップバイステップ ガイドでフェンス コード機能を使用する方法を学びます。
type: docs
weight: 10
url: /ja/net/working-with-markdown/fenced-code/
---

この例では、Aspose.Words for .NET でフェンスされたコード機能を使用する方法を説明します。フェンスで囲まれたコードは、特定の形式のコード ブロックを表すために使用されます。

## ステップ 1: ドキュメント ジェネレーターを使用する

まず、ドキュメント ジェネレーターを使用してドキュメントにコンテンツを追加します。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## ステップ 2: フェンスで囲まれたコードのスタイルを追加する

を使用して、フェンスで囲まれたコードのカスタム スタイルを追加します。`Styles.Add`の方法`Document`物体。この例では、フェンスで囲まれたコード用に「FencedCode」というスタイルを作成します。

```csharp
Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
```

## ステップ 3: 情報なしでフェンスで囲まれたコードを追加する

これで、「FencedCode」カスタム スタイルを使用して、情報文字列のないフェンスで囲まれたコード ブロックを追加できるようになりました。

```csharp
builder.Writeln("This is an fenced code");
```

## ステップ 4: 情報文字列を含むフェンスされたコードを追加する

別のカスタム スタイルを使用して、情報の文字列を含むフェンスで囲まれたコード ブロックを追加することもできます。この例では、C# コードのブロックを表す「FencedCode.C#」というスタイルを作成しています。

```csharp
Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### Aspose.Words for .NET を使用したフェンス コードのソース コード例

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

#### Q: Markdown の区切り文字で区切られたコードとは何ですか?

A: Markdown の区切りコードは、Markdown ドキュメント内のコードを表示するために使用される書式設定方法です。これは、コードを特定の区切り文字で構成することで構成されます。

#### Q: Markdown で区切られたコードの利点は何ですか?

A: Markdown で区切られたコードにより、コードの可読性が向上し、読者が理解しやすくなります。また、一部の Markdown エディターで構文の強調表示を保持することもできます。

#### Q: Markdown の区切りコードとインデントコードの違いは何ですか?

A: 区切りコードでは特定の区切り文字を使用してコードを囲みますが、インデント コードではコードの各行をスペースまたはタブでインデントします。

#### Q: Markdown の区切り文字で区切られたコードは、すべての Markdown エディターでサポートされていますか?

A: Markdown での区切りコードのサポートは、Markdown エディターによって異なる場合があります。発行元の特定のドキュメントを確認してください。

