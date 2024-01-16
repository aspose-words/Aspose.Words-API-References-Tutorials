---
title: 横罫
linktitle: 横罫
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET のステップバイステップ ガイドを使用して水平罫線を挿入する方法を学びます。
type: docs
weight: 10
url: /ja/net/working-with-markdown/horizontal-rule/
---

この例では、Aspose.Words for .NET で水平罫線機能を使用する方法を示します。水平罫線は、文書のセクションを視覚的に区切るために使用されます。

## ステップ 1: ドキュメント ジェネレーターを使用する

まず、ドキュメント ジェネレーターを使用してドキュメントにコンテンツを追加します。

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## ステップ 2: 横罫線を挿入する

を使用して水平罫線を挿入できます。`InsertHorizontalRule`ドキュメントジェネレーターのメソッド。

```csharp
builder. InsertHorizontalRule();
```

## Aspose.Words for .NET を使用した水平罫線のサンプル ソース コード

```csharp
//ドキュメント ビルダーを使用してドキュメントにコンテンツを追加します。
DocumentBuilder builder = new DocumentBuilder();

//横罫線を挿入します。
builder.InsertHorizontalRule();
```

おめでとうございます！これで、Aspose.Words for .NET で水平罫線機能を使用する方法を学習しました。


### よくある質問

#### Q: Markdown で水平ルーラーを作成するにはどうすればよいですか?

A: Markdown で水平ルーラーを作成するには、空の行に次のいずれかの記号を使用できます: 3 つのアスタリスク (\***)、ダッシュ 3 つ (\---)、または 3 つのアンダースコア (\___）。

#### Q: Markdown で水平ルーラーの外観をカスタマイズできますか?

A: 標準の Markdown では、水平ルーラーの外観をカスタマイズする方法はありません。ただし、一部の高度な Markdown エディターと拡張機能は追加のカスタマイズ機能を提供します。

#### Q: 水平ルーラーはすべての Markdown エディターでサポートされていますか?

A: はい、ほとんどの一般的な Markdown エディターは水平ルーラーをサポートしています。ただし、特定のベンダーのドキュメントを参照して、それがサポートされていることを確認することが常に最善です。

#### Q: Markdown では他にどのような要素を作成できますか?

A: 水平ルーラーに加えて、Markdown ではタイトル、段落、リスト、リンク、画像、表などを作成できます。