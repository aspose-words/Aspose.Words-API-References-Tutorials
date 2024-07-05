---
title: Word 文書にシンプルな縦棒グラフを挿入する
linktitle: Word 文書にシンプルな縦棒グラフを挿入する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、ドキュメントに単純な縦棒グラフを挿入する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-charts/insert-simple-column-chart/
---

このチュートリアルでは、Aspose.Words for .NET を使用して、ドキュメントに単純な縦棒グラフを挿入する方法について説明します。提供されているソース コードでは、グラフを作成し、系列データを追加し、ドキュメントを保存する方法が示されています。

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

次に、`InsertChart`方法の`DocumentBuilder`ドキュメントに縦棒グラフを挿入します。 必要に応じて、さまざまなグラフの種類とサイズを指定できます。

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## ステップ3: グラフに系列データを追加する

グラフに系列データを追加します。この例では、それぞれ 2 つのカテゴリを持つ複数の系列を追加します。

```csharp
ChartSeriesCollection seriesColl = chart.Series;
seriesColl.Clear();

string[] categories = new string[] { "Category 1", "Category 2" };

seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
```

## ステップ4: ドキュメントを保存する

最後に、指定されたディレクトリにドキュメントを保存します。`Save`方法の`Document`物体。

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

これで、Aspose.Words for .NET を使用して単純な縦棒グラフを挿入する実装が完了します。

### Aspose.Words for .NET を使用して単純な縦棒グラフを挿入するためのサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	//さまざまなグラフの種類とサイズを指定できます。
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	ChartSeriesCollection seriesColl = chart.Series;
	Console.WriteLine(seriesColl.Count);
	//デフォルトで生成されたシリーズを削除します。
	seriesColl.Clear();
	//カテゴリ名の配列を作成します。このチュートリアルでは 2 つのカテゴリがあります。
	string[] categories = new string[] { "Category 1", "Category 2" };
	//データ配列は空であってはならず、配列は同じサイズでなければならないことに注意してください。
	seriesColl.Add("Aspose Series 1", categories, new double[] { 1, 2 });
	seriesColl.Add("Aspose Series 2", categories, new double[] { 3, 4 });
	seriesColl.Add("Aspose Series 3", categories, new double[] { 5, 6 });
	seriesColl.Add("Aspose Series 4", categories, new double[] { 7, 8 });
	seriesColl.Add("Aspose Series 5", categories, new double[] { 9, 10 });
	doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して、Word 文書に単純な縦棒グラフを挿入する方法を学習しました。ステップ バイ ステップ ガイドに従い、提供されているソース コードを使用することで、新しい文書を作成し、縦棒グラフを挿入し、カテゴリと対応する値を持つ複数のシリーズを追加し、グラフを含む文書を保存できます。

Aspose.Words for .NET は、Word 文書内のグラフを使用した Words Processing 用の強力で柔軟な API を提供します。シンプルな縦棒グラフは、さまざまなカテゴリのデータを表示および比較する効果的な方法です。Aspose.Words for .NET を使用すると、カスタム データを含む縦棒グラフを簡単に作成し、視覚的に比較できるように複数のシリーズを追加し、要件に応じてグラフの外観をカスタマイズできます。

Aspose.Words for .NET を使用すると、縦棒グラフを含むドキュメントの生成プロセスを自動化し、手動でのドキュメント作成にかかる時間と労力を節約できます。ライブラリには、シンプルな縦棒グラフを含むさまざまなグラフ タイプが用意されており、さまざまなカスタマイズ オプションを使用して、ニーズに合わせてグラフの外観を調整できます。

### よくある質問

#### Q1. 縦棒グラフとは何ですか?
縦棒グラフは、さまざまな高さの縦棒を使用してデータを表示するグラフの一種です。各縦棒はカテゴリを表し、縦棒の高さはそのカテゴリの値に対応します。縦棒グラフは、通常、異なるカテゴリ間でデータを比較したり、時間の経過に伴う変化を追跡したりするために使用されます。

#### Q2. 縦棒グラフに複数の系列を追加できますか?
はい、Aspose.Words for .NET を使用すると、縦棒グラフに複数のシリーズを追加できます。各シリーズは、それぞれのカテゴリと値を持つデータ ポイントのセットを表します。複数のシリーズを追加することで、同じ縦棒グラフ内でさまざまなデータセットを比較および分析し、データを包括的に表示できます。

#### Q3. 縦棒グラフの外観をカスタマイズできますか?
はい、Aspose.Words for .NET を使用すると、縦棒グラフの外観のさまざまな側面をカスタマイズできます。系列の色、軸ラベル、データ ラベル、グラフ領域の書式設定などのプロパティを変更できます。ライブラリには、グラフの視覚要素を制御し、ニーズに合わせてカスタマイズされた外観を作成するための豊富な API セットが用意されています。

#### Q4. 縦棒グラフを挿入したドキュメントを別の形式で保存できますか?
はい、Aspose.Words for .NETでは、挿入された縦棒グラフを含むドキュメントをDOCX、PDF、HTMLなどのさまざまな形式で保存できます。要件に応じて必要な出力形式を選択し、`Save`方法の`Document`オブジェクトをクリックしてドキュメントを保存します。挿入された縦棒グラフは保存されたドキュメントに保存されます。

#### Q5. 縦棒グラフを挿入した後で、データや外観を変更できますか?
はい、ドキュメントに縦棒グラフを挿入した後、Aspose.Words for .NET が提供する API を使用してデータと外観を変更できます。新しいカテゴリと値で系列データを更新したり、列の色と書式を変更したり、軸のプロパティをカスタマイズしたり、さまざまな書式設定オプションを適用したりして、Word ドキュメントに動的で視覚的に魅力的なグラフを作成できます。