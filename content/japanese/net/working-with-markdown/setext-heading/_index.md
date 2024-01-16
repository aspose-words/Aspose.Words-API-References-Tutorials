---
title: セットテキストの見出し
linktitle: セットテキストの見出し
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET のステップバイステップ ガイドで、Setext 見出しを使用してドキュメントを書式設定する方法を学びます。
type: docs
weight: 10
url: /ja/net/working-with-markdown/setext-heading/
---

このチュートリアルでは、Aspose.Words for .NET で Settext Heading 機能を使用する方法を説明します。 Settext Heading は、Markdown ドキュメントのタイトルを書式設定する代替方法です。

## ステップ 1: ドキュメント ジェネレーターを使用する

まず、ドキュメント ジェネレーターを使用してドキュメントにコンテンツを追加します。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
DocumentBuilder builder = new DocumentBuilder();
```

## ステップ 2: Settext 見出しスタイルを使用する

デフォルトの「見出し 1」段落スタイルを使用して、文書内にレベル 1 の見出しを作成します。

```csharp
builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

## ステップ 3: スタイルをリセットする

段落間のスタイルの望ましくない組み合わせを避けるために、以前に適用されたフォント スタイルをリセットします。

```csharp
builder.Font.Bold = false;
builder.Font.Italic = false;
```

## ステップ 4: セットテキストの見出しレベルをカスタマイズする

既存の見出しスタイルに基づいて新しい段落スタイルを追加することで、Setext の見出しレベルをカスタマイズできます。この例では、「見出し 1」スタイルに基づいて「SetextHeading1」スタイルを作成し、Setext 形式のレベル 1 見出しを表します。

```csharp
Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Title Setext level 1");
```

## ステップ 5: ドキュメントを保存する

最後に、ドキュメントを希望の形式で保存できます。

```csharp
builder.Document.Save(dataDir + "Test.md");
```

### Aspose.Words for .NET を使用した Setext タイトルのソース コード例

```csharp
//ドキュメントディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメント ビルダーを使用してドキュメントにコンテンツを追加します。
DocumentBuilder builder = new DocumentBuilder();

builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");

//前の段落のスタイルをリセットして、段落間でスタイルを結合しないようにします。
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Setext Heading level 1");

builder.ParagraphFormat.Style = builder.Document.Styles["Heading 3"];
builder.Writeln("This is an H3 tag");

//前の段落のスタイルをリセットして、段落間でスタイルを結合しないようにします。
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading2 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading2");
builder.ParagraphFormat.Style = setexHeading2;
builder.Document.Styles["SetextHeading2"].BaseStyleName = "Heading 3";

//基本段落の見出しレベルが 2 より大きい場合、Setex 見出しレベルは 2 にリセットされます。
builder.Writeln("Setext Heading level 2");


builder.Document.Save(dataDir + "Test.md");
```

### よくある質問

#### Q: Settext Markdown ヘッダーとは何ですか?

A: Setext Markdown ヘッダーは、Markdown ドキュメントに見出しを作成する別の方法です。アンダースコア文字 (= または -) を使用して、さまざまなレベルの見出しを示します。

#### Q: Settext Markdown ヘッダーの使用方法は?

A: Setext Markdown 見出しを使用するには、タイトル テキストの下にアンダースコアを置きます。レベル 1 ヘッダーには等号 (=) を使用し、レベル 2 ヘッダーにはハイフン (-) を使用します。

#### Q: Settext Markdown ヘッダーの使用に制限はありますか?

A: Settext Markdown 見出しには見出し階層の点で制限があり、標準の Markdown 見出しほど視覚的に区別できません。

#### Q: Settext Markdown ヘッダーの外観をカスタマイズできますか?

A: 標準の Markdown では、Setext Markdown ヘッダーの外観をカスタマイズすることはできません。これらの外観は、使用されるアンダースコア文字に基づいて事前に定義されています。

#### Q: Setext Markdown ヘッダーはすべての Markdown エディターでサポートされていますか?

A: Setext Markdown ヘッダーのサポートは、Markdown エディターによって異なる場合があります。発行元の特定のドキュメントを確認してください。