---
title: グラフの XY 軸プロパティを定義する
linktitle: グラフの XY 軸プロパティを定義する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してグラフの XY 軸プロパティを定義する方法を学習します。X 軸と Y 軸のカスタマイズ オプションについて説明します。
type: docs
weight: 10
url: /ja/net/programming-with-charts/define-xyaxis-properties/
---

このチュートリアルでは、Aspose.Words for .NET を使用してグラフの X 軸と Y 軸のプロパティを定義する方法について説明します。提供されているソース コードでは、グラフの作成方法、系列データの追加方法、軸のプロパティのカスタマイズ方法が示されています。

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

次に、`InsertChart`方法の`DocumentBuilder`この例では、面グラフを挿入します。

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## ステップ3: グラフに系列データを追加する

グラフに系列データを追加します。この例では、対応する日付と値を持つ 5 つのデータ ポイントを追加します。

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

## ステップ4: X軸とY軸のプロパティをカスタマイズする

X軸とY軸のプロパティをカスタマイズするには、`ChartAxis`チャートに関連付けられたオブジェクト。

```csharp
ChartAxis xAxis = chart.AxisX;
ChartAxis yAxis = chart.AxisY;
```

プロパティを変更する`xAxis`そして`yAxis`オブジェクトを使用して、X 軸と Y 軸に必要なオプションを設定します。この例では、カスタマイズできる一般的なプロパティをいくつか紹介します。

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

## ステップ5: ドキュメントを保存する

最後に、指定されたディレクトリにドキュメントを保存します。`Save`方法の`Document`物体。

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

これで、Aspose.Words for .NET を使用してグラフの XY 軸プロパティを定義する実装が完了します。

### Aspose.Words for .NET を使用して XYAxis プロパティを定義するためのサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	//グラフを挿入
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

このチュートリアルでは、Aspose.Words for .NET を使用してグラフの X 軸と Y 軸のプロパティを定義する方法を学習しました。ステップ バイ ステップ ガイドに従うことで、グラフを作成し、系列データを追加し、特定の要件を満たすように軸のプロパティをカスタマイズできます。Aspose.Words for .NET は、Word 文書内のグラフで Words Processing を行うための包括的な API を提供し、軸を含むグラフのさまざまな側面を操作できるようにします。

アクセスすることで`ChartAxis`グラフに関連付けられたオブジェクトでは、カテゴリの種類、軸の交差、目盛り、ラベルの位置、スケーリングなどのプロパティを変更できます。この柔軟性により、グラフの軸の外観と動作をカスタマイズして、データを効果的に表示できます。

Aspose.Words for .NET を使用すると、グラフ作成機能とカスタマイズ機能を .NET アプリケーションにシームレスに統合し、豊富な視覚化機能を備えたプロフェッショナルなドキュメントの生成を自動化できます。

### よくある質問

#### Q1. Aspose.Words for .NET とは何ですか?
Aspose.Words for .NET は、開発者が .NET アプリケーションでプログラムを使用して Word 文書を作成、操作、保存できるようにする強力なドキュメント処理ライブラリです。チャートなどのドキュメント要素を使用して Words を処理するための幅広い機能を提供します。

#### Q2. Aspose.Words for .NET をインストールするにはどうすればよいですか?
Aspose.Words for .NET は、Visual Studio の NuGet パッケージ マネージャーを使用してダウンロードすることでインストールできます。NuGet パッケージ マネージャーで「Aspose.Words」を検索し、プロジェクトにインストールするだけです。

#### Q3. Aspose.Words for .NET を使用してグラフの他の側面をカスタマイズできますか?
はい、Aspose.Words for .NET は、グラフのさまざまな側面をカスタマイズするための広範な機能を提供します。軸のプロパティを定義するだけでなく、グラフの種類、データ シリーズ、凡例、タイトル、プロット領域、データ ラベル、およびグラフのその他の多くの要素を変更できます。API は、グラフの外観と動作を細かく制御します。

#### Q4. Aspose.Words for .NET を使用してさまざまな種類のグラフを作成できますか?
はい、Aspose.Words for .NETは、面グラフ、棒グラフ、折れ線グラフ、円グラフ、散布図など、さまざまなグラフの種類をサポートしています。`ChartType` Word 文書にグラフの図形を挿入するときに、目的のグラフの種類を指定するための列挙体。

#### Q5. チャートを異なる形式で保存できますか?
はい、Aspose.Words for .NETでは、チャートを含むドキュメントをDOCX、PDF、HTMLなどのさまざまな形式で保存できます。要件に応じて適切な形式を選択し、`Save`方法の`Document`ドキュメントを保存するオブジェクト。

#### Q6. これらのテクニックをドキュメント内の複数のグラフに適用できますか?
はい、各グラフに必要な手順を繰り返すことで、ドキュメント内の複数のグラフにこれらのテクニックを適用できます。`Chart`そして`ChartAxis`各グラフのオブジェクトを作成し、それに応じてプロパティをカスタマイズします。Aspose.Words for .NET は、1 つのドキュメントで複数のグラフを使用した Words Processing を完全にサポートします。