---
title: 在 Aspose.Words for Java 中格式化表格和表格樣式
linktitle: 設定表格格式和表格樣式
second_title: Aspose.Words Java 文件處理 API
description: 了解如何在 Aspose.Words for Java 中設定表格格式並套用表格樣式。探索具有原始程式碼的逐步指南，以實現有效的表格格式設定。使用 Aspose.Words 增強您的文件佈局。
type: docs
weight: 17
url: /zh-hant/java/document-conversion-and-export/formatting-tables-and-table-styles/
---

## Aspose.Words for Java 中的表格格式和表格樣式簡介

表格在建立和組織文件中的資訊方面發揮著至關重要的作用。 Aspose.Words for Java 提供了強大的表格格式化和應用表格樣式的功能，以增強文件的視覺吸引力。在本逐步指南中，我們將探討使用 Aspose.Words for Java 設定表格格式和套用表格樣式的各個面向。

## 先決條件

在我們深入了解細節之前，請確保您已將 Aspose.Words for Java 庫整合到您的專案中。您可以從 Aspose 網站下載：[下載 Java 版 Aspose.Words](https://releases.aspose.com/words/java/).

## 取得表格和周圍文字之間的距離

首先，我們來探討如何檢索表格與文件中周圍文字之間的距離。

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
System.out.println("Distance Top: " + table.getDistanceTop());
System.out.println("Distance Bottom: " + table.getDistanceBottom());
System.out.println("Distance Right: " + table.getDistanceRight());
System.out.println("Distance Left: " + table.getDistanceLeft());
```

## 將輪廓邊框套用至表格

您可以將表格與頁面中心對齊，清除現有邊框，並使用以下程式碼設定自訂輪廓邊框：

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setAlignment(TableAlignment.CENTER);
table.clearBorders();
table.setBorder(BorderType.LEFT, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setBorder(BorderType.RIGHT, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setBorder(BorderType.TOP, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setBorder(BorderType.BOTTOM, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setShading(TextureIndex.TEXTURE_SOLID, Color.lightGray, new Color(0, true));
```

## 建立一個有邊框的表格

此程式碼片段示範如何建立表格並為表格及其儲存格設定邊框：

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.clearBorders();
table.setBorders(LineStyle.SINGLE, 1.5, Color.GREEN);
```

## 修改行格式

了解如何修改表格中特定行的格式：

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Row firstRow = table.getFirstRow();
firstRow.getRowFormat().getBorders().setLineStyle(LineStyle.NONE);
firstRow.getRowFormat().setHeightRule(HeightRule.AUTO);
firstRow.getRowFormat().setAllowBreakAcrossPages(true);
```

## 應用程式格式

此範例示範如何將格式套用至表格中的整行：

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
builder.insertCell();
RowFormat rowFormat = builder.getRowFormat();
rowFormat.setHeight(100.0);
rowFormat.setHeightRule(HeightRule.EXACTLY);
table.setLeftPadding(30.0);
table.setRightPadding(30.0);
table.setTopPadding(30.0);
table.setBottomPadding(30.0);
builder.writeln("I'm a wonderfully formatted row.");
```

## 設定單元格內邊距

了解如何為表格中的各個儲存格設定填充：

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.startTable();
builder.insertCell();
builder.getCellFormat().setPaddings(30.0, 50.0, 30.0, 50.0);
builder.writeln("I'm a wonderfully formatted cell.");
```

## 修改單元格格式

了解如何修改表格中特定儲存格的格式：

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
firstCell.getCellFormat().setWidth(30.0);
firstCell.getCellFormat().setOrientation(TextOrientation.DOWNWARD);
firstCell.getCellFormat().getShading().setForegroundPatternColor(Color.GREEN);
```

## 設定具有不同邊框的表格和儲存格格式

了解如何為表格中的個別儲存格設定不同的邊框：

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
//設定表格邊框
table.setBorders(LineStyle.SINGLE, 2.0, Color.BLACK);
//設定單一儲存格的儲存格陰影
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.RED);
//在儲存格中新增內容
builder.writeln("Cell #1");
builder.insertCell();
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.GREEN);
builder.writeln("Cell #2");
//清除下一行的儲存格格式
builder.getCellFormat().clearFormatting();
//為該行的第一個儲存格建立更大的邊框
builder.getCellFormat().getBorders().getLeft().setLineWidth(4.0);
builder.getCellFormat().getBorders().getRight().setLineWidth(4.0);
builder.getCellFormat().getBorders().getTop().setLineWidth(4.0);
builder.getCellFormat().getBorders().getBottom().setLineWidth(4.0);
builder.writeln("Cell #3");
builder.insertCell();
builder.getCellFormat().clearFormatting();
builder.writeln("Cell #4");
```

## 設定表格標題和描述

在表格中新增標題和說明：

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setTitle("Test title");
table.setDescription("Test description");
```

## 第 10 步：留出單元格間距

允許儲存格間距並為表格設定其值：

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setAllowCellSpacing(true);
table.setCellSpacing(2.0);
```

## 第11步：建立一個有風格的表格

建立具有預先定義樣式的表格：

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
table.setStyleIdentifier(StyleIdentifier.MEDIUM_SHADING_1_ACCENT_1);
table.setStyleOptions(TableStyleOptions.FIRST_COLUMN | TableStyleOptions.ROW_BANDS | TableStyleOptions.FIRST_ROW);
builder.writeln("Item");
builder.getCellFormat().setRightPadding(40.0);
builder.insertCell();
builder.writeln("Quantity (kg)");
```

## 步驟12：從樣式展開儲存格和行的格式設置

了解如何擴展表格樣式以將格式套用至儲存格和行：

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
Color cellShadingBefore = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
doc.expandTableStylesToDirectFormatting();
Color cellShadingAfter = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
```

## 第13步：建立表格樣式

建立具有特定格式的自訂表格樣式：

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
table.setStyleIdentifier(StyleIdentifier.MEDIUM_SHADING_1_ACCENT_1);
table.setStyleOptions(TableStyleOptions.FIRST_COLUMN | TableStyleOptions.ROW_BANDS | TableStyleOptions.FIRST_ROW);
builder.writeln("Item");
builder.getCellFormat().setRightPadding(40.0);
builder.insertCell();
builder.writeln("Quantity (kg)");
```

## 第 14 步：定義條件格式

將條件格式套用至表中的行：

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
TableStyle tableStyle = (TableStyle) doc.getStyles().add(StyleType.TABLE, "MyTableStyle1");
tableStyle.getConditionalStyles().getFirstRow().getShading().setBackgroundPatternColor(Color.yellow);
table.setStyle(tableStyle);
```

## 第15步：設定TableCell格式

為單一儲存格設定特定格式：

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.startTable();
builder.insertCell();
CellFormat cellFormat = builder.getCellFormat();
cellFormat.setWidth(250.0);
cellFormat.setLeftPadding(30.0);
cellFormat.setRightPadding(30.0);
cellFormat.setTopPadding(30.0);
cellFormat.setBottomPadding(30.0);
builder.writeln("I'm a wonderfully formatted cell.");
```

## 第16步：設定TableRow格式

將格式套用至表中的整行：

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
RowFormat rowFormat = builder.getRowFormat();
rowFormat.setHeight(100.0);
rowFormat.setHeightRule(HeightRule.EXACTLY);
table.setLeftPadding(30.0);
table.setRightPadding(30.0);
table.setTopPadding(30.0);
table.setBottomPadding(30.0);
builder.writeln("I'm a wonderfully formatted row.");
```

## 結論

Aspose.Words for Java 可讓您精確地格式化表格並套用表格樣式。從修改單一儲存格格式到建立自訂表格樣式，您擁有使文件具有視覺吸引力和組織性的工具。

## 常見問題解答

### 如何下載 Java 版 Aspose.Words？

您可以從 Aspose 網站下載 Aspose.Words for Java：[下載 Java 版 Aspose.Words](https://releases.aspose.com/words/java/).

### 我可以對表格中的各個儲存格套用不同的邊框嗎？

是的，您可以使用 Aspose.Words for Java 為表格中的各個儲存格設定不同的邊框，如本指南所示。

### 設定表格標題和描述的目的是什麼？

設定表格標題和說明可以增強文件的可訪問性和組織性，使讀者和輔助技術更容易理解內容。

### 如何將條件格式套用至表中的特定行？

您可以透過使用條件格式規則定義自訂表格樣式，將條件格式套用至表格中的特定行，如本指南所示。

### 在哪裡可以找到有關 Aspose.Words for Java 的更多文件和資源？

如需全面的文件和其他資源，請造訪 Aspose.Words for Java 文件：[Aspose.Words for Java 文檔](https://reference.aspose.com/words/java/).