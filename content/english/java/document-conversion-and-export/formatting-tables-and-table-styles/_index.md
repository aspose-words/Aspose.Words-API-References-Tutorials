---
title: Formatting Tables and Table Styles in Aspose.Words for Java
linktitle: Formatting Tables and Table Styles in Aspose.Words for Java
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

## Step 1: Get Distance Between Table and Surrounding Text

To begin, let's explore how to retrieve the distance between a table and the surrounding text in a document.

```java
Document doc = new Document(getMyDir() + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
System.out.println("Distance Top: " + table.getDistanceTop());
System.out.println("Distance Bottom: " + table.getDistanceBottom());
System.out.println("Distance Right: " + table.getDistanceRight());
System.out.println("Distance Left: " + table.getDistanceLeft());
```

## Step 2: Apply Outline Border to a Table

You can align a table to the center of the page, clear existing borders, and set a custom outline border with this code:

```java
Document doc = new Document(getMyDir() + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setAlignment(TableAlignment.CENTER);
table.clearBorders();
table.setBorder(BorderType.LEFT, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setBorder(BorderType.RIGHT, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setBorder(BorderType.TOP, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setBorder(BorderType.BOTTOM, LineStyle.SINGLE, 1.5, Color.GREEN, true);
table.setShading(TextureIndex.TEXTURE_SOLID, Color.lightGray, new Color(0, true));
```

## Step 3: Build a Table with Borders

This code snippet demonstrates how to create a table and set borders for both the table and its cells:

```java
Document doc = new Document(getMyDir() + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.clearBorders();
table.setBorders(LineStyle.SINGLE, 1.5, Color.GREEN);
```

## Step 4: Modify Row Formatting

Learn how to modify the formatting of a specific row within a table:

```java
Document doc = new Document(getMyDir() + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Row firstRow = table.getFirstRow();
firstRow.getRowFormat().getBorders().setLineStyle(LineStyle.NONE);
firstRow.getRowFormat().setHeightRule(HeightRule.AUTO);
firstRow.getRowFormat().setAllowBreakAcrossPages(true);
```

## Step 5: Apply Row Formatting

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

## Step 6: Set Cell Padding

