---
title: Word 文書に面グラフを挿入する
linktitle: Word 文書に面グラフを挿入する
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用して面グラフをドキュメントに挿入する方法を学習します。シリーズ データを追加し、グラフとともにドキュメントを保存します。
type: docs
weight: 10
url: /ja/net/programming-with-charts/insert-area-chart/
---

このチュートリアルでは、Aspose.Words for .NET を使用して面グラフをドキュメントに挿入する方法について説明します。提供されているソース コードは、グラフの作成方法、系列データの追加方法、およびドキュメントの保存方法を示しています。

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

次に、`InsertChart`の方法`DocumentBuilder`面グラフをドキュメントに挿入します。

```csharp
Shape shape = builder.InsertChart(ChartType.Area, 432, 252);
Chart chart = shape.Chart;
```

## ステップ 3: 系列データをグラフに追加する

系列データをグラフに追加します。この例では、対応する日付と値を持つ 5 つのデータ ポイントを追加します。

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

## ステップ 4: ドキュメントを保存する

最後に、次のコマンドを使用してドキュメントを指定したディレクトリに保存します。`Save`の方法`Document`物体。

```csharp
doc.Save(dataDir + "WorkingWithCharts.InsertAreaChart.docx");
```

これで、Aspose.Words for .NET を使用した面グラフの挿入の実装が完了しました。

### Aspose.Words for .NET を使用した面グラフの挿入のソース コード例 

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

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書に面グラフを挿入する方法を学習しました。ステップバイステップのガイドに従い、提供されているソース コードを使用すると、新しいドキュメントの作成、面グラフの挿入、系列データの追加、グラフ付きのドキュメントの保存を行うことができます。

Aspose.Words for .NET は、Word ドキュメント内のグラフを使用したワード処理用の強力な API を提供します。わずか数行のコードで、本格的な面グラフを作成し、要件に応じてカスタマイズできます。面グラフは、時間またはカテゴリに沿ったデータの大きさと傾向を表示するために一般的に使用されます。

Aspose.Words for .NET を使用すると、面グラフを含むドキュメントを生成するプロセスを自動化し、手動でドキュメントを作成する時間と労力を節約できます。このライブラリには、幅広いグラフの種類とカスタマイズ オプションが用意されており、Word 文書内に視覚的に魅力的で有益なグラフを作成できます。

### よくある質問

#### Q1. Aspose.Words for .NET とは何ですか?
Aspose.Words for .NET は、開発者が .NET アプリケーションで Word ドキュメントをプログラム的に作成、変更、変換できるようにする強力なドキュメント処理ライブラリです。これは、グラフ、段落、表などの文書要素を含む文書処理用の包括的な API セットを提供します。

#### Q2. Aspose.Words for .NET をインストールするにはどうすればよいですか?
Aspose.Words for .NET をインストールするには、Visual Studio の NuGet パッケージ マネージャーを使用してライブラリをプロジェクトに直接インストールできます。 NuGet パッケージ マネージャーで「Aspose.Words」を検索し、パッケージをインストールするだけです。

#### Q3.面グラフの外観をカスタマイズできますか?
はい、Aspose.Words for .NET を使用すると、面グラフの外観のさまざまな側面をカスタマイズできます。グラフのタイトル、系列の色、軸ラベル、グラフ領域の書式設定などのプロパティを変更できます。このライブラリは、グラフの視覚要素を制御し、ニーズに合ったカスタマイズされた外観を作成するための豊富な API セットを提供します。

#### Q4.複数のシリーズを面グラフに追加できますか?
はい、Aspose.Words for .NET を使用して複数の系列を面グラフに追加できます。各系列は、グラフ上にプロットされる一連のデータ ポイントを表します。さまざまなデータセットを持つシリーズを追加し、名前、データポイント、外観など各シリーズを個別にカスタマイズできます。

#### Q5.面グラフを挿入したドキュメントを別の形式で保存できますか?
はい、Aspose.Words for .NET を使用すると、面グラフが挿入されたドキュメントを DOCX、PDF、HTML などのさまざまな形式で保存できます。要件に基づいて希望の出力形式を選択し、`Save`の方法`Document`ドキュメントを保存するオブジェクト。挿入された面グラフは、保存されたドキュメントに保存されます。

#### Q6.面グラフを挿入した後に、面グラフのデータと外観を変更できますか?
はい、面グラフをドキュメントに挿入した後、Aspose.Words for .NET が提供する API を使用してそのデータと外観を変更できます。系列データを更新し、グラフの種類を変更し、軸のプロパティをカスタマイズし、書式設定オプションを適用して、Word 文書内に動的で対話型のグラフを作成できます。