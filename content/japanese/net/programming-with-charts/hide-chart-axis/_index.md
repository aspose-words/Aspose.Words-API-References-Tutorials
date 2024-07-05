---
title: Word 文書でグラフの軸を非表示にする
linktitle: Word 文書でグラフの軸を非表示にする
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してドキュメント内のグラフ軸を非表示にする方法を学びます。軸を非表示にすると、グラフの表示がよりすっきりして焦点が絞られます。
type: docs
weight: 10
url: /ja/net/programming-with-charts/hide-chart-axis/
---

このチュートリアルでは、Aspose.Words for .NET を使用してドキュメント内のグラフ軸を非表示にする方法について説明します。提供されているソース コードでは、グラフを作成し、系列データを追加し、グラフ軸を非表示にする方法が示されています。

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

次に、`InsertChart`方法の`DocumentBuilder`この例では、縦棒グラフを挿入します。

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## ステップ3: グラフに系列データを追加する

グラフに系列データを追加します。この例では、5 つの項目とそれに対応する値を追加します。

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## ステップ4: グラフの軸を非表示にする

グラフ軸を非表示にするには、`AxisY`チャートのプロパティを設定し、`Hidden`財産に`true`.

```csharp
chart.AxisY.Hidden = true;
```

この例では、グラフの Y 軸を非表示にします。

## ステップ5: ドキュメントを保存する

最後に、指定されたディレクトリにドキュメントを保存します。`Save`方法の`Document`物体。

```csharp
doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

これで、Aspose.Words for .NET を使用してチャートの軸を非表示にする実装が完了します。

### Aspose.Words for .NET を使用してチャート軸を非表示にするサンプル ソース コード 

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

このチュートリアルでは、Aspose.Words for .NET を使用して Word 文書内のグラフ軸を非表示にする方法を学習しました。ステップバイステップのガイドに従い、提供されているソース コードを使用することで、グラフを作成し、系列データを追加し、グラフ軸を非表示にして、目的の視覚効果を実現できます。

 Aspose.Words for .NETは、Word文書内のグラフを処理するための包括的なAPIを提供し、軸のプロパティを含むグラフのさまざまな側面を操作できます。`AxisY`グラフのプロパティを使用すると、Y 軸を非表示にしてグラフの視覚化から削除できます。

グラフ軸を非表示にすると、軸線やラベルに邪魔されずにグラフ データに集中したい場合に便利です。これにより、グラフの外観がよりすっきりとシンプルになります。

Aspose.Words for .NET を使用すると、.NET アプリケーションにグラフ作成機能を簡単に組み込み、カスタマイズされたグラフや非表示のグラフ軸を含むプロフェッショナルな外観のドキュメントを生成できます。

### よくある質問

#### Q1. Aspose.Words for .NET とは何ですか?
Aspose.Words for .NET は、開発者が .NET アプリケーションでプログラム的に Word 文書を作成、操作、保存できるようにする強力なドキュメント処理ライブラリです。グラフやグラフ軸などのドキュメント要素を使用して Words を処理するための幅広い機能を提供します。

#### Q2. Aspose.Words for .NET をインストールするにはどうすればよいですか?
Aspose.Words for .NET は、Visual Studio の NuGet パッケージ マネージャーを使用してダウンロードすることでインストールできます。NuGet パッケージ マネージャーで「Aspose.Words」を検索し、プロジェクトにインストールするだけです。

#### Q3. グラフの X 軸と Y 軸の両方を非表示にすることはできますか?
はい、Aspose.Words for .NETを使用すると、グラフのX軸とY軸の両方を非表示にすることができます。X軸を非表示にするには、`AxisX`チャートのプロパティを設定し、`Hidden`財産に`true`同様に、Y軸を非表示にするには、`AxisY`プロパティを設定し、`Hidden`財産に`true`これにより、チャートの視覚化から両方の軸を削除できます。

#### Q4. 軸を非表示にした後、再度表示することはできますか？
はい、Aspose.Words for .NETを使用してグラフの軸を非表示にした後、再度表示することができます。非表示の軸を表示するには、`Hidden`対応する`AxisX`または`AxisY`反対する`false`これにより、グラフに軸が再び表示されるようになります。

#### Q5. グラフ軸の他のプロパティをカスタマイズできますか?
はい、Aspose.Words for .NETでは、軸のタイトル、ラベル、線の色など、グラフ軸のさまざまなプロパティをカスタマイズできます。`AxisX`そして`AxisY`チャートのプロパティでは、次のようなプロパティを変更できます。`Title`, `MajorTickMark`, `MinorTickMark`, `TickLabelOffset`、その他多数。これにより、グラフ軸の外観と動作を細かく制御できます。

#### Q6. 軸を非表示にしたグラフを別のファイル形式で保存できますか?
はい、Aspose.Words for .NETでは、非表示の軸を持つグラフを含むドキュメントをDOCX、PDF、HTMLなどのさまざまなファイル形式で保存できます。要件に基づいて必要な出力形式を選択し、`Save`方法の`Document`オブジェクトを使用してドキュメントを保存します。保存されたドキュメントでは非表示の軸が保持されます。