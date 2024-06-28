---
title: インデントされたコード
linktitle: インデントされたコード
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET のステップバイステップ ガイドでインデントされたコードを使用する方法を学びます。
type: docs
weight: 10
url: /ja/net/working-with-markdown/indented-code/
---

この例では、Aspose.Words for .NET でインデント コード機能を使用する方法を説明します。インデントされたコードは、特定の書式設定でコードのブロックを視覚的に表現するために使用されます。

## ステップ 1: ドキュメント ジェネレーターを使用する

まず、ドキュメント ジェネレーターを使用してドキュメントにコンテンツを追加します。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## ステップ 2: 指定されたコードのスタイルを追加する

を使用して、インデントされたコードのカスタム スタイルを追加します。`Styles.Add`の方法`Document`物体。この例では、インデントされたコード用に「IndentedCode」というスタイルを作成します。

```csharp
Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
```

## ステップ 3: 指定されたコードを追加する

これで、「IndentedCode」カスタム スタイルを使用してインデントされたコード ブロックを追加できるようになりました。

```csharp
builder.Writeln("This is an indented code block");
```

### Aspose.Words for .NET を使用したインデントされたコードのソース コード例

```csharp
//ドキュメント ビルダーを使用してドキュメントにコンテンツを追加します。
DocumentBuilder builder = new DocumentBuilder();

Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
builder.Writeln("This is an indented code");
```

おめでとうございます！これで、Aspose.Words for .NET でインデントされたコード機能を使用する方法を学習しました。


### よくある質問

#### Q:Markdownで指定するコードとは何ですか?

A: Markdown のインデント コードは、Markdown ドキュメント内のコードを表示するために使用される書式設定方法です。これは、コードの各行をスペースまたはタブでインデントすることで構成されます。

#### Q: Markdown でインデントされたコードを使用するにはどうすればよいですか?

A: Markdown でインデントされたコードを使用するには、コードの各行をスペースまたはタブでインデントします。

#### Q: Markdown でインデントされたコードの利点は何ですか?

A: Markdown のコードをインデントすると、コードの可読性が向上し、読者が理解しやすくなります。

#### Q: Markdown のインデントされたコードとコード ブロックの違いは何ですか?

A: インデントされたコードはテキストに挿入される小さなコード スニペットに使用され、コード ブロックは大きなコード部分を別の形式で表示するために使用されます。

#### Q: Markdown のインデントされたコードはすべての Markdown エディターでサポートされていますか?

A: Markdown でのインデントされたコードのサポートは、Markdown エディターによって異なる場合があります。発行元の特定のドキュメントを確認してください。