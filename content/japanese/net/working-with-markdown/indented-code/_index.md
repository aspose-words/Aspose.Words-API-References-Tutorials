---
title: インデントされたコード
linktitle: インデントされたコード
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET でインデントされたコードを使用する方法をステップバイステップ ガイドで学習します。
type: docs
weight: 10
url: /ja/net/working-with-markdown/indented-code/
---

この例では、Aspose.Words for .NET でインデントされたコード機能を使用する方法について説明します。インデントされたコードは、特定の書式でコード ブロックを視覚的に表現するために使用されます。

## ステップ1: ドキュメントジェネレーターの使用

まず、ドキュメント ジェネレーターを使用してドキュメントにコンテンツを追加します。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## ステップ2: インデントされたコードにスタイルを追加する

インデントされたコードにカスタムスタイルを追加するには、`Styles.Add`方法の`Document`オブジェクト。この例では、インデントされたコード用の「IndentedCode」というスタイルを作成しています。

```csharp
Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
```

## ステップ3: インデントされたコードを追加する

これで、「IndentedCode」カスタム スタイルを使用してインデントされたコード ブロックを追加できます。

```csharp
builder.Writeln("This is an indented code block");
```

### Aspose.Words for .NET を使用したインデントされたコードのサンプル ソース コード

```csharp
//ドキュメント ビルダーを使用してドキュメントにコンテンツを追加します。
DocumentBuilder builder = new DocumentBuilder();

Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
builder.Writeln("This is an indented code");
```

おめでとうございます。これで、Aspose.Words for .NET でインデントされたコード機能を使用する方法を学習しました。


### よくある質問

#### Q: Markdown のインデントされたコードとは何ですか?

A: Markdown のインデントされたコードは、Markdown ドキュメントでコードを表示するために使用される書式設定方法です。コードの各行をスペースまたはタブでインデントします。

#### Q: Markdown でインデントされたコードを使用するにはどうすればよいですか?

A: Markdown でインデントされたコードを使用するには、コードの各行をスペースまたはタブでインデントします。

#### Q: Markdown でインデントされたコードの利点は何ですか?

A: Markdown でインデントされたコードを使用すると、コードの読みやすさが向上し、読者が理解しやすくなります。

#### Q: Markdown のインデントされたコードとコード ブロックの違いは何ですか?

A: インデントされたコードはテキストに挿入される小さなコードスニペットに使用され、コードブロックは大きなコード部分を別の形式で表示するために使用されます。

#### Q: Markdown のインデントされたコードはすべての Markdown エディターでサポートされていますか?

A: Markdown でのインデントされたコードのサポートは、Markdown エディターによって異なる場合があります。発行元の特定のドキュメントを確認してください。