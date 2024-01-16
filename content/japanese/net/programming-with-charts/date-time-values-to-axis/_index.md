---
title: チャートの軸に日時値を追加する
linktitle: チャートの軸に日時値を追加する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してグラフの軸に日時値を追加する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-charts/date-time-values-to-axis/
---

このチュートリアルでは、Aspose.Words for .NET を使用してグラフの軸に日時値を追加する方法について説明します。

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
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
chart.Series.Clear();
```

## ステップ 4: グラフにデータを追加する
日時値を含むデータをグラフ シリーズに追加します。

```csharp
chart.Series.Add("Aspose Series 1",
	new[]
	{
		new DateTime(2017, 11, 06), new DateTime(2017, 11, 09), new DateTime(2017, 11, 15),
		new DateTime(2017, 11, 21), new DateTime(2017, 11, 25), new DateTime(2017, 11, 29)
	},
	new double[] { 1.2, 0.3, 2.1, 2.9, 4.2, 5.3 });
```

## ステップ 5: 軸を構成する
日付時刻値を表示するようにグラフの X 軸を構成します。

```csharp
ChartAxis xAxis = chart.AxisX;
xAxis.Scaling.Minimum = new AxisBound(new DateTime(2017, 11, 05).ToOADate());
xAxis.Scaling.Maximum = new AxisBound(new DateTime(2017, 12, 03).ToOADate());
xAxis.MajorUnit = 7;
xAxis.MinorUnit = 1;
xAxis.MajorTickMark = AxisTickMark.Cross;
xAxis.MinorTickMark = AxisTickMark.Outside;
```

## ステップ 6: ドキュメントを保存する
を使用してドキュメントを指定されたディレクトリに保存します。`Save`方法。適切なファイル拡張子を付けて、目的のファイル名を指定します。この例では、ドキュメントを「WorkingWithCharts.DateTimeValuesToAxis.docx」として保存します。

```csharp
doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

### Aspose.Words for .NET を使用した Date Time Values To Axis のソース コード例 

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
	//大単位を 1 週間に設定し、小単位を 1 日に設定します。
	xAxis.MajorUnit = 7;
	xAxis.MinorUnit = 1;
	xAxis.MajorTickMark = AxisTickMark.Cross;
	xAxis.MinorTickMark = AxisTickMark.Outside;
	doc.Save(dataDir + "WorkingWithCharts.DateTimeValuesToAxis.docx");
```

このコード例では、新しい Word 文書を作成し、X 軸に日時値を含む縦棒グラフを挿入し、文書を指定されたディレクトリに保存します。

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用してグラフの軸に日時値を追加する方法を学習しました。ステップバイステップのガイドに従うことで、グラフを作成し、日付時刻値を系列に追加し、日付時刻値を正確に表示するように軸を構成できます。 Aspose.Words for .NET は、Word 文書内のグラフを使用したワープロ用の強力な機能セットを提供し、日付時刻値を使用してデータを効果的に表現および視覚化できるようにします。

### よくある質問

#### Q1. Aspose.Words for .NET を使用してグラフの軸に日時値を追加できますか?
はい、Aspose.Words for .NET を使用すると、Word ドキュメントのグラフの軸に日時値を追加して表示できます。 Aspose.Words は、軸上の日時値の処理など、さまざまな種類のグラフを操作し、外観をカスタマイズするための API と機能を提供します。

#### Q2.日付時刻値をグラフ シリーズに追加するにはどうすればよいですか?
日付時刻の値をグラフ シリーズに追加するには、`Add`チャートの系列のメソッド。カテゴリ (X 軸) データとして日付時刻値の配列と、対応する系列値を指定します。これにより、日付時刻値を含むデータ ポイントをグラフ上にプロットできます。

#### Q3.日付時刻値を表示するように軸を構成するにはどうすればよいですか?
適切なプロパティを設定することで、日付時刻値を表示するようにグラフの軸を構成できます。たとえば、次のコマンドを使用して軸の最小値と最大値を指定できます。`Scaling.Minimum`そして`Scaling.Maximum`それぞれのプロパティ。さらに、主単位と副単位を設定して、軸の間隔と目盛りを定義できます。