Explore how to set padding for individual cells in a table:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.startTable();
builder.insertCell();
builder.getCellFormat().setPaddings(30.0, 50.0, 30.0, 50.0);
builder.writeln("I'm a wonderfully formatted cell.");
```

## Step 7: Modify Cell Formatting

Discover how to modify the formatting of a specific cell within a table:

```java
Document doc = new Document(getMyDir() + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
Cell firstCell = table.getFirstRow().getFirstCell();
firstCell.getCellFormat().setWidth(30.0);
firstCell.getCellFormat().setOrientation(TextOrientation.DOWNWARD);
firstCell.getCellFormat().getShading().setForegroundPatternColor(Color.GREEN);
```

## Step 8: Format Table and Cell with Different Borders

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

## Step 9: Set Table Title and Description

Add a title and description to your table:

```java
Document doc = new Document(getMyDir() + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
table.setTitle("Test title");
table.setDescription("Test description");
```

## Step 10: Allow Cell Spacing

Allow cell spacing and set its value for a table:

```java
Document doc = new Document(getMyDir() + "Tables.docx");
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
Document doc = new Document(getMyDir() + "Tables.docx");
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

## Complete Source Code For Formatting Tables and Table Styles in Aspose.Words for Java

```java
	Document doc = new Document(getMyDir() + "Tables.docx");
	System.out.println("\nGet distance between table left, right, bottom, top and the surrounding text.");
	Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
	System.out.println(table.getDistanceTop());
	System.out.println(table.getDistanceBottom());
	System.out.println(table.getDistanceRight());
	System.out.println(table.getDistanceLeft());
}
@Test
public void applyOutlineBorder() throws Exception
{
	Document doc = new Document(getMyDir() + "Tables.docx");
	Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
	// Align the table to the center of the page.
	table.setAlignment(TableAlignment.CENTER);
	// Clear any existing borders from the table.
	table.clearBorders();
	// Set a green border around the table but not inside.
	table.setBorder(BorderType.LEFT, LineStyle.SINGLE, 1.5, Color.GREEN, true);
	table.setBorder(BorderType.RIGHT, LineStyle.SINGLE, 1.5, Color.GREEN, true);
	table.setBorder(BorderType.TOP, LineStyle.SINGLE, 1.5, Color.GREEN, true);
	table.setBorder(BorderType.BOTTOM, LineStyle.SINGLE, 1.5, Color.GREEN, true);
	// Fill the cells with a light green solid color.
	table.setShading(TextureIndex.TEXTURE_SOLID, Color.lightGray, new Color(0, true));
	doc.save(getArtifactsDir() + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
}
@Test
public void buildTableWithBorders() throws Exception
{
	Document doc = new Document(getMyDir() + "Tables.docx");
	Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
	// Clear any existing borders from the table.
	table.clearBorders();
	// Set a green border around and inside the table.
	table.setBorders(LineStyle.SINGLE, 1.5, Color.GREEN);
	doc.save(getArtifactsDir() + "WorkingWithTableStylesAndFormatting.BuildTableWithBorders.docx");
}
@Test
public void modifyRowFormatting() throws Exception
{
	Document doc = new Document(getMyDir() + "Tables.docx");
	Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
	// Retrieve the first row in the table.
	Row firstRow = table.getFirstRow();
	firstRow.getRowFormat().getBorders().setLineStyle(LineStyle.NONE);
	firstRow.getRowFormat().setHeightRule(HeightRule.AUTO);
	firstRow.getRowFormat().setAllowBreakAcrossPages(true);
}
@Test
public void applyRowFormatting() throws Exception
{
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.startTable();
	builder.insertCell();
	RowFormat rowFormat = builder.getRowFormat();
	rowFormat.setHeight(100.0);
	rowFormat.setHeightRule(HeightRule.EXACTLY);
	// These formatting properties are set on the table and are applied to all rows in the table.
	table.setLeftPadding(30.0);
	table.setRightPadding(30.0);
	table.setTopPadding(30.0);
	table.setBottomPadding(30.0);
	builder.writeln("I'm a wonderful formatted row.");
	builder.endRow();
	builder.endTable();
	doc.save(getArtifactsDir() + "WorkingWithTableStylesAndFormatting.ApplyRowFormatting.docx");
}
@Test
public void setCellPadding() throws Exception
{
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.startTable();
	builder.insertCell();
	// Sets the amount of space (in points) to add to the left/top/right/bottom of the cell's contents.
	builder.getCellFormat().setPaddings(30.0, 50.0, 30.0, 50.0);
	builder.writeln("I'm a wonderful formatted cell.");
	builder.endRow();
	builder.endTable();
	doc.save(getArtifactsDir() + "WorkingWithTableStylesAndFormatting.SetCellPadding.docx");
}
/// <summary>
/// Shows how to modify formatting of a table cell.
/// </summary>
@Test
public void modifyCellFormatting() throws Exception
{
	Document doc = new Document(getMyDir() + "Tables.docx");
	Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
	Cell firstCell = table.getFirstRow().getFirstCell();
	firstCell.getCellFormat().setWidth(30.0);
	firstCell.getCellFormat().setOrientation(TextOrientation.DOWNWARD);
	firstCell.getCellFormat().getShading().setForegroundPatternColor(Color.GREEN);
}
@Test
public void formatTableAndCellWithDifferentBorders() throws Exception
{
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.startTable();
	builder.insertCell();
	// Set the borders for the entire table.
	table.setBorders(LineStyle.SINGLE, 2.0, Color.BLACK);
	// Set the cell shading for this cell.
	builder.getCellFormat().getShading().setBackgroundPatternColor(Color.RED);
	builder.writeln("Cell #1");
	builder.insertCell();
	// Specify a different cell shading for the second cell.
	builder.getCellFormat().getShading().setBackgroundPatternColor(Color.GREEN);
	builder.writeln("Cell #2");
	builder.endRow();
	// Clear the cell formatting from previous operations.
	builder.getCellFormat().clearFormatting();
	builder.insertCell();
	// Create larger borders for the first cell of this row. This will be different
	// compared to the borders set for the table.
	builder.getCellFormat().getBorders().getLeft().setLineWidth(4.0);
	builder.getCellFormat().getBorders().getRight().setLineWidth(4.0);
	builder.getCellFormat().getBorders().getTop().setLineWidth(4.0);
	builder.getCellFormat().getBorders().getBottom().setLineWidth(4.0);
	builder.writeln("Cell #3");
	builder.insertCell();
	builder.getCellFormat().clearFormatting();
	builder.writeln("Cell #4");
	doc.save(getArtifactsDir() + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
}
@Test
public void setTableTitleAndDescription() throws Exception
{
	Document doc = new Document(getMyDir() + "Tables.docx");
	Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
	table.setTitle("Test title");
	table.setDescription("Test description");
	OoxmlSaveOptions options = new OoxmlSaveOptions(); { options.setCompliance(OoxmlCompliance.ISO_29500_2008_STRICT); }
	doc.getCompatibilityOptions().optimizeFor(com.aspose.words.MsWordVersion.WORD_2016);
	doc.save(getArtifactsDir() + "WorkingWithTableStylesAndFormatting.SetTableTitleAndDescription.docx", options);
}
@Test
public void allowCellSpacing() throws Exception
{
	Document doc = new Document(getMyDir() + "Tables.docx");
	Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
	table.setAllowCellSpacing(true);
	table.setCellSpacing(2.0);
	doc.save(getArtifactsDir() + "WorkingWithTableStylesAndFormatting.AllowCellSpacing.docx");
}
@Test
public void buildTableWithStyle() throws Exception
{
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.startTable();
	// We must insert at least one row first before setting any table formatting.
	builder.insertCell();
	// Set the table style used based on the unique style identifier.
	table.setStyleIdentifier(StyleIdentifier.MEDIUM_SHADING_1_ACCENT_1);
	// Apply which features should be formatted by the style.
	table.setStyleOptions(TableStyleOptions.FIRST_COLUMN | TableStyleOptions.ROW_BANDS | TableStyleOptions.FIRST_ROW);
	table.autoFit(AutoFitBehavior.AUTO_FIT_TO_CONTENTS);
	builder.writeln("Item");
	builder.getCellFormat().setRightPadding(40.0);
	builder.insertCell();
	builder.writeln("Quantity (kg)");
	builder.endRow();
	builder.insertCell();
	builder.writeln("Apples");
	builder.insertCell();
	builder.writeln("20");
	builder.endRow();
	builder.insertCell();
	builder.writeln("Bananas");
	builder.insertCell();
	builder.writeln("40");
	builder.endRow();
	builder.insertCell();
	builder.writeln("Carrots");
	builder.insertCell();
	builder.writeln("50");
	builder.endRow();
	doc.save(getArtifactsDir() + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
}
@Test
public void expandFormattingOnCellsAndRowFromStyle() throws Exception
{
	Document doc = new Document(getMyDir() + "Tables.docx");
	// Get the first cell of the first table in the document.
	Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
	Cell firstCell = table.getFirstRow().getFirstCell();
	// First print the color of the cell shading.
	// This should be empty as the current shading is stored in the table style.
	Color cellShadingBefore = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
	System.out.println("Cell shading before style expansion: " + cellShadingBefore);
	doc.expandTableStylesToDirectFormatting();
	// Now print the cell shading after expanding table styles.
	// A blue background pattern color should have been applied from the table style.
	Color cellShadingAfter = firstCell.getCellFormat().getShading().getBackgroundPatternColor();
	System.out.println("Cell shading after style expansion: " + cellShadingAfter);
}
@Test
public void createTableStyle() throws Exception
{
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.startTable();
	builder.insertCell();
	builder.write("Name");
	builder.insertCell();
	builder.write("Value");
	builder.endRow();
	builder.insertCell();
	builder.insertCell();
	builder.endTable();
	TableStyle tableStyle = (TableStyle) doc.getStyles().add(StyleType.TABLE, "MyTableStyle1");
	tableStyle.getBorders().setLineStyle(LineStyle.DOUBLE);
	tableStyle.getBorders().setLineWidth(1.0);
	tableStyle.setLeftPadding(18.0);
	tableStyle.setRightPadding(18.0);
	tableStyle.setTopPadding(12.0);
	tableStyle.setBottomPadding(12.0);
	table.setStyle(tableStyle);
	doc.save(getArtifactsDir() + "WorkingWithTableStylesAndFormatting.CreateTableStyle.docx");
}
@Test
public void defineConditionalFormatting() throws Exception
{
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.startTable();
	builder.insertCell();
	builder.write("Name");
	builder.insertCell();
	builder.write("Value");
	builder.endRow();
	builder.insertCell();
	builder.insertCell();
	builder.endTable();
	TableStyle tableStyle = (TableStyle) doc.getStyles().add(StyleType.TABLE, "MyTableStyle1");
	tableStyle.getConditionalStyles().getFirstRow().getShading().setBackgroundPatternColor(Color.yellow);
	tableStyle.getConditionalStyles().getFirstRow().getShading().setTexture(TextureIndex.TEXTURE_NONE);
	table.setStyle(tableStyle);
	doc.save(getArtifactsDir() + "WorkingWithTableStylesAndFormatting.DefineConditionalFormatting.docx");
}
@Test
public void setTableCellFormatting() throws Exception
{
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
	builder.writeln("I'm a wonderful formatted cell.");
	builder.endRow();
	builder.endTable();
	doc.save(getArtifactsDir() + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableCellFormatting.docx");
}
@Test
public void setTableRowFormatting() throws Exception
{
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.startTable();
	builder.insertCell();
	RowFormat rowFormat = builder.getRowFormat();
	rowFormat.setHeight(100.0);
	rowFormat.setHeightRule(HeightRule.EXACTLY);
	// These formatting properties are set on the table and are applied to all rows in the table.
	table.setLeftPadding(30.0);
	table.setRightPadding(30.0);
	table.setTopPadding(30.0);
	table.setBottomPadding(30.0);
	builder.writeln("I'm a wonderful formatted row.");
	builder.endRow();
	builder.endTable();
	doc.save(getArtifactsDir() + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
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
