---
title: チャート内の単一のチャートデータポイントをカスタマイズする
linktitle: チャート内の単一のチャートデータポイントをカスタマイズする
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してグラフ内の単一のデータ ポイントをカスタマイズする方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-charts/single-chart-data-point/
---

このチュートリアルでは、Aspose.Words for .NET を使用してグラフ内の単一のデータ ポイントをカスタマイズする方法について説明します。提供されているソース コードでは、グラフを作成し、特定のデータ ポイントにアクセスし、そのプロパティを変更する方法を示しています。

## ステップ1: プロジェクトを設定する

次の前提条件を満たしていることを確認してください。

- Aspose.Words for .NET ライブラリがインストールされています。NuGet パッケージ マネージャーを使用してダウンロードし、インストールできます。
- 出力ドキュメントが保存されるドキュメント ディレクトリ パス。

## ステップ2: 新しいドキュメントを作成し、グラフを挿入する

新しいを作成します`Document`オブジェクトと`DocumentBuilder`ドキュメントを作成します。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

次に、`InsertChart`方法の`DocumentBuilder`ドキュメントに折れ線グラフを挿入します。

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## ステップ3: データポイントにアクセスしてカスタマイズする

個々のデータポイントを変更するには、`ChartDataPointCollection`シリーズのインデックスを使用して目的のデータ ポイントを選択します。

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];

ChartDataPointCollection dataPointCollection = series0.DataPoints;
ChartDataPoint dataPoint00 = dataPointCollection[0];
ChartDataPoint dataPoint01 = dataPointCollection[1];

dataPoint00.Explosion = 50;
dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
dataPoint00.Marker.Size = 15;

dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
dataPoint01.Marker.Size = 20;

ChartDataPoint dataPoint12 = series1.DataPoints[2];
dataPoint12.InvertIfNegative = true;
dataPoint12.Marker.Symbol = MarkerSymbol.Star;
dataPoint12.Marker.Size = 20;
```

## ステップ4: ドキュメントを保存する

最後に、指定されたディレクトリにドキュメントを保存します。`Save`方法の`Document`物体。

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

これで、Aspose.Words for .NET を使用してグラフ内の単一のデータ ポイントをカスタマイズする実装が完了します。

### Aspose.Words for .NET を使用した単一チャート データ ポイントのサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	ChartDataPointCollection dataPointCollection = series0.DataPoints;
	ChartDataPoint dataPoint00 = dataPointCollection[0];
	ChartDataPoint dataPoint01 = dataPointCollection[1];
	dataPoint00.Explosion = 50;
	dataPoint00.Marker.Symbol = MarkerSymbol.Circle;
	dataPoint00.Marker.Size = 15;
	dataPoint01.Marker.Symbol = MarkerSymbol.Diamond;
	dataPoint01.Marker.Size = 20;
	ChartDataPoint dataPoint12 = series1.DataPoints[2];
	dataPoint12.InvertIfNegative = true;
	dataPoint12.Marker.Symbol = MarkerSymbol.Star;
	dataPoint12.Marker.Size = 20;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用してグラフ内の単一のデータ ポイントをカスタマイズする方法を学習しました。ステップ バイ ステップ ガイドに従い、提供されているソース コードを利用することで、新しいドキュメントを作成し、折れ線グラフを挿入し、グラフ シリーズ内の特定のデータ ポイントにアクセスし、そのプロパティを変更して、必要なカスタマイズを実現できます。

Aspose.Words for .NET は、Word 文書内のグラフを操作するための強力な機能を提供します。グラフ シリーズ内の個々のデータ ポイントにアクセスすることで、特定の変更を適用して外観と動作をカスタマイズできます。これにより、特定のデータ ポイントを強調表示したり、マーカー シンボルを変更したり、マーカー サイズを調整したりして、グラフの視覚的な表現を強化できます。

個々のデータ ポイントをカスタマイズすることで、重要なデータを強調したり、グラフ内の特定の傾向をハイライト表示したりする柔軟性が得られます。Aspose.Words for .NET を使用すると、さまざまな種類のグラフのデータ ポイントに簡単にアクセスして変更できるため、Word 文書で視覚的に魅力的で情報豊富なグラフを作成できます。

### よくある質問

#### Q1. グラフ内の複数のデータ ポイントをカスタマイズできますか?
はい、Aspose.Words for .NETを使用して、チャート内の複数のデータポイントをカスタマイズできます。`ChartDataPointCollection`系列では、インデックスに基づいて複数のデータ ポイントを選択し、変更できます。ループまたは個別の割り当てを使用して、各データ ポイントの必要なプロパティを変更します。このようにして、同じグラフ内の複数のデータ ポイントに異なるカスタマイズを適用できます。

#### Q2. データ ポイントのマーカー シンボルを変更するにはどうすればよいですか?
 Aspose.Words for .NETを使用してグラフ内のデータポイントのマーカーシンボルを変更するには、`Marker`の財産`ChartDataPoint`オブジェクトを設定し、`Symbol`プロパティを目的のマーカー シンボルに設定します。マーカー シンボルは、グラフ上の各データ ポイントを表すために使用される形状またはアイコンを表します。円、四角形、ひし形、三角形、星など、さまざまな組み込みマーカー シンボルから選択できます。

#### Q3. データポイントマーカーのサイズを調整できますか?
はい、Aspose.Words for .NETを使用してグラフ内のデータポイントマーカーのサイズを調整できます。`Marker`の財産`ChartDataPoint`オブジェクトを設定し、`Size`プロパティを目的のマーカー サイズに設定します。マーカーのサイズは通常ポイントで指定され、値が大きいほどマーカー サイズが大きくなります。マーカー サイズを調整すると、特定のデータ ポイントを強調したり、重要度に基づいて区別したりできます。

#### Q4. データ ポイントのその他のプロパティを変更できますか?
Aspose.Words for .NET には、グラフのデータ ポイントに対して変更できるさまざまなプロパティが用意されています。よく変更されるプロパティには、マーカー シンボル、マーカー サイズ、マーカーの色、データ ラベルの表示、分解、負の値の場合は反転などがあります。これらのプロパティを使用すると、個々のデータ ポイントの外観、動作、対話性をカスタマイズして、特定の要件に合わせたグラフを作成できます。

#### Q5. 他の種類のグラフのデータ ポイントをカスタマイズできますか?
はい、Aspose.Words for .NET を使用して、さまざまなグラフの種類のデータ ポイントをカスタマイズできます。このチュートリアルでは折れ線グラフのデータ ポイントをカスタマイズする方法を説明しますが、同様の手法を縦棒グラフ、棒グラフ、円グラフなどの他のグラフの種類にも適用できます。このプロセスでは、グラフ内の系列とデータ ポイントにアクセスし、それに応じてプロパティを変更します。