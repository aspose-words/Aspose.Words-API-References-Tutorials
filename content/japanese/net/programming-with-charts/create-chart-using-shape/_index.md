---
title: 形状を使用してグラフを作成およびカスタマイズする
linktitle: 形状を使用してグラフを作成およびカスタマイズする
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、Word 文書内の図形を使用してグラフを作成およびカスタマイズする方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-charts/create-chart-using-shape/
---

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の図形を使用してグラフを作成する方法について説明します。

## 前提条件
このチュートリアルに従うには、以下が必要です。

- Aspose.Words for .NET ライブラリがインストールされています。
- C# と Word ドキュメントを使用したワード処理の基本的な知識。

## ステップ 1: ドキュメント ディレクトリを設定する
まず、ドキュメント ディレクトリへのパスを設定します。交換する`"YOUR DOCUMENT DIRECTORY"`ドキュメントを保存するディレクトリへの実際のパスを指定します。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## ステップ 2: 新しいドキュメントと DocumentBuilder を作成する
の新しいインスタンスを作成します。`Document`クラスと`DocumentBuilder`ドキュメントを操作するオブジェクト。

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## ステップ 3: グラフ図形を挿入して構成する
を使用してグラフ図形をドキュメントに挿入します。`InsertChart`の方法`DocumentBuilder`物体。必要なグラフの種類と寸法を設定します。

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## ステップ 4: グラフをカスタマイズする
グラフのタイトルや凡例などのさまざまなプロパティを変更して、グラフをカスタマイズします。

```csharp
chart.Title.Show = true;
chart.Title.Text = "Line Chart Title";
chart.Title.Overlay = false;
chart.Legend.Position = LegendPosition.Left;
chart.Legend.Overlay = true;
```

## ステップ 5: ドキュメントを保存する
を使用してドキュメントを指定されたディレクトリに保存します。`Save`方法。適切なファイル拡張子を付けて、目的のファイル名を指定します。この例では、ドキュメントを「WorkingWithCharts.CreateChartUsingShape.docx」として保存します。

```csharp
doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

### Aspose.Words for .NET を使用して図形を使用してグラフを作成するためのソース コードの例 

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
	//タイトルテキストとして null または空の値が指定された場合、自動生成されたタイトルが表示されることに注意してください。
	chart.Legend.Position = LegendPosition.Left;
	chart.Legend.Overlay = true;
	doc.Save(dataDir + "WorkingWithCharts.CreateChartUsingShape.docx");
```

それでおしまい！ Aspose.Words for .NET を使用して、Word ドキュメント内の図形を使用したグラフを正常に作成できました。

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内の図形を使用してグラフを作成する方法を学習しました。ステップバイステップのガイドに従うことで、グラフ図形の挿入と構成、外観のカスタマイズ、ドキュメントの保存を行うことができます。 Aspose.Words for .NET は、Word 文書とグラフを使用したワード処理のための包括的な機能セットを提供し、.NET アプリケーションで直接、プロフェッショナルな見た目で視覚的に魅力的なグラフを作成できるようにします。

### よくある質問

#### Q1. Aspose.Words for .NET を使用して Word 文書内にグラフを作成できますか?
はい、Aspose.Words for .NET を使用すると、Word 文書内にプログラムでグラフを作成できます。 Aspose.Words は、さまざまな種類のグラフを挿入し、外観をカスタマイズし、グラフ データを操作するための API と機能を提供します。

#### Q2. Aspose.Words for .NET ではどのようなグラフの種類がサポートされていますか?
Aspose.Words for .NET は、折れ線グラフ、棒グラフ、円グラフ、面グラフ、散布図など、幅広い種類のグラフをサポートしています。データと視覚化の要件に基づいて、適切なグラフの種類を選択できます。

#### Q3.作成したグラフの外観をカスタマイズできますか?
はい、Aspose.Words for .NET を使用して、作成したグラフの外観をカスタマイズできます。特定のデザインや書式設定のニーズに合わせて、グラフのタイトル、凡例の位置、データ ラベル、軸ラベル、色、その他の視覚要素などのプロパティを変更できます。
