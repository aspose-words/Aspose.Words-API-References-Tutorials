---
title: Aspose.Words for Java でのグラフの使用
linktitle: チャートの使用
second_title: Aspose.Words Java ドキュメント処理 API
description: Aspose.Words for Java でグラフを作成およびカスタマイズする方法を学びます。データ視覚化のためのグラフの種類、書式設定、軸のプロパティを調べます。
type: docs
weight: 12
url: /ja/java/document-conversion-and-export/using-charts/
---

## Aspose.Words for Java でのグラフの使用の概要

このチュートリアルでは、Aspose.Words for Java を使用してグラフを操作する方法を説明します。さまざまなタイプのグラフの作成方法、軸プロパティのカスタマイズ方法、データ ラベルの書式設定などの方法を学びます。飛び込んでみましょう！

## 折れ線グラフの作成

折れ線グラフを作成するには、次のコードを使用します。

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.insertChart(ChartType.LINE, 432.0, 252.0);
Chart chart = shape.getChart();
chart.getTitle().setText("Data Labels With Different Number Format");

//デフォルトで生成されたシリーズを削除します。
chart.getSeries().clear();

//データとデータ ラベルを含むシリーズを追加します。
ChartSeries series1 = chart.getSeries().add("Aspose Series 1", 
    new String[] { "Category 1", "Category 2", "Category 3" }, 
    new double[] { 2.5, 1.5, 3.5 });

series1.hasDataLabels(true);
series1.getDataLabels().setShowValue(true);
series1.getDataLabels().get(0).getNumberFormat().setFormatCode("\"$\"#,##0.00");
series1.getDataLabels().get(1).getNumberFormat().setFormatCode("dd/mm/yyyy");
series1.getDataLabels().get(2).getNumberFormat().setFormatCode("0.00%");

//または、フォーマット コードをソース セルにリンクします。
series1.getDataLabels().get(2).getNumberFormat().isLinkedToSource(true);

doc.save("Your Directory Path" + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

## 他の種類のグラフの作成

同様の手法を使用して、縦棒グラフ、面グラフ、バブルグラフ、散布図などのさまざまなタイプのグラフを作成できます。単純な縦棒グラフを挿入する例を次に示します。

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.insertChart(ChartType.COLUMN, 432.0, 252.0);
Chart chart = shape.getChart();

//デフォルトで生成されたシリーズを削除します。
chart.getSeries().clear();

//カテゴリを作成し、データを追加します。
String[] categories = new String[] { "Category 1", "Category 2" };
chart.getSeries().add("Aspose Series 1", categories, new double[] { 1.0, 2.0 });
chart.getSeries().add("Aspose Series 2", categories, new double[] { 3.0, 4.0 });

doc.save("Your Directory Path" + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

## 軸のプロパティのカスタマイズ

軸のタイプの変更、目盛の設定、ラベルの書式設定など、軸のプロパティをカスタマイズできます。 XY 軸のプロパティを定義する例を次に示します。

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.insertChart(ChartType.AREA, 432.0, 252.0);
Chart chart = shape.getChart();

//デフォルトのシリーズをクリアし、データを追加します。

ChartAxis xAxis = chart.getAxisX();
ChartAxis yAxis = chart.getAxisY();

// X 軸を日付ではなくカテゴリに変更します。
xAxis.setCategoryType(AxisCategoryType.CATEGORY);
xAxis.setCrosses(AxisCrosses.CUSTOM);
xAxis.setCrossesAt(3.0); // 軸の表示単位 (百) で測定されます。
xAxis.setReverseOrder(true);
xAxis.setMajorTickMark(AxisTickMark.CROSS);
xAxis.setMinorTickMark(AxisTickMark.OUTSIDE);
xAxis.setTickLabelOffset(200);

yAxis.setTickLabelPosition(AxisTickLabelPosition.HIGH);
yAxis.setMajorUnit(100.0);
yAxis.setMinorUnit(50.0);
yAxis.getDisplayUnit().setUnit(AxisBuiltInUnit.HUNDREDS);
yAxis.getScaling().setMinimum(new AxisBound(100.0));
yAxis.getScaling().setMaximum(new AxisBound(700.0));

doc.save("Your Directory Path" + "WorkingWithCharts.DefineXYAxisProperties.docx");
```

## データラベルの書式設定

データ ラベルをさまざまな数値形式で書式設定できます。以下に例を示します。

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.insertChart(ChartType.COLUMN, 432.0, 252.0);
Chart chart = shape.getChart();

//デフォルトのシリーズをクリアし、データを追加します。

chart.getAxisY().getNumberFormat().setFormatCode("#,##0");

doc.save("Your Directory Path" + "WorkingWithCharts.NumberFormatForAxis.docx");
```

## 追加のグラフのカスタマイズ

範囲、ラベル間の間隔単位、グラフ軸の非表示などを調整して、グラフをさらにカスタマイズできます。これらのオプションの詳細については、提供されているコード スニペットを参照してください。

## 結論

このチュートリアルでは、Aspose.Words for Java を使用してグラフを操作する方法を検討しました。さまざまな種類のグラフの作成、軸プロパティのカスタマイズ、データ ラベルの書式設定などの方法を学習しました。 Aspose.Words for Java は、データの視覚的表現をドキュメントに追加し、情報の表示方法を強化するための強力なツールを提供します。

## よくある質問

### 複数の系列をグラフに追加するにはどうすればよいですか?

を使用して複数の系列をチャートに追加できます。`chart.getSeries().add()`方法。シリーズ名、カテゴリ、データ値を必ず指定してください。

### カスタム数値形式でデータ ラベルを書式設定するにはどうすればよいですか?

データラベルをフォーマットするには、`DataLabels`シリーズのプロパティと目的の形式コードの設定`getNumberFormat().setFormatCode()`.

### グラフの軸のプロパティをカスタマイズするにはどうすればよいですか?

タイプ、目盛り、ラベルなどの軸のプロパティをカスタマイズするには、`ChartAxis`のようなプロパティ`setCategoryType()`, `setCrosses()` 、 そして`setMajorTickMark()`.

### 散布図や面グラフなどの他のタイプのグラフを作成するにはどうすればよいですか?

適切なグラフを指定することで、さまざまな種類のグラフを作成できます。`ChartType`を使用してチャートを挿入するとき`builder.insertChart(ChartType.TYPE, width, height)`.

### グラフの軸を非表示にするにはどうすればよいですか?

を設定することでグラフの軸を非表示にできます。`setHidden(true)`軸のプロパティ。