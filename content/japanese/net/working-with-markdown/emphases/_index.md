---
title: 強調
linktitle: 強調
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET で強調記号 (太字と斜体) を使用する方法については、ステップバイステップ ガイドをご覧ください。
type: docs
weight: 10
url: /ja/net/working-with-markdown/emphases/
---

この例では、Aspose.Words for .NET で強調を使用する方法を説明します。 emphases は、太字や斜体など、テキストの特定の部分を強調するために使用されます。

## ステップ 1: ドキュメントの初期化

まず、のインスタンスを作成してドキュメントを初期化します。`Document`クラス。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
```

## ステップ 2: ドキュメント ジェネレーターを使用する

次に、ドキュメント ジェネレーターを使用してドキュメントにコンテンツを追加します。

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ 3: Emphases でテキストを追加する

ドキュメント ジェネレーターのフォント プロパティを変更することで、強調テキストを追加できます。この例では、テキストのさまざまな部分を強調するために太字と斜体を使用しています。

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

## ステップ 4: ドキュメントを保存する

最後に、ドキュメントを希望の形式で保存できます。この例では、`.md` Markdown形式の拡張子。

```csharp
builder.Document.Save(dataDir + "WorkingWithMarkdown.Emphases.md");
```

おめでとうございます！これで、Aspose.Words for .NET で強調を使用する方法を学習しました。

### Aspose.Words for .NET を使用した Emphases のソース コードの例


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

A: Markdown を使用してテキストを強調表示するには、テキストを適切な記号で囲むだけです。使用`*`または`_`イタリック体の場合、`**`または`__`太字の場合、および`~~`取り消し線用。

#### Q: 同じテキスト内で異なるハイライトを組み合わせることはできますか?

 A: はい、同じテキスト内で異なるハイライトを組み合わせることができます。たとえば、両方を使用すると、単語を太字にしたり斜体にしたりできます。`**`そして`*`という言葉の周りに。

#### Q: Markdown ではどのような強調表示オプションが利用できますか?

A: Markdown で使用できる強調表示オプションは斜体 (`*`または`_`）、 大胆な （`**`または`__`)、および取り消し線 (`~~`）。

#### Q: テキストに Markdown で強調表示に使用される特殊文字が含まれている場合は、どのように処理すればよいですか?

 A: テキストにマークダウンで強調表示に使用される特殊文字が含まれている場合は、文字の前に`\`。例えば、`\*`リテラルのアスタリスクが表示されます。

#### Q: CSS を使用してハイライトの外観をカスタマイズできますか?

A: Markdown での強調表示は通常、ブラウザーのデフォルト スタイルを使用してレンダリングされます。 Markdown を HTML に変換すると、CSS ルールを使用して強調表示の外観をカスタマイズできます。