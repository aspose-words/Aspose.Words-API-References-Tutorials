---
title: グラフの軸に日付と時刻の値を追加する
linktitle: グラフの軸に日付と時刻の値を追加する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、グラフの軸に日付と時刻の値を追加する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-charts/date-time-values-to-axis/
---

このチュートリアルでは、Aspose.Words for .NET を使用してグラフの軸に日付と時刻の値を追加する方法について説明します。

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
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
chart.Series.Clear();
```

## ステップ4: グラフにデータを追加する
日付と時刻の値を含むデータをグラフ シリーズに追加します。

```csharp
chart.Series.Add("Aspose Series 1",
	new[]
	{
		new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
		new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
	},
	new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
```

## ステップ5: 軸を構成する
グラフの X 軸を設定して、日付と時刻の値を表示します。

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
xAxis.MajorUnit = 7;
xAxis.MinorUnit = 1;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
```

## ステップ6: ドキュメントを保存する
指定されたディレクトリにドキュメントを保存するには、`Save`メソッド。適切なファイル拡張子を持つファイル名を指定します。この例では、ドキュメントを「WorkingWithCharts.DateTimeValuesToAxis.docx」として保存します。

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

### Aspose.Words for .NET を使用して日付時刻値を軸に表示するサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new[]
		{
			new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
			new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
		},
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
	ChartAxis xAxis = chart.AxisX;
	xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
	xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
	//主要単位を週、副次単位を日に設定します。
	xAxis.MajorUnit = 7;
	xAxis.MinorUnit = 1;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

このサンプル コードは、新しい Word 文書を作成し、X 軸に日時値を含む縦棒グラフを挿入し、指定されたディレクトリに文書を保存します。

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用して、グラフの軸に日付時刻値を追加する方法を学習しました。ステップ バイ ステップ ガイドに従うことで、グラフを作成し、系列に日付時刻値を追加し、軸を構成して日付時刻値を正確に表示することができます。Aspose.Words for .NET は、Word 文書のグラフを使用した Words Processing の強力な機能セットを提供し、日付時刻値を使用してデータを効果的に表現および視覚化できるようにします。

### よくある質問

#### Q1. Aspose.Words for .NET を使用して、グラフの軸に日付と時刻の値を追加できますか?
はい、Aspose.Words for .NET を使用すると、Word 文書のグラフの軸に日時値を追加して表示できます。Aspose.Words は、軸上の日時値の処理など、さまざまな種類のグラフを操作して外観をカスタマイズするための API と機能を提供します。

#### Q2. チャート シリーズに日付時刻値を追加するにはどうすればよいですか?
チャートシリーズに日付時刻値を追加するには、`Add`チャートのシリーズのメソッド。日付時刻値の配列をカテゴリ (X 軸) データとして、対応するシリーズ値とともに提供します。これにより、日付時刻値を持つデータ ポイントをチャートにプロットできます。

#### Q3. 日付と時刻の値を表示するように軸を構成するにはどうすればよいですか?
適切なプロパティを設定することで、グラフの軸に日付と時刻の値を表示するように設定できます。たとえば、軸の最小値と最大値を指定するには、`Scaling.Minimum`そして`Scaling.Maximum`プロパティをそれぞれ設定します。さらに、主単位と副単位を設定して、軸の間隔と目盛りを定義することもできます。
