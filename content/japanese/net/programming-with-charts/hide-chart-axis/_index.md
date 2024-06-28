---
title: Word 文書内のグラフの軸を非表示にする
linktitle: Word 文書内のグラフの軸を非表示にする
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメント内のグラフの軸を非表示にする方法を学習します。軸を非表示にすると、より明確で焦点を絞ったグラフ表示が可能になります。
type: docs
weight: 10
url: /ja/net/programming-with-charts/hide-chart-axis/
---

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメント内のグラフの軸を非表示にする方法について説明します。提供されているソース コードは、グラフの作成方法、系列データの追加方法、グラフ軸の非表示方法を示しています。

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

次に、`InsertChart`の方法`DocumentBuilder`。この例では、縦棒グラフを挿入します。

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## ステップ 3: 系列データをグラフに追加する

系列データをグラフに追加します。この例では、5 つの項目とそれらに対応する値を追加します。

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## ステップ 4: グラフの軸を非表示にする

グラフの軸を非表示にするには、`AxisY`チャートのプロパティを設定し、`Hidden`財産を`true`.

```csharp
chart.AxisY.Hidden = true;
```

この例では、グラフの Y 軸を非表示にします。

## ステップ 5: ドキュメントを保存する

最後に、次のコマンドを使用してドキュメントを指定したディレクトリに保存します。`Save`の方法`Document`物体。

```csharp
doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

これで、Aspose.Words for .NET を使用してグラフの軸を非表示にする実装が完了しました。

### Aspose.Words for .NET を使用したグラフ軸の非表示のソース コード例 

```csharp
	//ドキュメントディレクトリへのパス
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
	chart.AxisY.Hidden = true;
	doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内のグラフの軸を非表示にする方法を学習しました。ステップバイステップのガイドに従い、提供されているソース コードを使用すると、グラフを作成し、系列データを追加し、グラフの軸を非表示にして、目的の視覚効果を実現できます。

 Aspose.Words for .NET は、Word ドキュメント内のグラフを使用した Word Processing 用の包括的な API を提供し、軸プロパティなどのグラフのさまざまな側面を操作できます。にアクセスすることで、`AxisY`グラフのプロパティを使用すると、Y 軸を非表示にしてグラフの視覚化から削除できます。

グラフの軸を非表示にすると、軸の線やラベルに邪魔されずにグラフのデータに集中したい場合に便利です。これにより、チャートがよりクリーンでシンプルな外観になります。

Aspose.Words for .NET を使用すると、グラフ作成機能を .NET アプリケーションに簡単に組み込むことができ、カスタマイズされたグラフや非表示のグラフ軸を備えた本格的なドキュメントを生成できます。

### よくある質問

#### Q1. Aspose.Words for .NET とは何ですか?
Aspose.Words for .NET は、開発者が .NET アプリケーションで Word ドキュメントをプログラム的に作成、操作、保存できるようにする強力なドキュメント処理ライブラリです。グラフやグラフ軸などの文書要素を使用したワードプロセッサの幅広い機能を提供します。

#### Q2. Aspose.Words for .NET をインストールするにはどうすればよいですか?
Aspose.Words for .NET をインストールするには、Visual Studio の NuGet パッケージ マネージャーを使用してダウンロードします。 NuGet パッケージ マネージャーで「Apose.Words」を検索し、プロジェクトにインストールするだけです。

#### Q3.グラフの X 軸と Y 軸の両方を非表示にすることはできますか?
はい、Aspose.Words for .NET を使用すると、グラフの X 軸と Y 軸の両方を非表示にすることができます。 X 軸を非表示にするには、`AxisX`チャートのプロパティを設定し、`Hidden`財産を`true` 。同様に、Y 軸を非表示にするには、`AxisY`プロパティを設定し、`Hidden`財産を`true`。これにより、チャートの視覚化から両方の軸を削除できます。

#### Q4.軸を非表示にした後、再度表示することはできますか?
はい、Aspose.Words for .NET を使用してグラフの軸を非表示にした後、再度表示することができます。非表示の軸を表示するには、単に`Hidden`対応するプロパティ`AxisX`または`AxisY`に反対する`false`。これにより、グラフに軸が再び表示されるようになります。

#### Q5.グラフ軸の他のプロパティをカスタマイズできますか?
はい、Aspose.Words for .NET を使用すると、軸のタイトル、ラベル、線の色など、グラフ軸のさまざまなプロパティをカスタマイズできます。にアクセスすることで、`AxisX`そして`AxisY`チャートのプロパティ。次のようなプロパティを変更できます。`Title`, `MajorTickMark`, `MinorTickMark`, `TickLabelOffset`、他にもたくさんあります。これにより、グラフの軸の外観と動作をきめ細かく制御できるようになります。

#### Q6.非表示の軸を含むグラフを別のファイル形式で保存できますか?
はい、Aspose.Words for .NET を使用すると、非表示の軸を含むグラフを含むドキュメントを DOCX、PDF、HTML などのさまざまなファイル形式で保存できます。要件に基づいて希望の出力形式を選択し、`Save`の方法`Document`ドキュメントを保存するオブジェクト。非表示の軸は保存されたドキュメントに保存されます。