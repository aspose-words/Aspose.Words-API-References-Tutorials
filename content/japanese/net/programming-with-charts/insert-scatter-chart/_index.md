---
title: Word 文書に散布図を挿入する
linktitle: Word 文書に散布図を挿入する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントに散布図を挿入する方法を学びます。X 座標と Y 座標を使用して系列データを追加します。
type: docs
weight: 10
url: /ja/net/programming-with-charts/insert-scatter-chart/
---

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントに散布図を挿入する方法について説明します。提供されているソース コードでは、グラフを作成し、系列データを追加し、ドキュメントを保存する方法が示されています。

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

次に、`InsertChart`方法の`DocumentBuilder`ドキュメントに散布図を挿入します。

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
Chart chart = shape.Chart;
```

## ステップ3: グラフに系列データを追加する

グラフに系列データを追加します。この例では、X 座標と Y 座標の 2 セットを追加します。

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
```

## ステップ4: ドキュメントを保存する

最後に、指定されたディレクトリにドキュメントを保存します。`Save`方法の`Document`物体。

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

これで、Aspose.Words for .NET を使用して散布図を挿入する実装が完了しました。

### Aspose.Words for .NET を使用して散布図を挿入するためのサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
	doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して散布図を Word 文書に挿入する方法を学習しました。ステップ バイ ステップ ガイドに従い、提供されているソース コードを使用することで、新しい文書を作成し、散布図を挿入し、X 座標と Y 座標を含む系列データを追加し、グラフを含む文書を保存できます。

Aspose.Words for .NET は、Word 文書内のグラフを使用した Words Processing 用の包括的な API を提供します。散布図は、2 つの数値変数を使用してデータを視覚化および分析する場合に便利です。Aspose.Words for .NET を使用すると、X 値と Y 値の関係を表す散布図を簡単に作成し、データのパターンや傾向を識別できます。

Aspose.Words for .NET を使用すると、散布図を含むドキュメントの生成プロセスを自動化し、手動でのドキュメント作成にかかる時間と労力を節約できます。ライブラリには、散布図を含むさまざまなグラフの種類が用意されており、ニーズに応じてグラフの外観を調整するためのさまざまなカスタマイズ オプションが用意されています。

### よくある質問

#### Q1. 散布図とは何ですか？
散布図は、2 つの数値変数の関係を表示するグラフの一種です。座標グリッド上にプロットされた一連のポイントで構成され、1 つの変数は X 軸に、もう 1 つの変数は Y 軸に示されます。散布図は、2 セットのデータ ポイント間のパターン、相関関係、または傾向を識別するために使用されます。

#### Q2. 散布図に複数の系列を追加できますか?
はい、Aspose.Words for .NET を使用して、散布図に複数のシリーズを追加できます。各シリーズは、それぞれの X 座標と Y 座標を持つデータ ポイントのセットを表します。複数のシリーズを追加することで、同じ散布図内でさまざまなデータセットを比較および分析し、データを包括的に表示できます。

#### Q3. 散布図の外観をカスタマイズできますか?
はい、Aspose.Words for .NET を使用すると、散布図の外観のさまざまな側面をカスタマイズできます。系列の色、マーカーの形状、軸ラベル、グラフ領域の書式設定などのプロパティを変更できます。ライブラリには、グラフの視覚要素を制御し、ニーズに合わせてカスタマイズされた外観を作成するための豊富な API セットが用意されています。

#### Q4. 散布図を挿入したドキュメントを別の形式で保存できますか?
はい、Aspose.Words for .NETでは、散布図を挿入したドキュメントをDOCX、PDF、HTMLなどのさまざまな形式で保存できます。要件に応じて必要な出力形式を選択し、`Save`方法の`Document`オブジェクトをクリックしてドキュメントを保存します。挿入された散布図は保存されたドキュメントに保存されます。

#### Q5. 散布図を挿入した後で、データや外観を変更できますか?
はい、ドキュメントに散布図を挿入した後、Aspose.Words for .NET が提供する API を使用してデータと外観を変更できます。新しい X 座標と Y 座標で系列データを更新したり、マーカーの形状と色を変更したり、軸のプロパティをカスタマイズしたり、書式設定オプションを適用したりして、Word ドキュメントに動的でインタラクティブなグラフを作成できます。