---
title: Word 文書にバブル チャートを挿入する
linktitle: Word 文書にバブル チャートを挿入する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメントにバブル チャートを挿入する方法を学習します。X、Y、バブル サイズの値を持つシリーズ データを追加します。
type: docs
weight: 10
url: /ja/net/programming-with-charts/insert-bubble-chart/
---

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメントにバブル チャートを挿入する方法について説明します。提供されているソース コードでは、チャートを作成し、系列データを追加し、ドキュメントを保存する方法が示されています。

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

次に、`InsertChart`方法の`DocumentBuilder`ドキュメントにバブルチャートを挿入します。

```csharp
Shape shape = builder.InsertChart(ChartType.Bubble, 432, 252);
Chart chart = shape.Chart;
```

## ステップ3: グラフに系列データを追加する

グラフに系列データを追加します。この例では、対応する X、Y、バブル サイズの値を持つ 3 つのデータ ポイントを追加します。

```csharp
chart.Series.Add("Aspose Series 1", new double[] { 0.7, 1.8, 2.6 }, new double[] { 2.7, 3.2, 0.8 },
    new double[] { 10, 4, 8 });
```

## ステップ4: ドキュメントを保存する

最後に、指定されたディレクトリにドキュメントを保存します。`Save`方法の`Document`物体。

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertBubbleChart.docx");
```

これで、Aspose.Words for .NET を使用してバブル チャートを挿入する実装が完了します。

### Aspose.Words for .NET を使用してバブル チャートを挿入するためのサンプル ソース コード 

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

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書にバブル チャートを挿入する方法を学習しました。ステップ バイ ステップ ガイドに従い、提供されているソース コードを使用することで、新しい文書を作成し、バブル チャートを挿入し、系列データを追加し、チャートを含む文書を保存できます。

Aspose.Words for .NET は、Word 文書内のグラフを使用した Words Processing 用の強力な API を提供します。バブル チャートは、各データ ポイントが X 座標と Y 座標、およびサイズ値を持つバブルで表され、3 次元データを視覚化するのに最適です。Aspose.Words for .NET を使用すると、データの視覚的表現を強化する動的で情報豊富なバブル チャートを作成できます。

Aspose.Words for .NET を使用すると、バブル チャートを含むドキュメントの生成プロセスを自動化し、手動でのドキュメント作成にかかる時間と労力を節約できます。ライブラリにはさまざまなチャートの種類とカスタマイズ オプションが用意されており、Word ドキュメントで視覚的に魅力的でデータが豊富なチャートを作成できます。

### よくある質問

#### Q1. バブルチャートとは何ですか？
バブル チャートは、バブルまたは球を使用して 3 次元データを表示するチャートの一種です。各データ ポイントはバブルで表され、X 座標と Y 座標によってチャート上のバブルの位置が決定され、バブルのサイズによってデータの 3 次元が表されます。バブル チャートは、複数の変数間の関係やパターンを視覚化するのに役立ちます。

#### Q2. バブルチャートに複数のシリーズを追加できますか?
はい、Aspose.Words for .NET を使用してバブル チャートに複数のシリーズを追加できます。各シリーズは、それぞれの X、Y、バブル サイズの値を持つデータ ポイントのセットを表します。複数のシリーズを追加することで、同じチャート内で異なるデータセットを比較および分析し、データの包括的なビューを提供できます。

#### Q3. バブルチャートの外観をカスタマイズできますか?
はい、Aspose.Words for .NET を使用すると、バブル チャートの外観のさまざまな側面をカスタマイズできます。系列の色、バブルのサイズ、軸ラベル、グラフ領域の書式設定などのプロパティを変更できます。ライブラリには、グラフの視覚要素を制御し、ニーズに合わせてカスタマイズされた外観を作成するための豊富な API セットが用意されています。

#### Q4. バブルチャートを挿入したドキュメントを別の形式で保存できますか?
はい、Aspose.Words for .NETでは、バブルチャートを挿入したドキュメントをDOCX、PDF、HTMLなどのさまざまな形式で保存できます。要件に応じて必要な出力形式を選択し、`Save`方法の`Document`オブジェクトをクリックしてドキュメントを保存します。挿入されたバブル チャートは保存されたドキュメント内に保持されます。

#### Q5. バブルチャートを挿入した後で、データや外観を変更できますか?
はい、ドキュメントにバブル チャートを挿入した後、Aspose.Words for .NET が提供する API を使用してデータと外観を変更できます。シリーズ データの更新、バブル サイズの変更、軸プロパティのカスタマイズ、書式設定オプションの適用を行って、Word ドキュメントに動的でインタラクティブなチャートを作成できます。