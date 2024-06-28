---
title: グラフの軸の数値形式
linktitle: グラフの軸の数値形式
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してグラフの軸の数値形式を設定する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-charts/number-format-for-axis/
---

このチュートリアルでは、Aspose.Words for .NET を使用してグラフの軸の数値形式を設定する方法について説明します。提供されているソース コードは、グラフの作成方法、系列データの追加方法、および軸ラベルの書式設定方法を示しています。

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

次に、`InsertChart`の方法`DocumentBuilder`縦棒グラフをドキュメントに挿入します。

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
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
```

## ステップ 4: 軸ラベルの書式設定

 軸ラベルの数値形式を設定するには、`AxisY`チャートのプロパティを設定し、`NumberFormat.FormatCode`プロパティを目的の形式に変更します。この例では、形式を「#,##0」に設定して、桁区切りで数値を表示します。

```csharp
chart.AxisY.NumberFormat.FormatCode = "#,##0";
```

## ステップ 5: ドキュメントを保存する

最後に、次のコマンドを使用してドキュメントを指定したディレクトリに保存します。`Save`の方法`Document`物体。

```csharp
doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

これで、Aspose.Words for .NET を使用して軸の数値形式を設定する実装が完了しました。

### Aspose.Words for .NET を使用した軸の数値形式のソース コード例 

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
		new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
	chart.AxisY.NumberFormat.FormatCode = "#,##0";
	doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

## 結論

このチュートリアルでは、Aspose.Words for .NET を使用してグラフの軸の数値形式を設定する方法を学習しました。ステップバイステップのガイドに従い、提供されているソース コードを利用することで、新しいドキュメントの作成、縦棒グラフの挿入、系列データの追加、特定の形式で数値を表示するための軸ラベルの書式設定を行うことができます。

Aspose.Words for .NET は、Word ドキュメント内のグラフの外観をカスタマイズするための強力な機能を提供します。軸ラベルの数値形式を設定すると、小数点以下の桁数、千の位の区切り文字、通貨記号などのオプションを含めて、数値の表示方法を制御できます。これにより、数値データを明確かつ意味のある方法で表示できます。

Aspose.Words for .NET を使用すると、軸ラベルなど、グラフのさまざまな側面を柔軟にフォーマットできます。軸の数値形式を設定すると、一貫性が確保され、グラフの読みやすさが向上し、ユーザーが表現された値を解釈しやすくなります。

### よくある質問

#### Q1.グラフの軸の数値形式は何ですか?
グラフの軸の数値書式とは、軸に表示される数値に適用される書式を指します。小数点以下の桁数、桁区切り記号、通貨記号、パーセント記号などのオプションを含め、数値の表示方法を制御できます。数値形式を設定すると、特定の要件に合わせてグラフ内の数値データの外観をカスタマイズできます。

#### Q2.軸ラベルの数値形式を設定するにはどうすればよいですか?
 Aspose.Words for .NET を使用してグラフの軸ラベルの数値形式を設定するには、`AxisY`チャートのプロパティを設定し、`NumberFormat.FormatCode`プロパティを目的の形式コードに設定します。書式コードは、標準の数値書式設定パターンの構文に従い、数値の表示方法を決定します。たとえば、「#,##0.00」を使用すると、小数点以下 2 桁と千の位の区切り記号を使用して数値を表示できます。

#### Q3. X 軸と Y 軸のラベルに異なる数値形式を設定できますか?
はい、Aspose.Words for .NET を使用して、X 軸と Y 軸のラベルに異なる数値形式を設定できます。それぞれの軸にアクセスします (`AxisX` X軸の場合または`AxisY` 軸の場合)、チャートの`NumberFormat.FormatCode`軸ごとに個別にプロパティを設定します。これにより、特定の要件に基づいて、各軸のラベルに異なる数値形式を適用できます。

#### Q4.使用できる一般的な数値形式コードにはどのようなものがありますか?
Aspose.Words for .NET は、グラフの軸ラベルの書式設定に使用できる幅広い数値書式コードをサポートしています。一般的な形式コードには次のようなものがあります。

- `0`または`#` - 小数点以下を除いた数値を表示します。
- `0.00`または`#.00` - 数値を小数点以下 2 桁で表示します。
- `#,##0` 数値を千単位の区切り記号で表示します。
- `"€"0.00` - 数値をユーロ通貨記号と小数点以下 2 桁で表示します。
- `"%"0` - 数値をパーセンテージで表示します。

番号に関する詳細情報を見つけることができます[フォーマットコード](https://reference.aspose.com/words/net/aspose.words.drawing.charts/chartnumberformat/formatcode/)Aspose.Words for .NET の API リファレンス。

#### Q5.軸ラベルの他のプロパティをカスタマイズできますか?
はい。Aspose.Words for .NET は、軸ラベルの外観と動作をカスタマイズするための幅広いプロパティを提供します。数値の形式に加えて、フォント、サイズ、色、方向、配置などのプロパティを変更できます。これにより、希望のスタイルやプレゼンテーション要件に合わせて軸ラベルを完全にカスタマイズできます。