---
title: Word 文書に単純な縦棒グラフを挿入する
linktitle: Word 文書に単純な縦棒グラフを挿入する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、単純な縦棒グラフをドキュメントに挿入する方法を学びます。
type: docs
weight: 10
url: /ja/net/programming-with-charts/insert-simple-column-chart/
---

このチュートリアルでは、Aspose.Words for .NET を使用して単純な縦棒グラフをドキュメントに挿入する方法について説明します。提供されているソース コードは、グラフの作成方法、系列データの追加方法、およびドキュメントの保存方法を示しています。

## ステップ 1: プロジェクトをセットアップする

次の前提条件を満たしていることを確認してください。

- Aspose.Words for .NET ライブラリがインストールされています。 NuGet パッケージ マネージャーを使用してダウンロードしてインストールできます。
- 出力ドキュメントが保存されるドキュメント ディレクトリ パス。

## ステップ 2: 新しいドキュメントを作成し、グラフを挿入する

新しいを作成します`Document`オブジェクトと`DocumentBuilder`ドキュメントを作成します。

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

次に、`InsertChart`の方法`DocumentBuilder`縦棒グラフをドキュメントに挿入します。要件に応じて、さまざまなグラフの種類とサイズを指定できます。

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## ステップ 3: 系列データをグラフに追加する

系列データをグラフに追加します。この例では、それぞれ 2 つのカテゴリを持つ複数のシリーズを追加します。

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

## ステップ 4: ドキュメントを保存する

最後に、次のコマンドを使用してドキュメントを指定したディレクトリに保存します。`Save`の方法`Document`物体。

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

これで、Aspose.Words for .NET を使用して単純な縦棒グラフを挿入する実装が完了しました。

### Aspose.Words for .NET を使用した単純な縦棒グラフの挿入のソース コード例 

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

このチュートリアルでは、Aspose.Words for .NET を使用して単純な縦棒グラフを Word 文書に挿入する方法を学習しました。ステップバイステップのガイドに従い、提供されているソース コードを使用すると、新しいドキュメントを作成し、縦棒グラフを挿入し、カテゴリと対応する値を含む複数の系列を追加し、ドキュメントをグラフとともに保存することができます。

Aspose.Words for .NET は、Word ドキュメント内のグラフを使用したワード処理用の強力で柔軟な API を提供します。単純な縦棒グラフは、さまざまなカテゴリのデータを表し、比較するのに効果的な方法です。 Aspose.Words for .NET を使用すると、カスタム データを使用して縦棒グラフを簡単に作成したり、視覚的に比較するために複数の系列を追加したり、要件に応じてグラフの外観をカスタマイズしたりできます。

Aspose.Words for .NET を使用すると、縦棒グラフを含むドキュメントの生成プロセスを自動化し、手動でドキュメントを作成する時間と労力を節約できます。このライブラリは、単純な縦棒グラフを含む幅広い種類のグラフを提供し、ニーズに合わせてグラフの外観を調整するためのさまざまなカスタマイズ オプションを提供します。

### よくある質問

#### Q1.縦棒グラフとは何ですか?
縦棒グラフは、さまざまな高さの縦棒を使用してデータを表示するグラフの一種です。各列はカテゴリを表し、列の高さはそのカテゴリの値に対応します。縦棒グラフは、さまざまなカテゴリ間でデータを比較したり、経時的な変化を追跡したりするためによく使用されます。

#### Q2.複数の系列を縦棒グラフに追加できますか?
はい、Aspose.Words for .NET を使用すると、複数の系列を縦棒グラフに追加できます。各シリーズは、それぞれのカテゴリと値を持つ一連のデータ ポイントを表します。複数のシリーズを追加すると、同じ縦棒グラフ内でさまざまなデータセットを比較および分析でき、データの包括的なビューが提供されます。

#### Q3.縦棒グラフの外観をカスタマイズできますか?
はい、Aspose.Words for .NET を使用すると、縦棒グラフの外観のさまざまな側面をカスタマイズできます。シリーズの色、軸ラベル、データ ラベル、グラフ領域の書式設定などのプロパティを変更できます。このライブラリは、グラフの視覚要素を制御し、ニーズに合ったカスタマイズされた外観を作成するための豊富な API セットを提供します。

#### Q4.縦棒グラフを挿入したドキュメントを別の形式で保存できますか?
はい、Aspose.Words for .NET を使用すると、縦棒グラフが挿入されたドキュメントを DOCX、PDF、HTML などのさまざまな形式で保存できます。要件に基づいて希望の出力形式を選択し、`Save`の方法`Document`ドキュメントを保存するオブジェクト。挿入された縦棒グラフは、保存されたドキュメントに保存されます。

#### Q5.縦棒グラフを挿入した後にデータと外観を変更できますか?
はい、縦棒グラフをドキュメントに挿入した後、Aspose.Words for .NET が提供する API を使用してそのデータと外観を変更できます。新しいカテゴリと値で系列データを更新し、列の色と書式を変更し、軸のプロパティをカスタマイズし、さまざまな書式オプションを適用して、Word 文書内に動的で視覚的に魅力的なグラフを作成できます。