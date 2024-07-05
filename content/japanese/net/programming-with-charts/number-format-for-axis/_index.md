---
title: グラフの軸の数値形式
linktitle: グラフの軸の数値形式
second_title: Aspose.Words ドキュメント処理 API
description: Aspose.Words for .NET を使用してグラフの軸の数値形式を設定する方法を学習します。
type: docs
weight: 10
url: /ja/net/programming-with-charts/number-format-for-axis/
---

このチュートリアルでは、Aspose.Words for .NET を使用してグラフの軸の数値形式を設定する方法について説明します。提供されているソース コードは、グラフを作成し、系列データを追加し、軸ラベルをフォーマットする方法を示しています。

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

次に、`InsertChart`方法の`DocumentBuilder`ドキュメントに縦棒グラフを挿入します。

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## ステップ3: グラフに系列データを追加する

グラフに系列データを追加します。この例では、対応する値を持つ 5 つの項目を追加します。

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1900000, 850000, 2100000, 600000, 1500000 });
```

## ステップ4: 軸ラベルの書式を設定する

Y軸ラベルの数値形式を設定するには、`AxisY`チャートのプロパティを設定し、`NumberFormat.FormatCode`プロパティを目的の形式に設定します。この例では、桁区切りの数字を表示するために、形式を「#,##0」に設定します。

```csharp
chart.AxisY.NumberFormat.FormatCode = "#,##0";
```

## ステップ5: ドキュメントを保存する

最後に、指定されたディレクトリにドキュメントを保存します。`Save`方法の`Document`物体。

```csharp
doc.Save(dataDir + "WorkingWithCharts.NumberFormatForAxis.docx");
```

これで、Aspose.Words for .NET を使用して軸の数値形式を設定する実装が完了します。

### Aspose.Words for .NET を使用した軸の数値書式のサンプル ソース コード 

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

このチュートリアルでは、Aspose.Words for .NET を使用してグラフの軸の数値形式を設定する方法を学習しました。ステップバイステップのガイドに従い、提供されているソース コードを利用することで、新しいドキュメントを作成し、縦棒グラフを挿入し、系列データを追加し、軸ラベルを書式設定して特定の形式で数値を表示することができます。

Aspose.Words for .NET は、Word 文書内のグラフの外観をカスタマイズするための強力な機能を提供します。軸ラベルの数値形式を設定することで、小数点、千単位の区切り、通貨記号などのオプションを含む数値の表示方法を制御できます。これにより、数値データを明確かつ意味のある方法で表示できます。

Aspose.Words for .NET を使用すると、軸ラベルを含むグラフのさまざまな側面を柔軟にフォーマットできます。軸の数値書式を設定することで、一貫性が確保され、グラフの読みやすさが向上し、ユーザーが表される値を解釈しやすくなります。

### よくある質問

#### Q1. グラフの軸の数値形式は何ですか?
グラフの軸の数値書式とは、軸に表示される数値に適用される書式設定を指します。数値書式を使用すると、小数点、千単位の区切り、通貨記号、パーセント記号などのオプションを含め、数値の表示方法を制御できます。数値書式を設定すると、グラフ内の数値データの外観を特定の要件に合わせてカスタマイズできます。

#### Q2. 軸ラベルの数値形式を設定するにはどうすればよいですか?
 Aspose.Words for .NETを使用してグラフの軸ラベルの数値書式を設定するには、`AxisY`チャートのプロパティを設定し、`NumberFormat.FormatCode`プロパティを目的の書式コードに変更します。書式コードは、標準の数値書式パターンの構文に従い、数値の表示方法を決定します。たとえば、「#,##0.00」を使用すると、小数点以下 2 桁と 3 桁ごとの区切り記号で数値を表示できます。

#### Q3. X 軸と Y 軸のラベルに異なる数値形式を設定できますか?
はい、Aspose.Words for .NETを使用して、X軸とY軸のラベルに異なる数値形式を設定できます。それぞれの軸にアクセスします（`AxisX` X軸または`AxisY`グラフのY軸の`NumberFormat.FormatCode`プロパティを各軸ごとに個別に設定できます。これにより、特定の要件に基づいて、各軸のラベルに異なる数値形式を適用できます。

#### Q4. 使用できる一般的な数値形式コードにはどのようなものがありますか?
Aspose.Words for .NET は、グラフの軸ラベルの書式設定に使用できるさまざまな数値書式コードをサポートしています。一般的な書式コードには次のようなものがあります。

- `0`または`#` - 小数点なしで数値を表示します。
- `0.00`または`#.00` - 小数点以下2桁の数値を表示します。
- `#,##0` 3桁ごとの区切りで数値を表示します。
- `"€"0.00` - ユーロ通貨記号と小数点 2 桁で数値を表示します。
- `"%"0` - 数値をパーセンテージで表示します。

番号に関する詳細情報は[フォーマットコード](https://reference.aspose.com/words/net/aspose.words.drawing.charts/chartnumberformat/formatcode/)Aspose.Words for .NET の API リファレンス。

#### Q5. 軸ラベルの他のプロパティをカスタマイズできますか?
はい、Aspose.Words for .NET には、軸ラベルの外観と動作をカスタマイズするためのさまざまなプロパティが用意されています。数値の形式に加えて、フォント、サイズ、色、方向、配置などのプロパティを変更できます。これにより、希望するスタイルとプレゼンテーションの要件に合わせて軸ラベルを完全にカスタマイズできます。