---
title: Word文書の横罫線の形式
linktitle: Word文書の横罫線の形式
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して Word 文書の水平罫線を書式設定する方法を学びます。ステップバイステップのガイド。
type: docs
weight: 10
url: /ja/net/add-content-using-documentbuilder/horizontal-rule-format/
---
この包括的な例では、Aspose.Words for .NET を使用して Word 文書内の水平罫線を書式設定する方法を学習します。プロセスを案内し、必要な C# コード スニペットを提供します。このガイドを終えると、水平罫線の配置、幅、高さ、色、その他のプロパティをカスタマイズできるようになります。

## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
- Aspose.Words for .NET ライブラリがシステムにインストールされています。

## ステップ 1: DocumentBuilder を作成し、水平罫線を挿入する
まず、DocumentBuilder オブジェクトを作成し、InserthorizontalRule メソッドを使用して水平罫線を挿入します。

```csharp
DocumentBuilder builder = new DocumentBuilder();
Shape shape = builder.InsertHorizontalRule();
```

## ステップ 2: 横罫線フォーマットにアクセスする
次に、Shape オブジェクトの horizontalRuleFormat プロパティにアクセスして、書式設定オプションを取得します。

```csharp
HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
```

## ステップ 3: 書式設定オプションをカスタマイズする
水平罫線のさまざまな書式設定オプションをカスタマイズできるようになりました。たとえば、配置、幅、高さ、色、シェーディングを調整できます。

```csharp
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;
```

## ステップ 4: ドキュメントを保存する
水平罫線の書式を設定した後、Document オブジェクトの Save メソッドを使用してドキュメントをファイルに保存します。

```csharp
builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

### Aspose.Words for .NET を使用した水平罫線形式のソース コード例
Aspose.Words for .NET を使用して水平罫線をフォーマットするための完全なソース コードを次に示します。

```csharp
DocumentBuilder builder = new DocumentBuilder();

Shape shape = builder.InsertHorizontalRule();

HorizontalRuleFormat horizontalRuleFormat = shape.HorizontalRuleFormat;
horizontalRuleFormat.Alignment = HorizontalRuleAlignment.Center;
horizontalRuleFormat.WidthPercent = 70;
horizontalRuleFormat.Height = 3;
horizontalRuleFormat.Color = Color.Blue;
horizontalRuleFormat.NoShade = true;

builder.Document.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
```

特定の要件に応じてコードを調整し、必要に応じて追加機能でコードを強化することを忘れないでください。

## 結論
おめでとう！ Aspose.Words for .NET を使用して Word 文書内の水平罫線を書式設定する方法を学習しました。ステップバイステップのガイドに従い、提供されているソース コードを利用することで、水平罫線の外観をカスタマイズして、文書の視覚的なレイアウトを向上させることができます。

さまざまな書式設定オプションを試して、水平罫線に必要なスタイルと効果を実現します。

### Word文書の横罫フォーマットに関するFAQ

#### Q: 横罫線に別の色を適用できますか?

A: もちろんです！ Aspose.Words for .NET を使用すると、Color プロパティを目的の色の値に設定することで、水平罫線の色を簡単にカスタマイズできます。これにより、水平罫線を文書全体のデザインに合わせることができます。

#### Q：横罫の幅や高さを調整することはできますか？

A: はい、水平罫線の幅と高さを完全に制御できます。 widthPercent プロパティと Height プロパティを変更すると、水平罫線の希望の寸法を実現できます。

#### Q: 文書内の横罫線の配置を変更できますか?

A：確かに！ Aspose.Words for .NET では、Alignment プロパティを使用して水平罫線の配置を指定できます。中央、左、右、両端揃えなどのさまざまなオプションから選択できます。

#### Q: 横罫線に網掛けや背景色を適用できますか?

A: はい、横罫線に網掛けや背景色を追加できます。デフォルトでは、NoShade プロパティは true に設定されていますが、適切なメソッドを使用してこれを false に設定し、シェーディングを定義することもできます。

#### Q: 1 つの文書に複数の横罫線を挿入できますか?

A: もちろんです！ Aspose.Words for .NET を使用して、Word 文書に複数の水平罫線を挿入できます。必要に応じてチュートリアルの手順を繰り返し、必要なだけ水平罫線を追加します。