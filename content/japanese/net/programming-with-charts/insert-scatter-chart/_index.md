---
title: Word 文書に散布図を挿入する
linktitle: Word 文書に散布図を挿入する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して散布図をドキュメントに挿入する方法を学習します。 X 座標と Y 座標を含む系列データを追加します。
type: docs
weight: 10
url: /ja/net/programming-with-charts/insert-scatter-chart/
---

このチュートリアルでは、Aspose.Words for .NET を使用して散布図をドキュメントに挿入する方法について説明します。提供されているソース コードは、グラフの作成方法、系列データの追加方法、およびドキュメントの保存方法を示しています。

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

次に、`InsertChart`の方法`DocumentBuilder`散布図をドキュメントに挿入します。

```csharp
Shape shape = builder.InsertChart(ChartType.Scatter, 432, 252);
Chart chart = shape.Chart;
```

## ステップ 3: 系列データをグラフに追加する

系列データをグラフに追加します。この例では、X 座標と Y 座標の 2 セットを追加します。

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 });
```

## ステップ 4: ドキュメントを保存する

最後に、次のコマンドを使用してドキュメントを指定したディレクトリに保存します。`Save`の方法`Document`物体。

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertScatterChart.docx");
```

これで、Aspose.Words for .NET を使用した散布図の挿入の実装が完了しました。

### Aspose.Words for .NET を使用した散布図の挿入のソース コード例 

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

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書に散布図を挿入する方法を学習しました。ステップバイステップのガイドに従い、提供されているソース コードを使用すると、新しいドキュメントの作成、散布図の挿入、X および Y 座標を含む系列データの追加、グラフとともにドキュメントの保存を行うことができます。

Aspose.Words for .NET は、Word ドキュメント内のグラフを使用したワード処理用の包括的な API を提供します。散布図は、2 つの数値変数を使用してデータを視覚化および分析するのに役立ちます。 Aspose.Words for .NET を使用すると、X 値と Y 値の関係を表す散布図を簡単に作成し、データのパターンや傾向を特定できます。

Aspose.Words for .NET を使用すると、散布図を使用してドキュメントを生成するプロセスを自動化し、手動でドキュメントを作成する時間と労力を節約できます。このライブラリは、散布図などの幅広い種類のグラフを提供し、ニーズに応じてグラフの外観を調整するためのさまざまなカスタマイズ オプションを提供します。

### よくある質問

#### Q1.散布図とは何ですか?
散布図は、2 つの数値変数間の関係を表示するグラフの一種です。これは、座標グリッド上にプロットされた一連の点で構成され、1 つの変数は X 軸で表され、もう 1 つの変数は Y 軸で表されます。散布図は、2 セットのデータ ポイント間のパターン、相関関係、または傾向を識別するために使用されます。

#### Q2.散布図に複数の系列を追加できますか?
はい、Aspose.Words for .NET を使用して複数の系列を散布図に追加できます。各シリーズは、それぞれの X 座標と Y 座標を持つデータ ポイントのセットを表します。複数の系列を追加すると、同じ散布図内の異なるデータセットを比較および分析でき、データの包括的なビューが提供されます。

#### Q3.散布図の外観をカスタマイズできますか?
はい、Aspose.Words for .NET を使用すると、散布図の外観のさまざまな側面をカスタマイズできます。シリーズの色、マーカーの形状、軸ラベル、グラフ領域の書式設定などのプロパティを変更できます。このライブラリは、グラフの視覚要素を制御し、ニーズに合ったカスタマイズされた外観を作成するための豊富な API セットを提供します。

#### Q4.散布図を挿入したドキュメントを別の形式で保存できますか?
はい、Aspose.Words for .NET を使用すると、散布図が挿入されたドキュメントを DOCX、PDF、HTML などのさまざまな形式で保存できます。要件に基づいて希望の出力形式を選択し、`Save`の方法`Document`ドキュメントを保存するオブジェクト。挿入された散布図は、保存されたドキュメントに保存されます。

#### Q5.散布図を挿入した後に、散布図のデータと外観を変更できますか?
はい、散布図をドキュメントに挿入した後、Aspose.Words for .NET が提供する API を使用してそのデータと外観を変更できます。新しい X 座標と Y 座標で系列データを更新し、マーカーの形状と色を変更し、軸プロパティをカスタマイズし、書式設定オプションを適用して、Word 文書内に動的で対話型のグラフを作成できます。