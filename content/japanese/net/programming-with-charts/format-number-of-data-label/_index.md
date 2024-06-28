---
title: グラフ内のデータラベルの番号をフォーマットする
linktitle: グラフ内のデータラベルの番号をフォーマットする
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してグラフ内のデータ ラベルの数を書式設定する方法を学びます。データラベルの数値形式を簡単にカスタマイズします。
type: docs
weight: 10
url: /ja/net/programming-with-charts/format-number-of-data-label/
---

このチュートリアルでは、Aspose.Words for .NET を使用してグラフ内のデータ ラベルの数を書式設定する方法について説明します。提供されているソース コードは、グラフの作成方法、系列データの追加方法、およびデータ ラベルの数値形式のカスタマイズ方法を示しています。

## ステップ 1: プロジェクトをセットアップする

次の前提条件を満たしていることを確認してください。

- Aspose.Words for .NET ライブラリがインストールされています。 NuGet パッケージ マネージャーを使用してダウンロードしてインストールできます。
- 出力ドキュメントが保存されるドキュメント ディレクトリ パス。

## ステップ 2: 新しいドキュメントを作成し、グラフを挿入します。

新しいを作成します`Document`オブジェクトと`DocumentBuilder`ドキュメントを作成します。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

次に、`InsertChart`の方法`DocumentBuilder`。この例では、折れ線グラフを挿入します。

```csharp
Shape shape = builder.InsertChart(ChartType.Line, 432, 252);
Chart chart = shape.Chart;
chart.Title.Text = "Data Labels With Different Number Format";
```

## ステップ 3: 系列データをグラフに追加する

系列データをグラフに追加します。この例では、3 つのカテゴリとそれらに対応する値を追加します。

```csharp
chart.Series.Clear();
ChartSeries series1 = chart.Series.Add("Aspose Series 1", 
    new string[] { "Category 1", "Category 2", "Category 3" }, 
    new double[] { 2.5, 1.5, 3.5 });
series1.HasDataLabels = true;
```

## ステップ 4: データ ラベルの数値形式をカスタマイズする

データ ラベルの数をフォーマットするには、`DataLabels`シリーズにちなんだコレクション。

```csharp
series1.DataLabels.ShowValue = true;
series1.DataLabels[0].NumberFormat.FormatCode = "\"$\"#,##0.00";
series1.DataLabels[1].NumberFormat.FormatCode = "dd/mm/yyyy";
series1.DataLabels[2].NumberFormat.FormatCode = "0.00%";
```

この例では、データ ラベルごとに異なる数値形式を設定します。最初のデータ ラベルは通貨として、2 番目は日付、3 番目はパーセンテージとしてフォーマットされます。

## ステップ 5: ドキュメントを保存する

最後に、次のコマンドを使用してドキュメントを指定したディレクトリに保存します。`Save`の方法`Document`物体。

```csharp
doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

これで、Aspose.Words for .NET を使用してグラフ内のデータ ラベルの数を書式設定する実装が完了しました。

### Aspose.Words for .NET を使用したデータ ラベルの形式番号のソース コードの例 

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
	//または、ソースセルにリンクされるフォーマットコードを設定することもできます。
	//この場合、NumberFormat は一般にリセットされ、ソース セルから継承されます。
	series1.DataLabels[2].NumberFormat.IsLinkedToSource = true;
	doc.Save(dataDir + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用してグラフ内のデータ ラベルの数を書式設定する方法を学習しました。ステップバイステップのガイドに従い、提供されているソース コードを使用すると、要件に応じてグラフを作成し、系列データを追加し、データ ラベルの数値形式をカスタマイズできます。

 Aspose.Words for .NET は、Word ドキュメント内のグラフを使用したワード処理用の包括的な API を提供し、データ ラベルを含むグラフのさまざまな側面を操作できるようにします。にアクセスすることで、`DataLabels`シリーズに関連付けられたコレクションでは、個々のデータ ラベルの数値形式をカスタマイズできます。

API を使用すると、値の表示を制御したり、データ ラベルごとに異なる数値形式を設定したり、数値形式をソース セルにリンクしたりすることができます。この柔軟性により、通貨記号、日付形式、パーセンテージ値などの希望の形式で数値データをグラフに表示できます。

Aspose.Words for .NET を使用すると、強力なグラフ作成機能を .NET アプリケーションに組み込み、完全にフォーマットされたグラフとデータ ラベルを備えた本格的なドキュメントを生成できます。

### よくある質問

#### Q1. Aspose.Words for .NET とは何ですか?
Aspose.Words for .NET は、開発者が .NET アプリケーションで Word ドキュメントをプログラム的に作成、操作、保存できるようにする機能豊富なドキュメント処理ライブラリです。グラフやデータ ラベルなどの文書要素を含むワープロ向けの幅広い機能を提供します。

#### Q2. Aspose.Words for .NET をインストールするにはどうすればよいですか?
Aspose.Words for .NET をインストールするには、Visual Studio の NuGet パッケージ マネージャーを使用してダウンロードします。 NuGet パッケージ マネージャーで「Apose.Words」を検索し、プロジェクトにインストールするだけです。

#### Q3. Aspose.Words for .NET を使用してグラフの他の側面を書式設定できますか?
はい、Aspose.Words for .NET は、グラフのさまざまな側面を書式設定するための広範な機能を提供します。データ ラベルに加えて、グラフの種類、系列データ、軸のプロパティ、凡例、タイトル、プロット エリア、その他のグラフの多くの要素をカスタマイズできます。 API は、グラフの外観と書式設定をきめ細かく制御できます。

#### Q4.同じシリーズ内の異なるデータ ラベルに異なる数値形式を適用できますか?
はい、Aspose.Words for .NET を使用すると、同じシリーズ内の個々のデータ ラベルに異なる数値形式を適用できます。にアクセスすることで、`DataLabels`シリーズに関連付けられたコレクションでは、`FormatCode`各データ ラベルのプロパティを使用して、必要な数値形式を指定します。これにより、同じグラフ内で異なる形式で数値を表示できます。

#### Q5.データ ラベルにカスタムの数値形式を使用できますか?
はい、Aspose.Words for .NET はデータ ラベルのカスタム数値形式をサポートしています。を設定することで、希望の数値形式を指定できます。`FormatCode`データラベルのプロパティをカスタムフォーマットコードに変換します。これにより、通貨記号、日付形式、パーセント値など、幅広い数値形式を柔軟に適用できるようになります。

#### Q6.書式設定されたデータ ラベルを含むグラフをさまざまな形式で保存できますか?
はい。Aspose.Words for .NET を使用すると、書式設定されたデータ ラベルを含むグラフを含むドキュメントを、DOCX、PDF、HTML などのさまざまな形式で保存できます。要件に基づいて適切な形式を選択し、`Save`の方法`Document`ドキュメントを保存するオブジェクト。書式設定されたデータ ラベルは、保存されたドキュメントに保存されます。