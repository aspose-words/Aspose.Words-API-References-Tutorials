---
title: グラフデータラベルをカスタマイズする
linktitle: グラフデータラベルをカスタマイズする
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してグラフにデータ ラベルを追加およびカスタマイズし、データ ポイントに関する追加情報を提供する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-charts/chart-data-label/
---

このチュートリアルでは、Aspose.Words for .NET を使用してグラフにデータ ラベルを追加およびカスタマイズする方法について説明します。データ ラベルは、グラフ内のデータ ポイントに関する追加情報を提供します。

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

## ステップ3: グラフを挿入して構成する
ドキュメントにグラフを挿入するには、`InsertChart`方法の`DocumentBuilder`オブジェクト。希望するグラフの種類と寸法を設定します。

```csharp
Shape shape = builder.InsertChart(ChartType.Bar, 432, 252);
Chart chart = shape.Chart;
```

## ステップ4: データラベルをカスタマイズする
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

## ステップ5: ドキュメントを保存する
指定されたディレクトリにドキュメントを保存するには、`Save`メソッド。適切なファイル拡張子を持つファイル名を指定します。この例では、ドキュメントを「WorkingWithCharts.ChartDataLabel.docx」として保存します。

```csharp
doc.Save(dataDir + "WorkingWithCharts.ChartDataLabel.docx");
```

### Aspose.Words for .NET を使用したチャート データ ラベルのサンプル ソース コード 

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
	//デフォルトでは、円グラフのデータポイントにデータラベルを追加すると、データラベルに引出線が表示されます。
	//データポイントの端からかなり外側に配置されます。リーダーラインはデータラベルとそのラベルの間に視覚的なつながりを作り出します。
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

これで完了です。Aspose.Words for .NET を使用して、グラフにデータ ラベルを追加し、カスタマイズできました。

## 結論
このチュートリアルでは、Aspose.Words for .NET を使用してグラフにデータ ラベルを追加およびカスタマイズする方法を学習しました。ステップ バイ ステップ ガイドに従うことで、グラフを挿入し、データ ラベル コレクションにアクセスし、プロパティを変更してデータ ラベルの外観をカスタマイズできます。Aspose.Words for .NET は、Word ドキュメントとグラフを使用した Words Processing 用の強力な API を提供し、カスタマイズされたデータ ラベルを使用して視覚的に魅力的で情報豊富なグラフを作成できます。

### よくある質問

#### Q1. グラフのデータ ラベルとは何ですか?
グラフのデータ ラベルは、グラフに表示されるデータ ポイントに関する追加情報を提供します。グラフの種類と構成に応じて、値、カテゴリ、系列名、パーセンテージ、その他の関連詳細を表示できます。

#### Q2. データ ラベルの外観をカスタマイズできますか?
はい、グラフ内のデータ ラベルの外観をカスタマイズできます。Aspose.Words for .NET には、凡例キー、引き出し線、カテゴリ名、シリーズ名、値などの表示など、データ ラベルのさまざまなプロパティを変更するオプションが用意されています。また、区切り線を設定したり、特定の要件に合わせてラベルの書式を設定したりすることもできます。

#### Q3. どの種類のグラフにもデータ ラベルを追加できますか?
はい、棒グラフ、円グラフ、折れ線グラフなど、さまざまな種類のグラフにデータ ラベルを追加できます。データ ラベルを追加およびカスタマイズするプロセスは、グラフの種類や使用しているライブラリまたはツールによって若干異なる場合があります。
