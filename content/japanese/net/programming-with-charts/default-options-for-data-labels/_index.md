---
title: グラフのデータラベルのデフォルトオプションを設定する
linktitle: グラフのデータラベルのデフォルトオプションを設定する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してグラフ内のデータ ラベルのデフォルト オプションを設定する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-charts/default-options-for-data-labels/
---

このチュートリアルでは、Aspose.Words for .NET を使用してグラフ内のデータ ラベルのデフォルト オプションを設定する方法について説明します。提供されているコードは、Aspose.Words を使用してグラフを作成し、データ シリーズを追加し、データ ラベルをカスタマイズする方法を示しています。

## ステップ 1: プロジェクトをセットアップする

始める前に、次の要件が満たされていることを確認してください。

- Aspose.Words for .NET ライブラリがインストールされています。 NuGet パッケージ マネージャーを使用してダウンロードしてインストールできます。
- 出力ドキュメントが保存されるドキュメント ディレクトリ パス。

## ステップ 2: 新しいドキュメントを作成し、グラフを挿入する

まず、新しいものを作成しましょう`Document`オブジェクトと`DocumentBuilder`ドキュメントを作成します。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

次に、`InsertChart`の方法`DocumentBuilder`。この例では、円グラフを挿入します。

```csharp
Shape shape = builder.InsertChart(ChartType.Pie, 432, 252);
Chart chart = shape.Chart;
```

## ステップ 3: データ系列をグラフに追加する

次に、データ系列をグラフに追加しましょう。この例では、3 つのカテゴリとそれらに対応する値を追加します。

```csharp
chart.Series.Clear();
ChartSeries series = chart.Series.Add("Aspose Series 1",
    new string[] { "Category 1", "Category 2", "Category 3" },
    new double[] { 2.7, 3.2, 0.8 });
```

## ステップ 4: データラベルをカスタマイズする

グラフ内のデータ ラベルをカスタマイズするには、`ChartDataLabelCollection`シリーズに関連付けられたオブジェクト。

```csharp
ChartDataLabelCollection labels = series.DataLabels;
```

次に、のさまざまなプロパティを変更できます。`labels`オブジェクトを使用して、データ ラベルに必要なオプションを設定します。この例では、パーセンテージと値の表示を有効にし、引出線を無効にし、カスタム区切り文字を設定します。

```csharp
labels.ShowPercentage = true;
labels.ShowValue = true;
labels.ShowLeaderLines = false;
labels.Separator = " - ";
```

## ステップ 5: ドキュメントを保存する

最後に、次のコマンドを使用してドキュメントを指定されたディレクトリに保存します。`Save`の方法`Document`物体。

```csharp
doc.Save(dataDir + "WorkingWithCharts.DefaultOptionsForDataLabels.docx");
```

これで、Aspose.Words for .NET を使用してグラフ内のデータ ラベルのデフォルト オプションを設定する実装が完了しました。

### Aspose.Words for .NET を使用したデータ ラベルのデフォルト オプションのソース コードの例 

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

このチュートリアルでは、Aspose.Words for .NET を使用してグラフ内のデータ ラベルのデフォルト オプションを設定する方法を学習しました。ステップバイステップのガイドに従うことで、特定の要件に合わせてグラフを作成し、データ系列を追加し、データ ラベルをカスタマイズできます。 Aspose.Words for .NET は、Word 文書内のグラフを使用した Word Processing 用の強力な API を提供し、さまざまなグラフ要素を操作して、目的の外観と機能を実現できます。

のプロパティを設定することで、`ChartDataLabelCollection`グラフ シリーズに関連付けられたオブジェクトを使用すると、パーセンテージ、値、引出線、カスタム区切り記号の表示などのオプションを含む、データ ラベルの表示を制御できます。この柔軟性により、データを効果的に表示し、グラフの視覚的表現を向上させることができます。

### よくある質問

#### Q1. Aspose.Words for .NET とは何ですか?
Aspose.Words for .NET は、開発者が .NET アプリケーションを使用してプログラムで Word ドキュメントを作成、操作、保存できるようにするライブラリです。グラフなどの文書要素を含むワープロ向けの幅広い機能を提供します。

#### Q2. Aspose.Words for .NET をインストールするにはどうすればよいですか?
Aspose.Words for .NET をインストールするには、Visual Studio の NuGet パッケージ マネージャーを使用してダウンロードします。 NuGet パッケージ マネージャーで「Aspose.Words」を検索し、プロジェクトにインストールするだけです。

#### Q3. Aspose.Words for .NET を使用してグラフの他の側面をカスタマイズできますか?
はい、Aspose.Words for .NET を使用すると、グラフの種類、軸ラベル、凡例、プロット領域など、グラフのさまざまな側面をカスタマイズできます。チャート オブジェクトのさまざまなプロパティにアクセスして変更し、目的の外観と動作を実現できます。

#### Q4.グラフを別の形式で保存できますか?
はい。Aspose.Words for .NET は、グラフを含むドキュメントを DOCX、PDF、HTML などのさまざまな形式で保存することをサポートしています。要件に基づいて適切な形式を選択し、`Save`の方法`Document`ドキュメントを保存するオブジェクト。

#### Q5.これらのテクニックを他の種類のチャートに適用できますか?
はい、このチュートリアルで説明する手法は、Aspose.Words for .NET でサポートされている他のグラフ タイプに適用できます。重要なのは、ワープロ処理に使用しているグラフの種類に固有の関連オブジェクトとプロパティにアクセスすることです。