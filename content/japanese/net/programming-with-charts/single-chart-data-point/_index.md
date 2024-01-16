---
title: チャート内の単一のチャート データ ポイントをカスタマイズする
linktitle: チャート内の単一のチャート データ ポイントをカスタマイズする
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してグラフ内の単一のデータ ポイントをカスタマイズする方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-charts/single-chart-data-point/
---

このチュートリアルでは、Aspose.Words for .NET を使用してグラフ内の単一のデータ ポイントをカスタマイズする方法について説明します。提供されたソース コードは、グラフの作成方法、特定のデータ ポイントへのアクセス方法、およびそのプロパティの変更方法を示しています。

## ステップ 1: プロジェクトをセットアップする

次の前提条件を満たしていることを確認してください。

- Aspose.Words for .NET ライブラリがインストールされています。 NuGet パッケージ マネージャーを使用してダウンロードしてインストールできます。
- 出力ドキュメントが保存されるドキュメント ディレクトリ パス。

## ステップ 2: 新しいドキュメントを作成し、グラフを挿入する

新しいを作成します`Document`オブジェクトと`DocumentBuilder`ドキュメントを作成します。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

次に、`InsertChart`の方法`DocumentBuilder`折れ線グラフを文書に挿入します。

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
```

## ステップ 3: データポイントにアクセスしてカスタマイズする

個々のデータ ポイントを変更するには、`ChartDataPointCollection`シリーズのデータ ポイントを選択し、インデックスを使用して目的のデータ ポイントを選択します。

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

## ステップ 4: ドキュメントを保存する

最後に、次のコマンドを使用してドキュメントを指定したディレクトリに保存します。`Save`の方法`Document`物体。

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartDataPoint.docx");
```

これで、Aspose.Words for .NET を使用してグラフ内の単一のデータ ポイントをカスタマイズする実装が完了しました。

### Aspose.Words for .NET を使用した単一チャート データ ポイントのソース コード例 

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

このチュートリアルでは、Aspose.Words for .NET を使用してグラフ内の単一のデータ ポイントをカスタマイズする方法を学習しました。ステップバイステップのガイドに従い、提供されているソース コードを利用することで、新しいドキュメントの作成、折れ線グラフの挿入、グラフ シリーズ内の特定のデータ ポイントへのアクセス、およびそのプロパティの変更を行って目的のカスタマイズを実現できます。

Aspose.Words for .NET は、Word ドキュメント内のグラフを操作するための強力な機能を提供します。グラフ シリーズ内の個々のデータ ポイントにアクセスすることで、特定の変更を適用して、その外観と動作をカスタマイズできます。これにより、特定のデータ ポイントの強調表示、マーカー シンボルの変更、マーカー サイズの調整などが可能になり、グラフの視覚的表現を向上させることができます。

個々のデータ ポイントをカスタマイズすると、重要なデータを強調したり、グラフ内の特定の傾向を強調したりする柔軟性が得られます。 Aspose.Words for .NET を使用すると、さまざまな種類のグラフのデータ ポイントに簡単にアクセスして変更できるため、Word ドキュメント内に視覚的に魅力的で有益なグラフを作成できます。

### よくある質問

#### Q1.グラフ内の複数のデータ ポイントをカスタマイズできますか?
はい、Aspose.Words for .NET を使用して、グラフ内の複数のデータ ポイントをカスタマイズできます。にアクセスすることで、`ChartDataPointCollection`系列の複数のデータ ポイントをインデックスに基づいて選択し、変更できます。ループまたは個別の割り当てを使用して、各データ ポイントの必要なプロパティを変更します。このようにして、同じグラフ内の複数のデータ ポイントに異なるカスタマイズを適用できます。

#### Q2.データ ポイントのマーカー シンボルを変更するにはどうすればよいですか?
 Aspose.Words for .NET を使用してチャート内のデータ ポイントのマーカー シンボルを変更するには、`Marker`の財産`ChartDataPoint`オブジェクトを設定して、`Symbol`プロパティを目的のマーカー シンボルに設定します。マーカー シンボルは、チャート上の各データ ポイントを表すために使用される形状またはアイコンを表します。円、四角、ひし形、三角形、星など、さまざまな組み込みのマーカー シンボルから選択できます。

#### Q3.データポイントマーカーのサイズを調整できますか?
はい、Aspose.Words for .NET を使用して、グラフ内のデータ ポイント マーカーのサイズを調整できます。にアクセスしてください`Marker`の財産`ChartDataPoint`オブジェクトを設定して、`Size`プロパティを希望のマーカー サイズに合わせます。マーカーのサイズは通常、ポイント単位で指定され、値が大きいほどマーカー サイズが大きくなります。マーカー サイズを調整すると、特定のデータ ポイントを強調したり、重要性に基づいてデータ ポイントを区別したりできます。

#### Q4.データ ポイントに対して他にどのようなプロパティを変更できますか?
Aspose.Words for .NET は、グラフ内のデータ ポイントに対して変更できるさまざまなプロパティを提供します。よく変更されるプロパティには、マーカー シンボル、マーカー サイズ、マーカーの色、データ ラベルの表示/非表示、爆発、負の場合は反転などが含まれます。これらのプロパティを使用すると、個々のデータ ポイントの外観、動作、対話性をカスタマイズできるため、特定の要件に合わせたグラフを作成できます。

#### Q5.他のグラフ タイプのデータ ポイントをカスタマイズできますか?
はい、Aspose.Words for .NET を使用して、さまざまなグラフ タイプのデータ ポイントをカスタマイズできます。このチュートリアルでは折れ線グラフのデータ ポイントのカスタマイズを説明しますが、同様の手法を縦棒グラフ、棒グラフ、円グラフなどの他の種類のグラフに適用することもできます。このプロセスには、チャート内の系列とデータ ポイントにアクセスし、それに応じてそれらのプロパティを変更することが含まれます。