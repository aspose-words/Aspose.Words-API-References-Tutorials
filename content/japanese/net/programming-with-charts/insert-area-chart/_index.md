---
title: Word 文書に面グラフを挿入する
linktitle: Word 文書に面グラフを挿入する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して、面グラフをドキュメントに挿入する方法を学びます。系列データを追加し、グラフを含むドキュメントを保存します。
type: docs
weight: 10
url: /ja/net/programming-with-charts/insert-area-chart/
---

このチュートリアルでは、Aspose.Words for .NET を使用して面グラフをドキュメントに挿入する方法について説明します。提供されているソース コードでは、グラフを作成し、系列データを追加し、ドキュメントを保存する方法が示されています。

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

次に、`InsertChart`方法の`DocumentBuilder`ドキュメントに面グラフを挿入します。

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## ステップ3: グラフに系列データを追加する

グラフに系列データを追加します。この例では、対応する日付と値を持つ 5 つのデータ ポイントを追加します。

```csharp
chart.Series.Add("Aspose Series 1", new []
{
    new DateTime(2002, 05, 01),
    new DateTime(2002, 06, 01),
    new DateTime(2002, 07, 01),
    new DateTime(2002, 08, 01),
    new DateTime(2002, 09, 01)
}, 
new double[] { 32, 32, 28, 12, 15 });
```

## ステップ4: ドキュメントを保存する

最後に、指定されたディレクトリにドキュメントを保存します。`Save`方法の`Document`物体。

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

これで、Aspose.Words for .NET を使用して面グラフを挿入する実装が完了しました。

### Aspose.Words for .NET を使用して面グラフを挿入するためのサンプル ソース コード 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Add("Aspose Series 1", new []
		{
			new DateTime(2002, 05, 01),
			new DateTime(2002, 06, 01),
			new DateTime(2002, 07, 01),
			new DateTime(2002, 08, 01),
			new DateTime(2002, 09, 01)
		}, 
		new double[] { 32, 32, 28, 12, 15 });
	doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

### 結論

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書に面グラフを挿入する方法を学習しました。ステップ バイ ステップ ガイドに従い、提供されているソース コードを使用することで、新しい文書を作成し、面グラフを挿入し、系列データを追加し、グラフを含む文書を保存できます。

Aspose.Words for .NET は、Word 文書のグラフを使用した Words Processing 用の強力な API を提供します。わずか数行のコードで、プロフェッショナルな外観の面グラフを作成し、要件に応じてカスタマイズできます。面グラフは、時間やカテゴリごとのデータの大きさや傾向を表示する場合によく使用されます。

Aspose.Words for .NET を使用すると、面グラフを含むドキュメントの生成プロセスを自動化し、手動でのドキュメント作成にかかる時間と労力を節約できます。ライブラリにはさまざまなグラフの種類とカスタマイズ オプションが用意されており、Word ドキュメントで視覚的に魅力的で情報豊富なグラフを作成できます。

### よくある質問

#### Q1. Aspose.Words for .NET とは何ですか?
Aspose.Words for .NET は、開発者が .NET アプリケーションでプログラム的に Word ドキュメントを作成、変更、変換できるようにする強力なドキュメント処理ライブラリです。チャート、段落、表などのドキュメント要素を使用した Words 処理用の包括的な API セットを提供します。

#### Q2. Aspose.Words for .NET をインストールするにはどうすればよいですか?
Aspose.Words for .NET をインストールするには、Visual Studio の NuGet パッケージ マネージャーを使用して、ライブラリをプロジェクトに直接インストールします。NuGet パッケージ マネージャーで「Aspose.Words」を検索し、パッケージをインストールするだけです。

#### Q3. 面グラフの外観をカスタマイズできますか?
はい、Aspose.Words for .NET を使用すると、面グラフの外観のさまざまな側面をカスタマイズできます。グラフのタイトル、シリーズの色、軸ラベル、グラフ領域の書式設定などのプロパティを変更できます。ライブラリには、グラフの視覚要素を制御し、ニーズに合わせてカスタマイズされた外観を作成するための豊富な API セットが用意されています。

#### Q4. 面グラフに複数のシリーズを追加できますか?
はい、Aspose.Words for .NET を使用して、面グラフに複数のシリーズを追加できます。各シリーズは、グラフにプロットされるデータ ポイントのセットを表します。異なるデータ セットを持つシリーズを追加し、名前、データ ポイント、外観など、各シリーズを個別にカスタマイズできます。

#### Q5. 面グラフを挿入したドキュメントを別の形式で保存できますか?
はい、Aspose.Words for .NETでは、面グラフを挿入したドキュメントをDOCX、PDF、HTMLなどのさまざまな形式で保存できます。要件に応じて必要な出力形式を選択し、`Save`方法の`Document`オブジェクトをクリックしてドキュメントを保存します。挿入された面グラフは保存されたドキュメントに保存されます。

#### Q6. 面グラフを挿入した後で、データや外観を変更できますか?
はい、面グラフをドキュメントに挿入した後、Aspose.Words for .NET が提供する API を使用してデータと外観を変更できます。系列データを更新したり、グラフの種類を変更したり、軸のプロパティをカスタマイズしたり、書式設定オプションを適用したりして、Word ドキュメントに動的でインタラクティブなグラフを作成できます。