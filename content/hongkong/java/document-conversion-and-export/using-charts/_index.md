---
title: 在 Aspose.Words for Java 中使用圖表
linktitle: 使用圖表
second_title: Aspose.Words Java 文件處理 API
description: 了解如何在 Aspose.Words for Java 中建立和自訂圖表。探索資料視覺化的圖表類型、格式和軸屬性。
type: docs
weight: 12
url: /zh-hant/java/document-conversion-and-export/using-charts/
---

## 在 Aspose.Words for Java 中使用圖表簡介

在本教程中，我們將探索如何使用 Aspose.Words for Java 處理圖表。您將學習如何建立各種類型的圖表、自訂軸屬性、設定資料標籤格式等。讓我們深入了解吧！

## 建立折線圖

若要建立折線圖，請使用以下程式碼：

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.insertChart(ChartType.LINE, 432.0, 252.0);
Chart chart = shape.getChart();
chart.getTitle().setText("Data Labels With Different Number Format");

//刪除預設產生的系列。
chart.getSeries().clear();

//新增帶有資料和資料標籤的系列。
ChartSeries series1 = chart.getSeries().add("Aspose Series 1", 
    new String[] { "Category 1", "Category 2", "Category 3" }, 
    new double[] { 2.5, 1.5, 3.5 });

series1.hasDataLabels(true);
series1.getDataLabels().setShowValue(true);
series1.getDataLabels().get(0).getNumberFormat().setFormatCode("\"$\"#,##0.00");
series1.getDataLabels().get(1).getNumberFormat().setFormatCode("dd/mm/yyyy");
series1.getDataLabels().get(2).getNumberFormat().setFormatCode("0.00%");

//或將格式代碼連結到來源單元格。
series1.getDataLabels().get(2).getNumberFormat().isLinkedToSource(true);

doc.save("Your Directory Path" + "WorkingWithCharts.FormatNumberOfDataLabel.docx");
```

## 建立其他類型的圖表

您可以使用類似的技術建立不同類型的圖表，例如長條圖、面積圖、氣泡圖、散點圖等。下面是插入簡單長條圖的範例：

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.insertChart(ChartType.COLUMN, 432.0, 252.0);
Chart chart = shape.getChart();

//刪除預設產生的系列。
chart.getSeries().clear();

//建立類別並新增資料。
String[] categories = new String[] { "Category 1", "Category 2" };
chart.getSeries().add("Aspose Series 1", categories, new double[] { 1.0, 2.0 });
chart.getSeries().add("Aspose Series 2", categories, new double[] { 3.0, 4.0 });

doc.save("Your Directory Path" + "WorkingWithCharts.InsertSimpleColumnChart.docx");
```

## 自訂軸屬性

您可以自訂軸屬性，例如變更軸類型、設定刻度線、格式化標籤等。以下是定義 XY 軸屬性的範例：

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.insertChart(ChartType.AREA, 432.0, 252.0);
Chart chart = shape.getChart();

//清除預設系列並新增您的資料。

ChartAxis xAxis = chart.getAxisX();
ChartAxis yAxis = chart.getAxisY();

//將 X 軸更改為類別而不是日期。
xAxis.setCategoryType(AxisCategoryType.CATEGORY);
xAxis.setCrosses(AxisCrosses.CUSTOM);
xAxis.setCrossesAt(3.0); //以 Y 軸的顯示單位（百）測量。
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

## 設定資料標籤格式

您可以使用不同的數字格式來設定資料標籤的格式。這是一個例子：

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Shape shape = builder.insertChart(ChartType.COLUMN, 432.0, 252.0);
Chart chart = shape.getChart();

//清除預設系列並新增您的資料。

chart.getAxisY().getNumberFormat().setFormatCode("#,##0");

doc.save("Your Directory Path" + "WorkingWithCharts.NumberFormatForAxis.docx");
```

## 附加圖表定制

您可以透過調整邊界、標籤之間的間隔單位、隱藏圖表軸等來進一步自訂圖表。瀏覽提供的程式碼片段以了解有關這些選項的更多資訊。

## 結論

在本教程中，我們探索如何使用 Aspose.Words for Java 來處理圖表。您已經學習如何建立各種類型的圖表、自訂軸屬性、設定資料標籤格式等。 Aspose.Words for Java 提供了強大的工具，用於將資料的視覺化表示添加到文件中，從而增強您呈現資訊的方式。

## 常見問題解答

### 如何為圖表新增多個系列？

您可以使用以下命令將多個系列新增到圖表中`chart.getSeries().add()`方法。確保指定係列名稱、類別和資料值。

### 如何使用自訂數字格式設定資料標籤的格式？

您可以透過存取來格式化資料標籤`DataLabels`系列的屬性並使用設定所需的格式代碼`getNumberFormat().setFormatCode()`.

### 如何自訂圖表中的軸屬性？

您可以透過存取來自訂軸屬性，例如類型、刻度線、標籤等`ChartAxis`屬性如`setCategoryType()`, `setCrosses()`， 和`setMajorTickMark()`.

### 如何建立其他類型的圖表，例如散點圖或面積圖？

您可以透過指定適當的選項來建立各種圖表類型`ChartType`插入圖表時使用`builder.insertChart(ChartType.TYPE, width, height)`.

### 如何隱藏圖表軸？

您可以透過設定隱藏圖表軸`setHidden(true)`軸的屬性。