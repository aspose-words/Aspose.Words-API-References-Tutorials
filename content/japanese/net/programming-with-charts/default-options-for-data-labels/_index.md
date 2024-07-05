---
title: グラフのデータラベルのデフォルトオプションを設定する
linktitle: グラフのデータラベルのデフォルトオプションを設定する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してグラフのデータ ラベルの既定のオプションを設定する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-charts/default-options-for-data-labels/
---

このチュートリアルでは、Aspose.Words for .NET を使用してグラフのデータ ラベルの既定のオプションを設定する方法について説明します。提供されているコードは、Aspose.Words を使用してグラフを作成し、データ シリーズを追加し、データ ラベルをカスタマイズする方法を示しています。

## ステップ1: プロジェクトを設定する

始める前に、次の要件が満たされていることを確認してください。

- Aspose.Words for .NET ライブラリがインストールされました。NuGet パッケージ マネージャーを使用してダウンロードし、インストールできます。
- 出力ドキュメントが保存されるドキュメント ディレクトリ パス。

## ステップ2: 新しいドキュメントを作成し、グラフを挿入する

まず、新しい`Document`オブジェクトと`DocumentBuilder`ドキュメントを作成します。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

次に、`InsertChart`方法の`DocumentBuilder`この例では、円グラフを挿入します。

```csharp
Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
Chart chart = shape.Chart;
```

## ステップ3: グラフにデータ系列を追加する

次に、グラフにデータ系列を追加しましょう。この例では、3 つのカテゴリとそれに対応する値を追加します。

```csharp
chart.Series.Clear();
ChartSeries series = chart.Series.Add("Aspose Series 1",
    new string[] { "Category 1", "Category 2", "Category 3" },
    new double[] { 2.7, 3.2, 0.8 });
```

## ステップ4: データラベルをカスタマイズする

グラフのデータラベルをカスタマイズするには、`ChartDataLabelCollection`シリーズに関連付けられたオブジェクト。

```csharp
ChartDataLabelCollection labels = series.DataLabels;
```

その後、さまざまなプロパティを変更できます`labels`オブジェクトを使用して、データ ラベルに必要なオプションを設定します。この例では、パーセンテージと値の表示を有効にし、リーダー ラインを無効にして、カスタム セパレーターを設定します。

```csharp
labels.ShowPercentage = true;
labels.ShowValue = true;
labels.ShowLeaderLines = false;
labels.Separator = " - ";
```

## ステップ5: ドキュメントを保存する

最後に、指定されたディレクトリにドキュメントを保存します。`Save`方法の`Document`物体。

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

これで、Aspose.Words for .NET を使用してグラフのデータ ラベルの既定のオプションを設定する実装が完了します。

### Aspose.Words for .NET を使用したデータ ラベルの既定のオプションのサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	ChartSeries series = chart.Series.Add("Aspose Series 1",
		new string[] { "Category 1", "Category 2", "Category 3" },
		new double[] { 2.7, 3.2, 0.8 });
	ChartDataLabelCollection labels = series.DataLabels;
	labels.ShowPercentage = true;
	labels.ShowValue = true;
	labels.ShowLeaderLines = false;
	labels.Separator = " - ";
	doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用してグラフのデータ ラベルの既定のオプションを設定する方法を学習しました。ステップ バイ ステップ ガイドに従うことで、グラフを作成し、データ シリーズを追加し、特定の要件に合わせてデータ ラベルをカスタマイズできます。Aspose.Words for .NET は、Word 文書内のグラフを使用した Words Processing 用の強力な API を提供し、さまざまなグラフ要素を操作して、必要な外観と機能を実現できます。

プロパティを設定することで`ChartDataLabelCollection`グラフ シリーズに関連付けられたオブジェクトを使用すると、パーセンテージ、値、リーダー ライン、カスタム セパレーターの表示などのオプションを含むデータ ラベルの表示を制御できます。この柔軟性により、データを効果的に表示し、グラフの視覚的表現を強化できます。

### よくある質問

#### Q1. Aspose.Words for .NET とは何ですか?
Aspose.Words for .NET は、開発者が .NET アプリケーションを使用してプログラムで Word 文書を作成、操作、保存できるようにするライブラリです。チャートなどの文書要素を使用して Words を処理するための幅広い機能を提供します。

#### Q2. Aspose.Words for .NET をインストールするにはどうすればよいですか?
Aspose.Words for .NET は、Visual Studio の NuGet パッケージ マネージャーを使用してダウンロードすることでインストールできます。NuGet パッケージ マネージャーで「Aspose.Words」を検索し、プロジェクトにインストールするだけです。

#### Q3. Aspose.Words for .NET を使用してグラフの他の側面をカスタマイズできますか?
はい、Aspose.Words for .NET を使用すると、グラフの種類、軸ラベル、凡例、プロット領域など、グラフのさまざまな側面をカスタマイズできます。グラフ オブジェクトのさまざまなプロパティにアクセスして変更し、希望する外観と動作を実現できます。

#### Q4. チャートを異なる形式で保存できますか?
はい、Aspose.Words for .NETは、DOCX、PDF、HTMLなど、さまざまな形式でチャートを含むドキュメントの保存をサポートしています。要件に基づいて適切な形式を選択し、`Save`方法の`Document`ドキュメントを保存するオブジェクト。

#### Q5. これらのテクニックを他の種類のチャートにも適用できますか?
はい、このチュートリアルで説明する手法は、Aspose.Words for .NET でサポートされている他の種類のグラフにも適用できます。重要なのは、Words 処理に使用しているグラフの種類に固有の関連オブジェクトとプロパティにアクセスすることです。