---
title: セテキスト見出し
linktitle: セテキスト見出し
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET のステップバイステップ ガイドで、Setext 見出しを使用してドキュメントをフォーマットする方法を学びます。
type: docs
weight: 10
url: /ja/net/working-with-markdown/setext-heading/
---

このチュートリアルでは、Aspose.Words for .NET で Setext 見出し機能を使用する方法について説明します。Setext 見出しは、Markdown ドキュメントでタイトルをフォーマットする代替方法です。

## ステップ1: ドキュメントジェネレーターの使用

まず、ドキュメント ジェネレーターを使用してドキュメントにコンテンツを追加します。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
DocumentBuilder builder = new DocumentBuilder();
```

## ステップ2: Setext見出しスタイルの使用

デフォルトの「見出し 1」段落スタイルを使用して、ドキュメントにレベル 1 の見出しを作成します。

```csharp
builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

## ステップ3: スタイルのリセット

段落間でのスタイルの不要な組み合わせを回避するために、以前に適用されたフォント スタイルをリセットします。

```csharp
builder.Font.Bold = false;
builder.Font.Italic = false;
```

## ステップ4: Setextの見出しレベルのカスタマイズ

既存の見出しスタイルに基づいて新しい段落スタイルを追加することで、Setext の見出しレベルをカスタマイズできます。この例では、「見出し 1」スタイルに基づいて「SetextHeading1」スタイルを作成し、Setext 形式のレベル 1 の見出しを表します。

```csharp
Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Title Setext level 1");
```

## ステップ5: ドキュメントを保存する

最後に、ドキュメントを希望の形式で保存できます。

```csharp
builder.Document.Save(dataDir + "Test.md");
```

### Aspose.Words for .NET を使用した Setext タイトルのサンプル ソース コード

```csharp
//ドキュメント ディレクトリへのパス。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//ドキュメント ビルダーを使用してドキュメントにコンテンツを追加します。
DocumentBuilder builder = new DocumentBuilder();

builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");

//段落間でスタイルが結合されないように、前の段落のスタイルをリセットします。
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Setext Heading level 1");

builder.ParagraphFormat.Style = builder.Document.Styles["Heading 3"];
builder.Writeln("This is an H3 tag");

//段落間でスタイルが結合されないように、前の段落のスタイルをリセットします。
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

#### Q: Setext Markdown ヘッダーとは何ですか?

A: Setext Markdown ヘッダーは、Markdown ドキュメントで見出しを作成する別の方法です。アンダースコア文字 (= または -) を使用して、見出しの異なるレベルを示します。

#### Q: Setext Markdown ヘッダーを使用するにはどうすればよいですか?

A: Setext Markdown の見出しを使用するには、タイトル テキストの下にアンダースコアを配置します。レベル 1 のヘッダーには等号 (=) を使用し、レベル 2 のヘッダーにはハイフン (-) を使用します。

#### Q: Setext Markdown ヘッダーの使用には制限がありますか?

A: Setext Markdown の見出しには見出し階層の点で制限があり、標準の Markdown の見出しほど視覚的に区別できません。

#### Q: Setext Markdown ヘッダーの外観をカスタマイズできますか?

A: 標準の Markdown では、Setext Markdown ヘッダーの外観をカスタマイズすることはできません。使用されているアンダースコア文字に基づいて、外観が事前に定義されています。

#### Q: Setext Markdown ヘッダーはすべての Markdown エディターでサポートされていますか?

A: Setext Markdown ヘッダーのサポートは、Markdown エディターによって異なる場合があります。発行元の特定のドキュメントを確認してください。