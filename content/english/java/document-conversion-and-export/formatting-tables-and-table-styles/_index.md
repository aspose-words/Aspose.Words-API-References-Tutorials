---
title: Formatting Tables and Table Styles in Aspose.Words for Java
linktitle: Formatting Tables and Table Styles
second_title: Aspose.Words Java Document Processing API
description: Learn how to format tables and apply table styles in Aspose.Words for Java. Explore step-by-step guides with source code for effective table formatting. Enhance your document layout with Aspose.Words.
type: docs
weight: 17
url: /java/document-conversion-and-export/formatting-tables-and-table-styles/
---

## Introduction to Formatting Tables and Table Styles in Aspose.Words for Java

Tables play a crucial role in structuring and organizing information in documents. Aspose.Words for Java provides powerful features for formatting tables and applying table styles to enhance the visual appeal of your documents. In this step-by-step guide, we'll explore various aspects of formatting tables and applying table styles using Aspose.Words for Java.

## Prerequisites

Before we dive into the details, make sure you have the Aspose.Words for Java library integrated into your project. You can download it from the Aspose website: [Download Aspose.Words for Java](https://releases.aspose.com/words/java/).

## Get Distance Between Table and Surrounding Text

To begin, let's explore how to retrieve the distance between a table and the surrounding text in a document.

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
System.out.println("Distance Top: " + table.getDistanceTop());
System.out.println("Distance Bottom: " + table.getDistanceBottom());
System.out.println("Distance Right: " + table.getDistanceRight());
System.out.println("Distance Left: " + table.getDistanceLeft());
```

## Apply Outline Border to a Table

You can align a table to the center of the page, clear existing borders, and set a custom outline border with this code:

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

## Build a Table with Borders

This code snippet demonstrates how to create a table and set borders for both the table and its cells:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.clearBorders();
table.setBorders(LineStyle.SINGLE, 1.5, Color.GREEN);
```

## Modify Row Formatting

Learn how to modify the formatting of a specific row within a table:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Row firstRow = table.getFirstRow();
firstRow.getRowFormat().getBorders().setLineStyle(LineStyle.NONE);
firstRow.getRowFormat().setHeightRule(HeightRule.AUTO);
firstRow.getRowFormat().setAllowBreakAcrossPages(true);
```

## Apply Row Formatting

This example demonstrates how to apply formatting to an entire row in a table:

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

## Set Cell Padding

Explore how to set padding for individual cells in a table:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.startTable();
builder.insertCell();
builder.getCellFormat().setPaddings(30.0, 50.0, 30.0, 50.0);
builder.writeln("I'm a wonderfully formatted cell.");
```

## Modify Cell Formatting

Discover how to modify the formatting of a specific cell within a table:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
firstCell.getCellFormat().setWidth(30.0);
firstCell.getCellFormat().setOrientation(TextOrientation.DOWNWARD);
firstCell.getCellFormat().getShading().setForegroundPatternColor(Color.GREEN);
```

## Format Table and Cell with Different Borders

Learn how to set different borders for individual cells in a table:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
// Set the table borders
table.setBorders(LineStyle.SINGLE, 2.0, Color.BLACK);
// Set cell shading for individual cells
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.RED);
// Add content to the cells
builder.writeln("Cell #1");
builder.insertCell();
builder.getCellFormat().getShading().setBackgroundPatternColor(Color.GREEN);
builder.writeln("Cell #2");
// Clear cell formatting for the next row
builder.getCellFormat().clearFormatting();
// Create larger borders for the first cell of this row
builder.getCellFormat().getBorders().getLeft().setLineWidth(4.0);
builder.getCellFormat().getBorders().getRight().setLineWidth(4.0);
builder.getCellFormat().getBorders().getTop().setLineWidth(4.0);
builder.getCellFormat().getBorders().getBottom().setLineWidth(4.0);
builder.writeln("Cell #3");
builder.insertCell();
builder.getCellFormat().clearFormatting();
builder.writeln("Cell #4");
```

## Set Table Title and Description

Add a title and description to your table:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setTitle("Test title");
table.setDescription("Test description");
```

## Step 10: Allow Cell Spacing

Allow cell spacing and set its value for a table:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setAllowCellSpacing(true);
table.setCellSpacing(2.0);
```

## Step 11: Build a Table with Style

Create a table with a predefined style:

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

## Step 12: Expand Formatting on Cells and Rows from Style

Learn how to expand table styles to apply formatting to cells and rows:

```java
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
Color cellShadingBefore = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
doc.expandTableStylesToDirectFormatting();
Color cellShadingAfter = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
```

## Step 13: Create a Table Style

Create a custom table style with specific formatting:

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

## Step 14: Define Conditional Formatting

Apply conditional formatting to rows in a table:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
Table table = builder.startTable();
TableStyle tableStyle = (TableStyle) doc.getStyles().add(StyleType.TABLE, "MyTableStyle1");
tableStyle.getConditionalStyles().getFirstRow().getShading().setBackgroundPatternColor(Color.yellow);
table.setStyle(tableStyle);
```

## Step 15: Set TableCell Formatting

Set specific formatting for individual cells:

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

## Step 16: Set TableRow Formatting

Apply formatting to entire rows in a table:

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

## Conclusion

Aspose.Words for Java empowers you to format tables and apply table styles with precision. From modifying individual cell formatting to creating custom table styles, you have the tools to make your documents visually appealing and organized.

## FAQ's

### How do I download Aspose.Words for Java?

You can download Aspose.Words for Java from the Aspose website: [Download Aspose.Words for Java](https://releases.aspose.com/words/java/).

### Can I apply different borders to individual cells within a table?

Yes, you can set different borders for individual cells within a table using Aspose.Words for Java, as demonstrated in this guide.

### What is the purpose of setting a table title and description?

Setting a table title and description enhances the accessibility and organization of your document, making it easier for readers and assistive technologies to understand the content.

### How can I apply conditional formatting to specific rows in a table?

You can apply conditional formatting to specific rows in a table by defining custom table styles with conditional formatting rules, as shown in this guide.

### Where can I find more documentation and resources for Aspose.Words for Java?

For comprehensive documentation and additional resources, please visit the Aspose.Words for Java documentation: [Aspose.Words for Java Documentation](https://reference.aspose.com/words/java/).
