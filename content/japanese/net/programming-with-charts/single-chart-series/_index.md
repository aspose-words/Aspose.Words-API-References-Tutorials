---
title: チャート内の単一のチャートシリーズをカスタマイズする
linktitle: チャート内の単一のチャートシリーズをカスタマイズする
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してグラフ内の単一のグラフ シリーズをカスタマイズする方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-charts/single-chart-series/
---

このチュートリアルでは、Aspose.Words for .NET を使用してグラフ内の単一のグラフ シリーズをカスタマイズする方法について説明します。提供されているソース コードは、グラフを作成し、特定のシリーズにアクセスし、それらのプロパティを変更する方法を示しています。

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

## ステップ3: チャートシリーズにアクセスしてカスタマイズする

単一のチャートシリーズを変更するには、`ChartSeries`チャートのオブジェクト。

```csharp
ChartSeries series0 = chart.Series[0];
ChartSeries series1 = chart.Series[1];

series0.Name = "Chart Series Name 1";
series1.Name = "Chart Series Name 2";

series0.Smooth = true;
series1.Smooth = true;

series0.InvertIfNegative = true;
series0.Marker.Symbol = MarkerSymbol.Circle;
series0.Marker.Size = 15;

series1.Marker.Symbol = MarkerSymbol.Star;
series1.Marker.Size = 10;
```

## ステップ4: ドキュメントを保存する

最後に、指定されたディレクトリにドキュメントを保存します。`Save`方法の`Document`物体。

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

これで、Aspose.Words for .NET を使用して単一のグラフ シリーズをカスタマイズする実装が完了します。

### Aspose.Words for .NET を使用した単一チャート シリーズのサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = chart.Series[0];
	ChartSeries series1 = chart.Series[1];
	series0.Name = "Chart Series Name 1";
	series1.Name = "Chart Series Name 2";
	//また、チャート上の点を結ぶ線を Catmull-Rom スプラインを使用して滑らかにするかどうかも指定できます。
	series0.Smooth = true;
	series1.Smooth = true;
	//値が負の場合に親要素の色をデフォルトで反転するかどうかを指定します。
	series0.InvertIfNegative = true;
	series0.Marker.Symbol = MarkerSymbol.Circle;
	series0.Marker.Size = 15;
	series1.Marker.Symbol = MarkerSymbol.Star;
	series1.Marker.Size = 10;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して、グラフ内の単一のグラフ シリーズをカスタマイズする方法を学習しました。ステップ バイ ステップ ガイドに従い、提供されているソース コードを利用することで、新しいドキュメントを作成し、折れ線グラフを挿入し、特定のグラフ シリーズにアクセスし、そのプロパティを変更して、必要なカスタマイズを実現できます。

Aspose.Words for .NET は、Word 文書内のグラフを操作するための強力な機能を提供します。個々のグラフ シリーズにアクセスすることで、特定の変更を適用して外観と動作をカスタマイズできます。これにより、シリーズ名の変更、グラフ ラインのスムージングの有効化、データ ポイントのマーカーのカスタマイズ、負の値の色を反転するなど、グラフの視覚的表現を強化できます。

単一のグラフ シリーズをカスタマイズすると、グラフ内の特定のデータを強調表示したり、特定の傾向を強調したりする柔軟性が得られます。Aspose.Words for .NET を使用すると、グラフ シリーズのプロパティに簡単にアクセスして変更できるため、Word 文書で視覚的に魅力的で情報豊富なグラフを作成できます。

### よくある質問

#### Q1. グラフ内の複数のグラフ シリーズをカスタマイズできますか?
はい、Aspose.Words for .NETを使用して、チャート内の複数のチャートシリーズをカスタマイズできます。`ChartSeries`チャート内のオブジェクトでは、インデックスまたは特定の条件に基づいて複数のシリーズを選択して変更できます。ループまたは個別の割り当てを使用して、各チャート シリーズの必要なプロパティを変更します。このようにして、同じチャート内の複数のシリーズに異なるカスタマイズを適用できます。

#### Q2. チャートシリーズの名前を変更するにはどうすればよいですか?
 Aspose.Words for .NETを使用してチャート内のチャートシリーズの名前を変更するには、`Name`の財産`ChartSeries`オブジェクトを作成し、希望する名前を設定します。シリーズ名は通常、グラフの凡例またはデータ ラベルに表示され、シリーズの説明ラベルとなります。シリーズ名を変更することで、各シリーズで表されるデータを反映する意味のある名前を付けることができます。

#### Q3. チャートシリーズのスムージングとは何ですか?
チャートの系列スムージングは、チャート上の点を結ぶ滑らかな線を作成できる視覚的強化技術です。Catmull-Rom スプラインなどのスムージング アルゴリズムを適用して、データ ポイント間を補間し、視覚的に美しい曲線を作成します。Aspose.Words for .NET を使用してチャートの系列スムージングを有効にするには、`Smooth`の財産`ChartSeries`オブジェクトに設定して`true`平滑化は、不規則な変動があるデータの傾向やパターンを表示する場合に役立ちます。

#### Q4. チャート シリーズのデータ ポイントのマーカーをカスタマイズするにはどうすればよいですか?
 Aspose.Words for .NETを使用してチャートシリーズのデータポイントのマーカーをカスタマイズするには、`Marker`の財産`ChartSeries`オブジェクトを作成し、そのプロパティを変更します。`Symbol`そして`Size`マーカーは、個々のデータ ポイントを表すためにグラフ上に配置される視覚的なインジケーターです。さまざまな組み込みマーカー シンボルから選択し、サイズを調整して、シリーズ内の特定のデータ ポイントを強調表示したり区別したりできます。

#### Q5. グラフシリーズ内の負の値の色を反転できますか?
はい、Aspose.Words for .NETを使用して、チャートシリーズの負の値の色を反転することができます。`InvertIfNegative`の財産`ChartSeries`反対する`true`、負の値を持つデータ ポイントの色が反転され、正の値と視覚的に区別されます。この機能は、グラフ シリーズで正の値と負の値を比較する場合に役立ち、両者を明確に区別できます。