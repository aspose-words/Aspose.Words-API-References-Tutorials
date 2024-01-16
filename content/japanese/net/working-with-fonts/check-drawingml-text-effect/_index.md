---
title: DrawingML テキスト効果を確認する
linktitle: DrawingML テキスト効果を確認する
second_title: Aspose.Words ドキュメント処理 API
description: このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の DrawingML テキスト効果を確認する方法を学びます。
type: docs
weight: 10
url: /ja/net/working-with-fonts/check-drawingml-text-effect/
---

このチュートリアルでは、Aspose.Words Library for .NET を使用して Word 文書内の DrawingML テキスト効果を確認する方法を説明します。 DrawingML テキスト効果をチェックすると、特定の効果がテキストの一部に適用されているかどうかを判断できます。 .NET プロジェクトのコードを理解して実装できるように、段階的に説明します。

## 前提条件
始める前に、次のものが揃っていることを確認してください。
- C# プログラミング言語に関する実践的な知識
- プロジェクトにインストールされた .NET 用の Aspose.Words ライブラリ
- DrawingML テキスト効果を含む Word 文書

## ステップ 1: ドキュメント ディレクトリを定義する
まず、Word 文書の場所へのディレクトリ パスを設定する必要があります。交換する`"YOUR DOCUMENT DIRECTORY"`コード内で適切なパスを指定します。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## ステップ 2: ドキュメントをロードしてテキスト効果を確認する
次に、Word 文書をロードし、文書本文の最初の段落にあるラン (文字シーケンス) のコレクションにアクセスします。次に、特定の DrawingML テキスト効果が最初の実行のフォントに適用されているかどうかを確認します。

```csharp
//ドキュメントをロードします
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

### Aspose.Words for .NET を使用した Check DMLText Effect のサンプル ソース コード 

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
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の DrawingML テキスト効果を確認する方法を説明しました。 DrawingML のテキスト効果をチェックすると、特定の効果が適用されているテキストの部分を特定できます。この機能を自由に使用して、Word 文書内のテキスト効果を操作および分析できます。

### よくある質問

#### Q: Aspose.Words を使用して Word 文書内の DrawingML テキスト効果にアクセスするにはどうすればよいですか?

A: Aspose.Words を使用すると、提供された API を使用して Word ドキュメント内の DrawingML テキスト効果にアクセスできます。テキスト要素を参照し、色やサイズなどのテキスト効果の特定のプロパティを確認できます。

#### Q: Word 文書ではどのような種類の DrawingML テキスト効果が一般的に使用されますか?

A: Word 文書で一般的に使用される DrawingML テキスト効果には、影、反射、光彩、グラデーションなどが含まれます。これらの効果を適用すると、テキストの外観や書式を改善できます。

#### Q: Word 文書内の DrawingML テキスト効果の色を確認するにはどうすればよいですか?

A: Word 文書内の DrawingML テキスト効果の色を確認するには、Aspose.Words が提供するメソッドを使用して、テキスト効果の色のプロパティにアクセスします。このようにして、特定のテキスト効果に使用される色を取得できます。

#### Q: 複数のセクションを含む Word 文書のテキスト効果を確認することはできますか?

A: はい、Aspose.Words を使用すると、複数のセクションを含む Word 文書のテキスト効果をチェックできます。ドキュメントの各セクションに移動し、各セクションのテキスト効果に個別にアクセスできます。

#### Q: Word 文書内の DrawingML テキスト効果の不透明度を確認するにはどうすればよいですか?

A: Word 文書内の DrawingML テキスト効果の不透明度を確認するには、Aspose.Words が提供するメソッドを使用して、テキスト効果の不透明度プロパティにアクセスします。これにより、特定のテキスト効果に適用される不透明度の値を取得できるようになります。