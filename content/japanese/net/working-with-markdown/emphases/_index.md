---
title: 強調点
linktitle: 強調点
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET で強調 (太字と斜体) を使用する方法をステップ バイ ステップ ガイドで学習します。
type: docs
weight: 10
url: /ja/net/working-with-markdown/emphases/
---

この例では、Aspose.Words for .NET で強調を使用する方法について説明します。強調は、太字や斜体など、テキストの特定の部分を強調するために使用されます。

## ステップ1: ドキュメントの初期化

まず、ドキュメントを初期化するために、`Document`クラス。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## ステップ2: ドキュメントジェネレーターの使用

次に、ドキュメント ジェネレーターを使用してドキュメントにコンテンツを追加します。

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ3: 強調したテキストを追加する

ドキュメント ジェネレーターのフォント プロパティを変更することで、強調テキストを追加できます。この例では、太字と斜体を使用してテキストのさまざまな部分を強調しています。

```csharp
builder.Writeln("Markdown treats asterisks (*) and underscores (_) as emphases indicators.");
builder.Write("You can write");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(".");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("bold and italic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder. Write(".");

```

## ステップ4: ドキュメントを保存する

最後に、ドキュメントを希望の形式で保存します。この例では、`.md` Markdown 形式の拡張子。

```csharp
builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

おめでとうございます。これで、Aspose.Words for .NET で強調を使用する方法を学習しました。

### Aspose.Words for .NET を使用した強調のサンプル ソース コード


```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("Markdown treats asterisks (*) and underscores (_) as indicators of emphases.");
builder.Write("You can write ");

builder.Font.Bold = true;
builder.Write("bold");

builder.Font.Bold = false;
builder.Write(" or ");

builder.Font.Italic = true;
builder.Write("italic");

builder.Font.Italic = false;
builder.Writeln(" text. ");

builder.Write("You can also write ");
builder.Font.Bold = true;

builder.Font.Italic = true;
builder.Write("BoldItalic");

builder.Font.Bold = false;
builder.Font.Italic = false;
builder.Write("text.");

builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

### よくある質問

#### Q: Markdown を使用してテキストを強調表示するにはどうすればよいですか?

A: Markdownを使用してテキストを強調表示するには、テキストを適切な記号で囲むだけです。`*`または`_`斜体の場合、`**`または`__`太字、`~~`取り消し線用。

#### Q: 同じテキスト内で異なるハイライトを組み合わせることはできますか?

 A: はい、同じテキスト内で異なるハイライトを組み合わせることは可能です。例えば、両方を使って単語を太字と斜体にすることができます。`**`そして`*`単語の周り。

#### Q: Markdown ではどのようなハイライトオプションが利用できますか?

A: Markdownで使用できるハイライトオプションは斜体（`*`または`_`）、 大胆な （`**`または`__`）、取り消し線（`~~`）。

#### Q: テキストに Markdown で強調表示に使用される特殊文字が含まれている場合は、どのように対処すればよいですか?

 A: テキストにMarkdownでハイライトに使用される特殊文字が含まれている場合は、その前に`\`。 例えば、`\*`文字どおりのアスタリスクが表示されます。

#### Q: CSS を使用してハイライトの外観をカスタマイズできますか?

A: Markdown でのハイライト表示は通常、ブラウザのデフォルトのスタイルを使用してレンダリングされます。Markdown を HTML に変換すると、CSS ルールを使用してハイライト表示の外観をカスタマイズできます。