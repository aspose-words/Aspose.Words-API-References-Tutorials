---
title: オープンタイプの機能
linktitle: オープンタイプの機能
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET で Open Type 機能を有効にして使用する方法を学びます
type: docs
weight: 10
url: /ja/net/enable-opentype-features/open-type-features/
---

この包括的なチュートリアルでは、Aspose.Words for .NET で Open Type 機能を有効にして使用する方法を学習します。プロセスをガイドし、必要な C# コード スニペットを提供します。このガイドの最後まで読めば、Word 文書で Open Type 機能を操作できるようになります。

## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
- Aspose.Words for .NET ライブラリがシステムにインストールされています。

## ステップ1: ドキュメントを読み込む
まず、Document クラスを使用してドキュメントを読み込みます。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");
```

## ステップ2: オープンタイプ機能を有効にする
Open Type 機能を有効にするには、LayoutOptions クラスの TextShaperFactory プロパティを、目的のテキスト シェイパー ファクトリのインスタンスに設定します。この例では、HarfBuzzTextShaperFactory を使用します。

```csharp
doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;
```

## ステップ3: ドキュメントを保存する
Open Type 機能を有効にした後、PDF などの目的の出力形式でドキュメントを保存します。

```csharp
doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

### Aspose.Words for .NET を使用したオープン タイプ機能のサンプル ソース コード
Aspose.Words for .NET で Open Type 機能を使用するための完全なソース コードは次のとおりです。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");

doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;

doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

## 結論
おめでとうございます。Aspose.Words for .NET で Open Type 機能を有効にして使用する方法を学習しました。ステップ バイ ステップ ガイドに従い、提供されているソース コードを利用することで、Word 文書で Open Type 機能を操作できるようになります。

Open Type 機能により、強化されたタイポグラフィとテキスト シェーピング機能が提供され、見た目に魅力的でプロフェッショナルなドキュメントを作成できます。さまざまなテキスト シェーパー ファクトリーを試して、プロジェクトにおける Open Type 機能の可能性を探ってみましょう。

### よくある質問

#### Q: Aspose.Words for .NET で OpenType 機能を有効にするにはどうすればいいですか?

A: Aspose.Words for .NET で OpenType 機能を有効にするには、チュートリアルに記載されている手順に従う必要があります。

#### Q: Aspose.Words for .NET ではどのような OpenType 機能がサポートされていますか?

A: Aspose.Words for .NET は、合字、グリフのバリエーション、コンテキストの置換など、いくつかの OpenType 機能をサポートしています。

#### Q: 特定のフォントで OpenType 機能がサポートされているかどうかを確認するにはどうすればよいですか?

A: OpenType機能が特定のフォントでサポートされているかどうかを確認するには、`Font.OpenTypeFeatures` Aspose.Words for .NET のメソッド。

#### Q: Aspose.Words for .NET は他にどのようなテキスト書式設定機能をサポートしていますか?

A: OpenType 機能以外にも、Aspose.Words for .NET は段落の書式設定、表の作成、画像の追加など、他のテキスト書式設定機能もサポートしています。

#### Q: Aspose.Words for .NET のすべてのバージョンで OpenType 機能を使用できますか?

A: OpenType 機能は、Aspose.Words for .NET の新しいバージョンでサポートされています。これらの機能を活用するには、互換性のあるバージョンを使用していることを確認してください。