---
title: 水平線
linktitle: 水平線
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して水平線を挿入する方法をステップバイステップ ガイドで学習します。
type: docs
weight: 10
url: /ja/net/working-with-markdown/horizontal-rule/
---

この例では、Aspose.Words for .NET で水平線機能を使用する方法を説明します。水平線は、ドキュメントのセクションを視覚的に区切るために使用されます。

## ステップ1: ドキュメントジェネレーターの使用

まず、ドキュメント ジェネレーターを使用してドキュメントにコンテンツを追加します。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## ステップ2: 水平線を挿入する

水平線を挿入するには、`InsertHorizontalRule`ドキュメントジェネレーターのメソッド。

```csharp
builder. InsertHorizontalRule();
```

## Aspose.Words for .NET を使用した水平線のサンプル ソース コード

```csharp
//ドキュメント ビルダーを使用してドキュメントにコンテンツを追加します。
DocumentBuilder builder = new DocumentBuilder();

//水平線を挿入します。
builder.InsertHorizontalRule();
```

おめでとうございます！これで、Aspose.Words for .NET で水平線機能を使用する方法を学習しました。


### よくある質問

#### Q: Markdown で水平ルーラーを作成するにはどうすればよいですか?

A: Markdownで水平ルーラーを作成するには、空白行に次の記号のいずれかを使用します: 3つのアスタリスク(\***）、3つのダッシュ（\---）、または3つのアンダースコア（\___）。

#### Q: Markdown で水平ルーラーの外観をカスタマイズできますか?

A: 標準の Markdown では、水平ルーラーの外観をカスタマイズする方法はありません。ただし、一部の高度な Markdown エディターと拡張機能では、追加のカスタマイズ機能が提供されています。

#### Q: 水平ルーラーはすべての Markdown エディターでサポートされていますか?

A: はい、ほとんどの一般的な Markdown エディターは水平ルーラーをサポートしています。ただし、サポートされているかどうかを確認するには、特定のベンダーのドキュメントを確認することをお勧めします。

#### Q: Markdown で他にどのような要素を作成できますか?

A: 水平ルーラーに加えて、Markdown ではタイトル、段落、リスト、リンク、画像、表などを作成できます。