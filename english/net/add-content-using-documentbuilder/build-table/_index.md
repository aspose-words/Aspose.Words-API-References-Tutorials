---
title: Build Table
linktitle: Build Table
second_title: Aspose.Words Document Processing API
description: Learn how to build a table in a Word document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/add-content-using-documentbuilder/build-table/
---

In this step-by-step tutorial, you will learn how to build a table in a Word document using Aspose.Words for .NET. We will guide you through the process and provide you with the necessary C# code snippets. By the end of this guide, you will be able to create a table with custom formatting and content using the DocumentBuilder class.

## Prerequisites
Before we begin, ensure that you have the following prerequisites:
- Aspose.Words for .NET library installed on your system.

## Step 1: Create a New Document
To start, create a new document using the Document class:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2: Start the Table
Next, use the StartTable method of the DocumentBuilder class to start building the table:

```csharp
Table table = builder.StartTable();
```

## Step 3: Insert Cells and Add Content
Now, you can insert cells into the table and add content to them using the InsertCell and Write methods of the DocumentBuilder class. Customize the cell formatting as needed:

```csharp
builder.InsertCell();
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");
```

## Step 4: End the Row
After adding content to the cells of the first row, use the EndRow method of the DocumentBuilder class to end the row:

```csharp
builder.EndRow();
```

## Step 5: Customize Row Formatting
You can customize the formatting of a row by setting properties of the RowFormat and CellFormat objects:

```csharp
builder.InsertCell();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");
```

## Step 6: End the Table
To complete the table, use the EndTable method of the DocumentBuilder class:

```csharp
builder.EndTable();
```

### Example Source Code for Building a Table using Aspose.Words for .NET
Here is the complete source code for building a table using Aspose.Words for .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Table table = builder.StartTable();
builder.InsertCell();
table.AutoFit(AutoFitBehavior.FixedColumnWidths);

builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.Write("This is row 1 cell 1");

builder.InsertCell();
builder.Write("This is row 1 cell 2");

builder.EndRow();

builder.InsertCell();

builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
builder.CellFormat.Orientation = TextOrientation.Upward;
builder.Writeln("This is row 2 cell 1");

builder.InsertCell();
builder.CellFormat.Orientation = TextOrientation.Downward;
builder.Writeln("This is row 2 cell 2");

builder.EndRow();
builder.EndTable();

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.BuildTable.docx");
```

## Conclusion
Congratulations! You have successfully learned how to build a table in a Word document using Aspose.Words for .NET. By following the step-by-step guide and utilizing the provided source code, you can now create tables with custom formatting.