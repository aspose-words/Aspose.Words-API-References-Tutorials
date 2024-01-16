---
title: チャートの XY 軸プロパティを定義する
linktitle: チャートの XY 軸プロパティを定義する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してグラフの XY 軸プロパティを定義する方法を学びます。 X 軸と Y 軸のカスタマイズ オプションが示されています。
type: docs
weight: 10
url: /ja/net/programming-with-charts/define-xyaxis-properties/
---

このチュートリアルでは、Aspose.Words for .NET を使用してグラフの X 軸と Y 軸のプロパティを定義する方法について説明します。提供されているソース コードは、グラフの作成方法、系列データの追加方法、および軸プロパティのカスタマイズ方法を示しています。

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

次に、`InsertChart`の方法`DocumentBuilder`。この例では、面グラフを挿入します。

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## ステップ 3: 系列データをグラフに追加する

系列データをグラフに追加します。この例では、対応する日付と値を持つ 5 つのデータ ポイントを追加します。

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new DateTime[]
    {
        new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
        new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
    },
    new double[] { 640, 320, 280, 120, 150 });
```

## ステップ 4: X 軸と Y 軸のプロパティをカスタマイズする

 軸と Y 軸のプロパティをカスタマイズするには、`ChartAxis`チャートに関連付けられたオブジェクト。

```csharp
ChartAxis xAxis = chart.AxisX;
ChartAxis yAxis = chart.AxisY;
```

のプロパティを変更します。`xAxis`そして`yAxis`オブジェクトを使用して、X 軸と Y 軸に必要なオプションを設定します。この例では、カスタマイズ可能ないくつかの一般的なプロパティを示します。

```csharp
xAxis.CategoryType = AxisCategoryType.Category;
xAxis.Crosses = AxisCrosses.Custom;
xAxis.CrossesAt = 3;
xAxis.ReverseOrder = true;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
xAxis.TickLabelOffset = 200;

yAxis.TickLabelPosition = AxisTickLabelPosition.High;
yAxis.MajorUnit = 100;
yAxis.MinorUnit = 50;
yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
yAxis.Scaling.Minimum = new AxisBound(100);
yAxis.Scaling.Maximum = new AxisBound(700);
```

## ステップ 5: ドキュメントを保存する

最後に、次のコマンドを使用してドキュメントを指定したディレクトリに保存します。`Save`の方法`Document`物体。

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

これで、Aspose.Words for .NET を使用してグラフに XY 軸プロパティを定義する実装が完了しました。

### Aspose.Words for .NET を使用した XYAxis プロパティの定義のソース コード例 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	//グラフの挿入
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new DateTime[]
		{
			new DateTime(2002, 01, 01), new DateTime(2002, 06, 01), new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01), new DateTime(2002, 09, 01)
		},
		new double[] { 640, 320, 280, 120, 150 });
	ChartAxis xAxis = chart.AxisX;
	ChartAxis yAxis = chart.AxisY;
	// 軸を日付ではなくカテゴリに変更すると、すべてのポイントが X 軸上に等間隔で配置されます。
	xAxis.CategoryType = AxisCategoryType.Category;
	xAxis.Crosses = AxisCrosses.Custom;
	xAxis.CrossesAt = 3; // 軸の表示単位 (百) で測定されます。
	xAxis.ReverseOrder = true;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	xAxis.TickLabelOffset = 200;
	yAxis.TickLabelPosition = AxisTickLabelPosition.High;
	yAxis.MajorUnit = 100;
	yAxis.MinorUnit = 50;
	yAxis.DisplayUnit.Unit = AxisBuiltInUnit.Hundreds;
	yAxis.Scaling.Minimum = new AxisBound(100);
	yAxis.Scaling.Maximum = new AxisBound(700);
	doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用してグラフの X 軸と Y 軸のプロパティを定義する方法を学習しました。ステップバイステップのガイドに従うことで、特定の要件を満たすようにグラフを作成し、系列データを追加し、軸のプロパティをカスタマイズできます。 Aspose.Words for .NET は、Word ドキュメント内のグラフを使用したワード処理用の包括的な API を提供し、軸などグラフのさまざまな側面を操作できます。

にアクセスすることで、`ChartAxis`チャートに関連付けられたオブジェクトを使用すると、カテゴリ タイプ、軸の交差、目盛り、ラベルの位置、スケールなどのプロパティを変更できます。この柔軟性により、グラフの軸の外観と動作を調整して、データを効果的に表示できます。

Aspose.Words for .NET を使用すると、グラフの作成機能とカスタマイズ機能を .NET アプリケーションにシームレスに統合し、豊富な視覚効果を備えた本格的なドキュメントの生成を自動化できます。

### よくある質問

#### Q1. Aspose.Words for .NET とは何ですか?
Aspose.Words for .NET は、開発者が .NET アプリケーションで Word ドキュメントをプログラム的に作成、操作、保存できるようにする強力なドキュメント処理ライブラリです。グラフなどの文書要素を含むワープロ向けの幅広い機能を提供します。

#### Q2. Aspose.Words for .NET をインストールするにはどうすればよいですか?
Aspose.Words for .NET をインストールするには、Visual Studio の NuGet パッケージ マネージャーを使用してダウンロードします。 NuGet パッケージ マネージャーで「Aspose.Words」を検索し、プロジェクトにインストールするだけです。

#### Q3. Aspose.Words for .NET を使用してグラフの他の側面をカスタマイズできますか?
はい、Aspose.Words for .NET は、グラフのさまざまな側面をカスタマイズするための広範な機能を提供します。軸プロパティの定義に加えて、グラフの種類、データ系列、凡例、タイトル、プロット領域、データ ラベル、およびグラフの他の多くの要素を変更できます。 API は、チャートの外観と動作をきめ細かく制御できます。

#### Q4. Aspose.Words for .NET を使用してさまざまな種類のグラフを作成できますか?
はい。Aspose.Words for .NET は、面グラフ、棒グラフ、折れ線グラフ、円グラフ、散布図など、幅広い種類のグラフをサポートしています。使用できます`ChartType`Word 文書にグラフ図形を挿入するときに、必要なグラフの種類を指定する列挙体。

#### Q5.グラフを別の形式で保存できますか?
はい、Aspose.Words for .NET を使用すると、チャートを含むドキュメントを DOCX、PDF、HTML などのさまざまな形式で保存できます。要件に基づいて適切な形式を選択し、`Save`の方法`Document`ドキュメントを保存するオブジェクト。

#### Q6.これらのテクニックをドキュメント内の複数のグラフに適用できますか?
はい、グラフごとに必要な手順を繰り返すことで、これらのテクニックをドキュメント内の複数のグラフに適用できます。別々に作成することもできます`Chart`そして`ChartAxis`各チャートのオブジェクトを作成し、それに応じてプロパティをカスタマイズします。 Aspose.Words for .NET は、単一のドキュメント内に複数のグラフを含むワード処理を完全にサポートします。