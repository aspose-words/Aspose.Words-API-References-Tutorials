---
title: Word 文書にバブル チャートを挿入する
linktitle: Word 文書にバブル チャートを挿入する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントにバブル チャートを挿入する方法を学びます。 X、Y、バブル サイズの値を含む系列データを追加します。
type: docs
weight: 10
url: /ja/net/programming-with-charts/insert-bubble-chart/
---

このチュートリアルでは、Aspose.Words for .NET を使用してバブル チャートをドキュメントに挿入する方法について説明します。提供されているソース コードは、グラフの作成方法、系列データの追加方法、およびドキュメントの保存方法を示しています。

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

次に、`InsertChart`の方法`DocumentBuilder`バブル チャートをドキュメントに挿入します。

```csharp
Shape shape = builder.InsertChart(ChartType.Bubble, 432, 252);
Chart chart = shape.Chart;
```

## ステップ 3: 系列データをグラフに追加する

系列データをグラフに追加します。この例では、対応する X、Y、およびバブル サイズの値を持つ 3 つのデータ ポイントを追加します。

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 },
    new double[] { 10, 4, 8 });
```

## ステップ 4: ドキュメントを保存する

最後に、次のコマンドを使用してドキュメントを指定したディレクトリに保存します。`Save`の方法`Document`物体。

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertBubbleChart.docx");
```

これで、Aspose.Words for .NET を使用したバブル チャートの挿入の実装が完了しました。

### Aspose.Words for .NET を使用したバブル チャートの挿入のソース コード例 

```csharp
//ドキュメントディレクトリへのパス
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.InsertChart(ChartType.Bubble, 432, 252);
Chart chart = shape.Chart;
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 },
	new double[] { 10, 4, 8 });
doc.Save(dataDir + "WorkingWithCharts.InsertBubbleChart.docx");
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書にバブル チャートを挿入する方法を学習しました。ステップバイステップのガイドに従い、提供されているソース コードを使用すると、新しいドキュメントの作成、バブル チャートの挿入、系列データの追加、およびチャートを含むドキュメントの保存を行うことができます。

Aspose.Words for .NET は、Word ドキュメント内のグラフを使用したワード処理用の強力な API を提供します。バブル チャートは 3 次元データを視覚化するのに最適で、各データ ポイントは X 座標と Y 座標およびサイズ値を持つバブルで表されます。 Aspose.Words for .NET を使用すると、データの視覚的表現を強化する動的で有益なバブル チャートを作成できます。

Aspose.Words for .NET を使用すると、バブル チャートを含むドキュメントの生成プロセスを自動化し、手動でドキュメントを作成する時間と労力を節約できます。このライブラリには、幅広いグラフの種類とカスタマイズ オプションが用意されており、Word 文書内に視覚的に魅力的でデータが豊富なグラフを作成できます。

### よくある質問

#### Q1.バブルチャートとは何ですか?
バブル チャートは、泡または球を使用して 3 次元データを表示するチャートの一種です。各データ ポイントはバブルで表され、X 座標と Y 座標によってチャート上のバブルの位置が決まり、バブルのサイズがデータの 3 番目の次元を表します。バブル チャートは、複数の変数間の関係やパターンを視覚化するのに役立ちます。

#### Q2.バブル チャートに複数の系列を追加できますか?
はい、Aspose.Words for .NET を使用して、複数の系列をバブル チャートに追加できます。各シリーズは、それぞれの X、Y、およびバブル サイズの値を持つデータ ポイントのセットを表します。複数のシリーズを追加すると、同じグラフ内でさまざまなデータセットを比較および分析でき、データの包括的なビューが提供されます。

#### Q3.バブル チャートの外観をカスタマイズできますか?
はい、Aspose.Words for .NET を使用すると、バブル チャートの外観のさまざまな側面をカスタマイズできます。シリーズの色、バブルのサイズ、軸ラベル、グラフ領域の書式設定などのプロパティを変更できます。このライブラリは、グラフの視覚要素を制御し、ニーズに合ったカスタマイズされた外観を作成するための豊富な API セットを提供します。

#### Q4.バブル チャートを挿入したドキュメントを別の形式で保存できますか?
はい、Aspose.Words for .NET を使用すると、バブル チャートが挿入されたドキュメントを DOCX、PDF、HTML などのさまざまな形式で保存できます。要件に基づいて希望の出力形式を選択し、`Save`の方法`Document`ドキュメントを保存するオブジェクト。挿入されたバブル チャートは、保存されたドキュメントに保存されます。

#### Q5.バブル チャートを挿入した後にデータと外観を変更できますか?
はい、バブル チャートをドキュメントに挿入した後、Aspose.Words for .NET が提供する API を使用してそのデータと外観を変更できます。系列データの更新、バブル サイズの変更、軸プロパティのカスタマイズ、書式設定オプションの適用を行って、Word 文書内に動的で対話型のグラフを作成できます。