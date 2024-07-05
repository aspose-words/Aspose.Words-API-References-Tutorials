---
title: チェックDrawingMLテキスト効果
linktitle: チェックDrawingMLテキスト効果
second_title: Aspose.Words ドキュメント処理 API
description: このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の DrawingML テキスト効果を確認する方法を学習します。
type: docs
weight: 10
url: /ja/net/working-with-fonts/check-drawingml-text-effect/
---

このチュートリアルでは、Aspose.Words Library for .NET を使用して Word 文書内の DrawingML テキスト効果を確認する方法について説明します。DrawingML テキスト効果を確認すると、特定の効果がテキストの一部に適用されているかどうかを判断できます。.NET プロジェクトでコードを理解して実装できるように、手順を追って説明します。

## 前提条件
始める前に、次のものが揃っていることを確認してください。
- C#プログラミング言語の実用的な知識
- プロジェクトにインストールされた .NET 用の Aspose.Words ライブラリ
- DrawingML テキスト効果を含む Word 文書

## ステップ1: ドキュメントディレクトリを定義する
まず、Word文書の場所にディレクトリパスを設定する必要があります。`"YOUR DOCUMENT DIRECTORY"`コード内に適切なパスを追加します。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ2: ドキュメントを読み込み、テキスト効果を確認する
次に、Word 文書を読み込み、文書本文の最初の段落にある一連の文字列 (文字シーケンス) にアクセスします。次に、最初の文字列のフォントに特定の DrawingML テキスト効果が適用されているかどうかを確認します。

```csharp
//ドキュメントを読み込む
Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// DrawingML テキスト効果を確認する
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));
```

### Aspose.Words for .NET を使用して DML テキスト効果をチェックするためのサンプル ソース コード 

```csharp

//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "DrawingML text effects.docx");
RunCollection runs = doc.FirstSection.Body.FirstParagraph.Runs;
Font runFont = runs[0].Font;

// 回の実行で複数の Dml テキスト効果が適用される場合があります。
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Shadow));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Effect3D));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Reflection));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Outline));
Console.WriteLine(runFont.HasDmlEffect(TextDmlEffect.Fill));

```

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の DrawingML テキスト効果を確認する方法を説明しました。DrawingML テキスト効果を確認すると、特定の効果が適用されているテキスト部分を識別できます。この機能を使用して、Word 文書内のテキスト効果を自由に操作および分析してください。

### よくある質問

#### Q: Aspose.Words を使用して Word 文書内の DrawingML テキスト効果にアクセスするにはどうすればよいでしょうか?

A: Aspose.Words では、提供されている API を使用して Word 文書内の DrawingML テキスト効果にアクセスできます。テキスト要素を参照し、色、サイズなどのテキスト効果の特定のプロパティを確認できます。

#### Q: Word 文書ではどのような種類の DrawingML テキスト効果がよく使用されますか?

A: Word 文書でよく使用される DrawingML テキスト効果の種類には、影、反射、輝き、グラデーションなどがあります。これらの効果を適用して、テキストの外観と書式設定を改善できます。

#### Q: Word 文書内の DrawingML テキスト効果の色を確認するにはどうすればよいですか?

A: Word 文書内の DrawingML テキスト効果の色を確認するには、Aspose.Words が提供するメソッドを使用して、テキスト効果の色のプロパティにアクセスします。この方法で、特定のテキスト効果に使用されている色を取得できます。

#### Q: 複数のセクションを含む Word 文書内のテキスト効果を確認することはできますか?

A: はい、Aspose.Words では、複数のセクションを含む Word 文書のテキスト効果をチェックできます。文書の各セクションを移動し、各セクションのテキスト効果に個別にアクセスできます。

#### Q: Word 文書内の DrawingML テキスト効果の不透明度を確認するにはどうすればよいですか?

A: Word 文書内の DrawingML テキスト効果の不透明度を確認するには、Aspose.Words が提供するメソッドを使用して、テキスト効果の不透明度プロパティにアクセスします。これにより、特定のテキスト効果に適用されている不透明度の値を取得できます。