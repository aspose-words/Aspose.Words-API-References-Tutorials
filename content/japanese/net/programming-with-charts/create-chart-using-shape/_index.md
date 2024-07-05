---
title: 図形を使用してチャートを作成およびカスタマイズする
linktitle: 図形を使用してチャートを作成およびカスタマイズする
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書内の図形を使用してグラフを作成およびカスタマイズする方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-charts/create-chart-using-shape/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の図形を使用してグラフを作成する方法について説明します。

## 前提条件
このチュートリアルを実行するには、次のものが必要です。

- Aspose.Words for .NET ライブラリがインストールされています。
- C# と Word 文書を使用した Words Processing に関する基本的な知識。

## ステップ1: ドキュメントディレクトリを設定する
まず、ドキュメントディレクトリへのパスを設定します。`"YOUR DOCUMENT DIRECTORY"`ドキュメントを保存するディレクトリへの実際のパスを入力します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ2: 新しいドキュメントとDocumentBuilderを作成する
新しいインスタンスを作成する`Document`クラスと`DocumentBuilder`ドキュメントを操作するオブジェクト。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ3: グラフ図形を挿入して構成する
チャート図形をドキュメントに挿入するには、`InsertChart`方法の`DocumentBuilder`オブジェクト。希望するグラフの種類と寸法を設定します。

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## ステップ4: チャートをカスタマイズする
グラフのタイトルや凡例などのさまざまなプロパティを変更してグラフをカスタマイズします。

```csharp
chart.Title.Show = true;
chart.Title.Text = "Line Chart Title";
chart.Title.Overlay = false;
chart.Legend.Position = LegendPosition.Left;
chart.Legend.Overlay = true;
```

## ステップ5: ドキュメントを保存する
指定されたディレクトリにドキュメントを保存するには、`Save`メソッド。適切なファイル拡張子を持つファイル名を指定します。この例では、ドキュメントを「WorkingWithCharts.CreateChartUsingShape.docx」として保存します。

```csharp
doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

### Aspose.Words for .NET を使用して図形を使用してグラフを作成するためのサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Show = true;
	chart.Title.Text = "Line Chart Title";
	chart.Title.Overlay = false;
	//タイトル テキストとして null または空の値が指定されている場合は、自動生成されたタイトルが表示されることに注意してください。
	chart.Legend.Position = LegendPosition.Left;
	chart.Legend.Overlay = true;
	doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

これで完了です。Aspose.Words for .NET を使用して、Word 文書内の図形を使用してグラフを作成することができました。

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の図形からグラフを作成する方法を学習しました。ステップ バイ ステップ ガイドに従うことで、グラフ図形を挿入して構成し、外観をカスタマイズして、文書を保存できます。Aspose.Words for .NET は、Word 文書とグラフを使用した Words Processing の包括的な機能セットを提供し、.NET アプリケーションで直接、プロフェッショナルな外観と視覚的に魅力的なグラフを作成できます。

### よくある質問

#### Q1. Aspose.Words for .NET を使用して Word 文書内にグラフを作成できますか?
はい、Aspose.Words for .NET を使用すると、Word 文書にプログラムでグラフを作成できます。Aspose.Words は、さまざまな種類のグラフを挿入し、外観をカスタマイズし、グラフ データを操作するための API と機能を提供します。

#### Q2. Aspose.Words for .NET ではどのようなグラフ タイプがサポートされていますか?
Aspose.Words for .NET は、折れ線グラフ、棒グラフ、円グラフ、面グラフ、散布図など、さまざまなグラフの種類をサポートしています。データと視覚化の要件に基づいて、適切なグラフの種類を選択できます。

#### Q3. 作成したチャートの外観をカスタマイズできますか？
はい、Aspose.Words for .NET を使用して、作成したグラフの外観をカスタマイズできます。グラフのタイトル、凡例の位置、データ ラベル、軸ラベル、色、その他の視覚要素などのプロパティを変更して、特定のデザインや書式設定のニーズを満たすことができます。
