---
title: グラフのデータラベルの数値をフォーマットする
linktitle: グラフのデータラベルの数値をフォーマットする
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してグラフ内のデータ ラベルの数をフォーマットする方法を学びます。データ ラベルの数値フォーマットを簡単にカスタマイズします。
type: docs
weight: 10
url: /ja/net/programming-with-charts/format-number-of-data-label/
---

このチュートリアルでは、Aspose.Words for .NET を使用してグラフ内のデータ ラベルの数をフォーマットする方法について説明します。提供されているソース コードでは、グラフを作成し、系列データを追加し、データ ラベルの数値形式をカスタマイズする方法が示されています。

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

次に、`InsertChart`方法の`DocumentBuilder`この例では、折れ線グラフを挿入します。

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
chart.Title.Text = "Data Labels With Different Number Format";
```

## ステップ3: グラフに系列データを追加する

グラフに系列データを追加します。この例では、3 つのカテゴリとそれに対応する値を追加します。

```csharp
chart.Series.Clear();
ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
    new string[] { "Category 1", "Category 2", "Category 3" }, 
    new double[] { 2.5, 1.5, 3.5 });
series1.HasDataLabels = true;
```

## ステップ4: データラベルの数値形式をカスタマイズする

データラベルの数をフォーマットするには、`DataLabels`シリーズに関連したコレクション。

```csharp
series1.DataLabels.ShowValue = true;
series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
```

この例では、各データ ラベルに異なる数値形式を設定します。最初のデータ ラベルは通貨として、2 番目は日付として、3 番目はパーセンテージとして書式設定されます。

## ステップ5: ドキュメントを保存する

最後に、指定されたディレクトリにドキュメントを保存します。`Save`方法の`Document`物体。

```csharp
doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

これで、Aspose.Words for .NET を使用してグラフ内のデータ ラベルの数をフォーマットする実装が完了します。

### Aspose.Words for .NET を使用してデータ ラベルの数値をフォーマットするためのサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
	Chart chart = shape.Chart;
	chart.Title.Text = "Data Labels With Different Number Format";
	//デフォルトで生成されたシリーズを削除します。
	chart.Series.Clear();
	ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
		new string[] { "Category 1", "Category 2", "Category 3" }, 
		new double[] { 2.5, 1.5, 3.5 });
	series1.HasDataLabels = true;
	series1.DataLabels.ShowValue = true;
	series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
	series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
	series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
	//または、書式コードをソースセルにリンクするように設定することもできます。
	//この場合、NumberFormat は一般にリセットされ、ソース セルから継承されます。
	series1.DataLabels[2].NumberFormat.IsLinkedToSource = true;
	doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用してグラフ内のデータ ラベルの数をフォーマットする方法を学習しました。ステップ バイ ステップ ガイドに従い、提供されているソース コードを使用することで、グラフを作成し、系列データを追加し、要件に応じてデータ ラベルの数値形式をカスタマイズできます。

 Aspose.Words for .NETは、Word文書内のグラフを処理するための包括的なAPIを提供し、データラベルを含むグラフのさまざまな側面を操作できます。`DataLabels`系列に関連付けられたコレクションでは、個々のデータ ラベルの数値形式をカスタマイズできます。

API を使用すると、値の表示を制御し、データ ラベルごとに異なる数値形式を設定し、数値形式をソース セルにリンクすることができます。この柔軟性により、通貨記号、日付形式、パーセンテージ値などの必要な書式を使用して、グラフに数値データを表示できます。

Aspose.Words for .NET を使用すると、強力なグラフ作成機能を .NET アプリケーションに組み込み、完全にフォーマットされたグラフとデータ ラベルを含むプロフェッショナルな外観のドキュメントを生成できます。

### よくある質問

#### Q1. Aspose.Words for .NET とは何ですか?
Aspose.Words for .NET は、開発者が .NET アプリケーションでプログラムを使用して Word 文書を作成、操作、保存できるようにする機能豊富なドキュメント処理ライブラリです。グラフやデータ ラベルなどのドキュメント要素を使用して Words を処理するための幅広い機能を提供します。

#### Q2. Aspose.Words for .NET をインストールするにはどうすればよいですか?
Aspose.Words for .NET は、Visual Studio の NuGet パッケージ マネージャーを使用してダウンロードすることでインストールできます。NuGet パッケージ マネージャーで「Aspose.Words」を検索し、プロジェクトにインストールするだけです。

#### Q3. Aspose.Words for .NET を使用してグラフの他の部分をフォーマットできますか?
はい、Aspose.Words for .NET は、グラフのさまざまな側面を書式設定するための広範な機能を提供します。データ ラベルに加えて、グラフの種類、系列データ、軸のプロパティ、凡例、タイトル、プロット領域、およびグラフのその他の多くの要素をカスタマイズできます。API は、グラフの外観と書式設定を細かく制御します。

#### Q4. 同じ系列内の異なるデータ ラベルに異なる数値書式を適用できますか?
はい、Aspose.Words for .NETでは、同じ系列内の個々のデータラベルに異なる数値書式を適用できます。`DataLabels`シリーズに関連付けられたコレクションでは、`FormatCode`各データ ラベルの プロパティを使用して、必要な数値形式を指定します。これにより、同じグラフ内で数値をさまざまな形式で表示できます。

#### Q5. データ ラベルにカスタム数値形式を使用できますか?
はい、Aspose.Words for .NETはデータラベルのカスタム数値書式をサポートしています。`FormatCode`データ ラベルのプロパティをカスタム書式コードに適用します。これにより、通貨記号、日付形式、パーセンテージ値など、さまざまな数値形式を柔軟に適用できます。

#### Q6. フォーマットされたデータ ラベルを含むグラフを別の形式で保存できますか?
はい、Aspose.Words for .NETでは、DOCX、PDF、HTMLなど、さまざまな形式でフォーマットされたデータラベルを含むチャートを含むドキュメントを保存できます。要件に基づいて適切な形式を選択し、`Save`方法の`Document`オブジェクトを使用してドキュメントを保存します。保存されたドキュメントには、書式設定されたデータ ラベルが保持されます。