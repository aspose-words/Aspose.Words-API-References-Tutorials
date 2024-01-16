---
title: チャート内の単一のチャートシリーズをカスタマイズする
linktitle: チャート内の単一のチャートシリーズをカスタマイズする
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してグラフ内の単一のグラフ シリーズをカスタマイズする方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-charts/single-chart-series/
---

このチュートリアルでは、Aspose.Words for .NET を使用してグラフ内の単一のグラフ シリーズをカスタマイズする方法について説明します。提供されているソース コードは、グラフの作成方法、特定のシリーズへのアクセス方法、およびそのプロパティの変更方法を示しています。

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

## ステップ 3: チャート シリーズにアクセスしてカスタマイズする

単一のグラフ シリーズを変更するには、`ChartSeries`チャートのオブジェクト。

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

## ステップ 4: ドキュメントを保存する

最後に、次のコマンドを使用してドキュメントを指定したディレクトリに保存します。`Save`の方法`Document`物体。

```csharp
doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

これで、Aspose.Words for .NET を使用した単一のグラフ シリーズのカスタマイズの実装が完了しました。

### Aspose.Words for .NET を使用した単一チャート シリーズのソース コード例 

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
	//チャート上の点を結ぶ線を Catmull-Rom スプラインを使用して滑らかにするかどうかも指定できます。
	series0.Smooth = true;
	series1.Smooth = true;
	//値が負の場合、デフォルトで親要素の色を反転するかどうかを指定します。
	series0.InvertIfNegative = true;
	series0.Marker.Symbol = MarkerSymbol.Circle;
	series0.Marker.Size = 15;
	series1.Marker.Symbol = MarkerSymbol.Star;
	series1.Marker.Size = 10;
	doc.Save(dataDir + "WorkingWithCharts.SingleChartSeries.docx");
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用してグラフ内の単一のグラフ シリーズをカスタマイズする方法を学習しました。ステップバイステップのガイドに従い、提供されているソース コードを利用することで、新しいドキュメントの作成、折れ線グラフの挿入、特定のグラフ シリーズへのアクセス、およびそのプロパティの変更を行って、目的のカスタマイズを実現できます。

Aspose.Words for .NET は、Word ドキュメント内のグラフを操作するための強力な機能を提供します。個々のグラフ シリーズにアクセスすることで、特定の変更を適用して、グラフの外観と動作をカスタマイズできます。これにより、シリーズ名の変更、グラフの線の平滑化の有効化、データ ポイントのマーカーのカスタマイズ、負の値の色の反転などを行うことができ、グラフの視覚的表現を向上させることができます。

単一のグラフ シリーズをカスタマイズすると、特定のデータを強調表示したり、グラフ内の特定の傾向を強調したりする柔軟性が得られます。 Aspose.Words for .NET を使用すると、グラフ シリーズのプロパティに簡単にアクセスして変更できるため、Word ドキュメント内に視覚的に魅力的で有益なグラフを作成できます。

### よくある質問

#### Q1.チャート内の複数のチャートシリーズをカスタマイズできますか?
はい、Aspose.Words for .NET を使用して、グラフ内の複数のグラフ シリーズをカスタマイズできます。にアクセスすることで、`ChartSeries`チャート内のオブジェクトを使用すると、インデックスや特定の基準に基づいて複数のシリーズを選択および変更できます。ループまたは個別の割り当てを使用して、グラフ シリーズごとに必要なプロパティを変更します。このようにして、同じグラフ内の複数の系列に異なるカスタマイズを適用できます。

#### Q2.グラフシリーズの名前を変更するにはどうすればよいですか?
 Aspose.Words for .NET を使用してグラフ内のグラフ シリーズの名前を変更するには、`Name`の財産`ChartSeries`オブジェクトを選択し、目的の名前に設定します。シリーズ名は通常、グラフの凡例またはデータ ラベルに表示され、シリーズを説明するラベルとなります。シリーズ名を変更すると、各シリーズが表すデータを反映した意味のある名前を付けることができます。

#### Q3.チャート系列のスムージングとは何ですか?
チャート シリーズのスムージングは、チャート上の点を結ぶ滑らかな線を作成できる視覚的強化手法です。 Catmull-Rom スプラインなどの平滑化アルゴリズムを適用してデータ ポイント間を補間し、視覚的に美しい曲線を作成します。 Aspose.Words for .NET を使用してグラフで系列の平滑化を有効にするには、`Smooth`の財産`ChartSeries`オブジェクトを選択し、それに設定します`true`。平滑化は、不規則な変動のあるデータの傾向やパターンを表示するのに役立ちます。

#### Q4.グラフ シリーズ内のデータ ポイントのマーカーをカスタマイズするにはどうすればよいですか?
 Aspose.Words for .NET を使用してグラフ シリーズのデータ ポイントのマーカーをカスタマイズするには、`Marker`の財産`ChartSeries`オブジェクトを作成し、そのプロパティを変更します。`Symbol`そして`Size`。マーカーは、個々のデータ ポイントを表すためにチャート上に配置される視覚的なインジケーターです。さまざまな組み込みマーカー シンボルから選択し、そのサイズを調整して、系列内の特定のデータ ポイントを強調表示したり区別したりできます。

#### Q5.一連のグラフの負の値の色を反転できますか?
はい、Aspose.Words for .NET を使用して、グラフ シリーズ内の負の値の色を反転できます。を設定することで、`InvertIfNegative`の財産`ChartSeries`に反対する`true`を使用すると、負の値を持つデータ ポイントの色が反転され、正の値と視覚的に区別できるようになります。この機能は、一連のグラフで正の値と負の値を比較する場合に役立ち、2 つを明確に区別できます。