---
title: グラフのデータラベルをカスタマイズする
linktitle: グラフのデータラベルをカスタマイズする
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してグラフにデータ ラベルを追加およびカスタマイズし、データ ポイントに関する追加情報を提供する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-charts/chart-data-label/
---

このチュートリアルでは、Aspose.Words for .NET を使用してグラフにデータ ラベルを追加およびカスタマイズする方法について説明します。データ ラベルは、グラフ内のデータ ポイントに関する追加情報を提供します。

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

## ステップ 3: グラフの挿入と構成
を使用してドキュメントにグラフを挿入します。`InsertChart`の方法`DocumentBuilder`物体。必要なグラフの種類と寸法を設定します。

```csharp
Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
Chart chart = shape.Chart;
```

## ステップ 4: データラベルをカスタマイズする
グラフ シリーズのデータ ラベル コレクションにアクセスし、さまざまなプロパティを変更してデータ ラベルの外観をカスタマイズします。

```csharp
ChartSeries series0 = shape.Chart.Series[0];
ChartDataLabelCollection labels = series0.DataLabels;
labels.ShowLegendKey = true;
labels.ShowLeaderLines = true;
labels.ShowCategoryName = false;
labels.ShowPercentage = false;
labels.ShowSeriesName = true;
labels.ShowValue = true;
labels.Separator = "/";
```

## ステップ 5: ドキュメントを保存する
を使用してドキュメントを指定されたディレクトリに保存します。`Save`方法。適切なファイル拡張子を付けて、目的のファイル名を指定します。この例では、ドキュメントを「WorkingWithCharts.ChartDataLabel.docx」として保存します。

```csharp
doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

### Aspose.Words for .NET を使用したグラフ データ ラベルのソース コード例 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
	Chart chart = shape.Chart;
	ChartSeries series0 = shape.Chart.Series[0];
	ChartDataLabelCollection labels = series0.DataLabels;
	labels.ShowLegendKey = true;
	//デフォルトでは、円グラフのデータ ポイントにデータ ラベルを追加すると、データ ラベルに引出線が表示されます。
	//データポイントの終端のはるか外側に配置されます。引き出し線は、データ ラベルとそのラベルの間に視覚的なつながりを作成します。
	//対応するデータポイント。
	labels.ShowLeaderLines = true;
	labels.ShowCategoryName = false;
	labels.ShowPercentage = false;
	labels.ShowSeriesName = true;
	labels.ShowValue = true;
	labels.Separator = "/";
	labels.ShowValue = true;
	doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

それでおしまい！ Aspose.Words for .NET を使用してグラフにデータ ラベルを追加し、カスタマイズすることができました。

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用してグラフにデータ ラベルを追加およびカスタマイズする方法を学習しました。ステップバイステップのガイドに従うことで、グラフを挿入し、データ ラベル コレクションにアクセスし、プロパティを変更してデータ ラベルの外観をカスタマイズできます。 Aspose.Words for .NET は、Word ドキュメントとグラフを使用したワード処理用の強力な API を提供し、カスタマイズされたデータ ラベルを使用して、視覚的に魅力的で有益なグラフを作成できるようにします。

### よくある質問

#### Q1.グラフ内のデータ ラベルとは何ですか?
グラフ内のデータ ラベルは、グラフ内に表されるデータ ポイントに関する追加情報を提供します。グラフのタイプと構成に応じて、値、カテゴリ、シリーズ名、パーセンテージ、またはその他の関連詳細を表示できます。

#### Q2.データラベルの外観をカスタマイズできますか?
はい、グラフ内のデータ ラベルの外観をカスタマイズできます。 Aspose.Words for .NET には、凡例キー、引出線、カテゴリ名、シリーズ名、値などの表示など、データ ラベルのさまざまなプロパティを変更するオプションが用意されています。特定の要件に合わせて区切り文字を設定し、ラベルを書式設定することもできます。

#### Q3.任意の種類のグラフにデータ ラベルを追加できますか?
はい、棒グラフ、円グラフ、折れ線グラフなど、さまざまな種類のグラフにデータ ラベルを追加できます。データ ラベルの追加およびカスタマイズのプロセスは、グラフの種類および使用しているライブラリまたはツールによって若干異なる場合があります。
