---
title: オープンタイプの特長
linktitle: オープンタイプの特長
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET で Open Type 機能を有効にして使用する方法を学習します。
type: docs
weight: 10
url: /ja/net/enable-opentype-features/open-type-features/
---

この包括的なチュートリアルでは、Aspose.Words for .NET の Open Type 機能を有効にして利用する方法を学習します。プロセスを案内し、必要な C# コード スニペットを提供します。このガイドを終えると、Word 文書でオープン タイプ機能を使用できるようになります。

## 前提条件
始める前に、次の前提条件を満たしていることを確認してください。
- Aspose.Words for .NET ライブラリがシステムにインストールされています。

## ステップ 1: ドキュメントをロードする
まず、Document クラスを使用してドキュメントを読み込みます。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");
```

## ステップ 2: オープンタイプ機能を有効にする
オープン タイプ機能を有効にするには、LayoutOptions クラスの TextShaperFactory プロパティを目的のテキスト シェーパー ファクトリのインスタンスに設定します。この例では、HarfBuzzTextShaperFactory を使用します。

```csharp
doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;
```

## ステップ 3: ドキュメントを保存する
Open Type 機能を有効にした後、PDF などの目的の出力形式でドキュメントを保存します。

```csharp
doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

### Aspose.Words for .NET を使用したオープン タイプ機能のソース コード例
Aspose.Words for .NET で Open Type 機能を使用するための完全なソース コードを次に示します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "OpenType text shaping.docx");

doc.LayoutOptions.TextShaperFactory = Aspose.Words.Shaping.HarfBuzz.HarfBuzzTextShaperFactory.Instance;

doc.Save(dataDir + "WorkingWithHarfBuzz.OpenTypeFeatures.pdf");
```

## 結論
おめでとう！ Aspose.Words for .NET で Open Type 機能を有効にして利用する方法を学習しました。ステップバイステップのガイドに従い、提供されているソース コードを利用することで、Word 文書でオープン タイプ機能を操作できるようになります。

Open Type 機能は強化されたタイポグラフィーおよびテキスト整形機能を提供し、視覚的に魅力的でプロフェッショナルな外観のドキュメントを作成できます。さまざまなテキスト シェーパー ファクトリを試して、プロジェクトでの Open Type 機能の可能性を探ってください。

### よくある質問

#### Q: Aspose.Words for .NET で OpenType 機能を有効にするにはどうすればよいですか?

A: Aspose.Words for .NET で OpenType 機能を有効にするには、チュートリアルで説明されている手順に従う必要があります。

#### Q: Aspose.Words for .NET ではどのような OpenType 機能がサポートされていますか?

A: Aspose.Words for .NET は、合字、グリフ バリエーション、コンテキスト置換など、いくつかの OpenType 機能をサポートしています。

#### Q: OpenType 機能が特定のフォントでサポートされているかどうかを確認するにはどうすればよいですか?

A: OpenType 機能が特定のフォントでサポートされているかどうかを確認するには、`Font.OpenTypeFeatures` Aspose.Words for .NET のメソッド。

#### Q: Aspose.Words for .NET は他にどのようなテキスト書式設定機能をサポートしていますか?

A: OpenType 機能とは別に、Aspose.Words for .NET は、段落の書式設定、表の作成、画像の追加など、他のテキスト書式設定機能もサポートしています。

#### Q: Aspose.Words for .NET のすべてのバージョンで OpenType 機能を使用できますか?

A: OpenType 機能は、Aspose.Words for .NET の新しいバージョンでサポートされています。これらの機能を活用するには、互換性のあるバージョンを使用していることを確認してください。