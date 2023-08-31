---
title: Build Table In Word Document
linktitle: Build Table In Word Document
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

### FAQ's for build table in word document

#### Q: What is Aspose.Words for .NET?

A: Aspose.Words for .NET is a powerful document processing library that allows developers to create, read, edit, and convert Microsoft Word documents programmatically in .NET applications. It provides a wide range of features to work with Word documents, such as text manipulation, table creation, document protection, formatting, and more.

#### Q: How can I build a table in a Word document using Aspose.Words for .NET?

A: To build a table in a Word document using Aspose.Words for .NET, you can follow these steps:
1. Create a new instance of the `Document` class and a `DocumentBuilder` object.
2. Use the `StartTable` method of the `DocumentBuilder` class to start building the table.
3. Insert cells into the table and add content using the `InsertCell` and `Write` methods of the `DocumentBuilder` class.
4. End the row using the `EndRow` method of the `DocumentBuilder` class.
5. Customize row formatting by setting properties of the `RowFormat` and `CellFormat` objects.
6. End the table using the `EndTable` method of the `DocumentBuilder` class.
7. Save the document.

#### Q: How can I customize the formatting of the table and its cells?

A: You can customize the formatting of the table and its cells by setting various properties of the `RowFormat` and `CellFormat` objects. For example, you can adjust cell alignment, vertical and horizontal text orientation, cell height, row height, and more. By using these properties, you can achieve the desired appearance for the table and its contents.

#### Q: Can I build complex tables with merged cells and other advanced features?

A: Yes, Aspose.Words for .NET provides advanced features to build complex tables, including support for merged cells, nested tables, and complex table layouts. You can use the `MergeCells` method to merge cells, `StartTable` method to create nested tables, and other methods to achieve the desired table structure.

#### Q: Is Aspose.Words for .NET compatible with different Word document formats?

A: Yes, Aspose.Words for .NET is compatible with various Word document formats, including DOC, DOCX, RTF, and more. It supports both legacy formats (DOC) and modern XML-based formats (DOCX) and allows you to work with documents in different formats without any issues.

#### Q: Where can I find more information and documentation for Aspose.Words for .NET?

A: You can find comprehensive documentation and code examples on [API references](https://reference.aspose.com/words/net/). The documentation will provide detailed information about the library's features and how to use them in your .NET applications.
