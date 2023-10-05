---
title: 在 Aspose.Words for Java 中格式化表格和表格样式
linktitle: 设置表格格式和表格样式
second_title: Aspose.Words Java 文档处理 API
description: 了解如何在 Aspose.Words for Java 中设置表格格式并应用表格样式。探索带有源代码的分步指南，以实现有效的表格格式设置。使用 Aspose.Words 增强您的文档布局。
type: docs
weight: 17
url: /zh/java/document-conversion-and-export/formatting-tables-and-table-styles/
---

## Aspose.Words for Java 中的表格格式和表格样式简介

表格在构建和组织文档中的信息方面发挥着至关重要的作用。 Aspose.Words for Java 提供了强大的表格格式化和应用表格样式的功能，以增强文档的视觉吸引力。在本分步指南中，我们将探讨使用 Aspose.Words for Java 设置表格格式和应用表格样式的各个方面。

## 先决条件

在我们深入了解细节之前，请确保您已将 Aspose.Words for Java 库集成到您的项目中。您可以从 Aspose 网站下载：[下载 Java 版 Aspose.Words](https://releases.aspose.com/words/java/).

## 获取表格和周围文本之间的距离

首先，我们来探讨如何检索表格与文档中周围文本之间的距离。

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
System.out.println("Distance Top: " + table.getDistanceTop());
System.out.println("Distance Bottom: " + table.getDistanceBottom());
System.out.println("Distance Right: " + table.getDistanceRight());
System.out.println("Distance Left: " + table.getDistanceLeft());
```

## 将轮廓边框应用于表格

您可以将表格与页面中心对齐，清除现有边框，并使用以下代码设置自定义轮廓边框：

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

## 建立一个有边框的表格

此代码片段演示了如何创建表格并为表格及其单元格设置边框：

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.clearBorders();
table.setBorders(LineStyle.SINGLE, 1.5, Color.GREEN);
```

## 修改行格式

了解如何修改表中特定行的格式：

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Row firstRow = table.getFirstRow();
firstRow.getRowFormat().getBorders().setLineStyle(LineStyle.NONE);
firstRow.getRowFormat().setHeightRule(HeightRule.AUTO);
firstRow.getRowFormat().setAllowBreakAcrossPages(true);
```

## 应用行格式

此示例演示如何将格式应用于表中的整行：

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

## 设置单元格内边距

了解如何为表格中的各个单元格设置填充：

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.startTable();
builder.insertCell();
builder.getCellFormat().setPaddings(30.0, 50.0, 30.0, 50.0);
builder.writeln("I'm a wonderfully formatted cell.");
```

## 修改单元格格式

了解如何修改表格中特定单元格的格式：

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
firstCell.getCellFormat().setWidth(30.0);
firstCell.getCellFormat().setOrientation(TextOrientation.DOWNWARD);
firstCell.getCellFormat().getShading().setForegroundPatternColor(Color.GREEN);
```

## 设置具有不同边框的表格和单元格格式

了解如何为表格中的各个单元格设置不同的边框：

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
//设置表格边框
table.setBorders(LineStyle.SINGLE, 2.0, Color.BLACK);
//设置单个单元格的单元格阴影
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.RED);
//向单元格添加内容
builder.writeln("Cell #1");
builder.insertCell();
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.GREEN);
builder.writeln("Cell #2");
//清除下一行的单元格格式
builder.getCellFormat().clearFormatting();
//为该行的第一个单元格创建更大的边框
builder.getCellFormat().getBorders().getLeft().setLineWidth(4.0);
builder.getCellFormat().getBorders().getRight().setLineWidth(4.0);
builder.getCellFormat().getBorders().getTop().setLineWidth(4.0);
builder.getCellFormat().getBorders().getBottom().setLineWidth(4.0);
builder.writeln("Cell #3");
builder.insertCell();
builder.getCellFormat().clearFormatting();
builder.writeln("Cell #4");
```

## 设置表格标题和描述

向表格添加标题和说明：

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setTitle("Test title");
table.setDescription("Test description");
```

## 第 10 步：留出单元格间距

允许单元格间距并为表格设置其值：

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setAllowCellSpacing(true);
table.setCellSpacing(2.0);
```

## 第11步：建立一个有风格的表格

创建具有预定义样式的表格：

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

## 第12步：从样式中展开单元格和行的格式设置

了解如何扩展表格样式以将格式应用于单元格和行：

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
Color cellShadingBefore = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
doc.expandTableStylesToDirectFormatting();
Color cellShadingAfter = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
```

## 第13步：创建表格样式

创建具有特定格式的自定义表格样式：

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

## 第 14 步：定义条件格式

将条件格式应用于表中的行：

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
TableStyle tableStyle = (TableStyle) doc.getStyles().add(StyleType.TABLE, "MyTableStyle1");
tableStyle.getConditionalStyles().getFirstRow().getShading().setBackgroundPatternColor(Color.yellow);
table.setStyle(tableStyle);
```

## 第15步：设置TableCell格式

为单个单元格设置特定格式：

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

## 第16步：设置TableRow格式

将格式应用于表中的整行：

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

## 结论

Aspose.Words for Java 使您能够精确格式化表格并应用表格样式。从修改单个单元格格式到创建自定义表格样式，您拥有使文档具有视觉吸引力和组织性的工具。

## 常见问题解答

### 如何下载 Java 版 Aspose.Words？

您可以从 Aspose 网站下载 Aspose.Words for Java：[下载 Java 版 Aspose.Words](https://releases.aspose.com/words/java/).

### 我可以对表格中的各个单元格应用不同的边框吗？

是的，您可以使用 Aspose.Words for Java 为表格中的各个单元格设置不同的边框，如本指南中所示。

### 设置表格标题和描述的目的是什么？

设置表格标题和说明可以增强文档的可访问性和组织性，使读者和辅助技术更容易理解内容。

### 如何将条件格式应用于表中的特定行？

您可以通过使用条件格式规则定义自定义表格样式，将条件格式应用于表格中的特定行，如本指南中所示。

### 在哪里可以找到有关 Aspose.Words for Java 的更多文档和资源？

如需全面的文档和其他资源，请访问 Aspose.Words for Java 文档：[Aspose.Words for Java 文档](https://reference.aspose.com/words/java/).