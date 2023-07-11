---
title: Insert Table From Html
linktitle: Insert Table From Html
second_title: Aspose.Words Document Processing API
description: Learn how to insert a table from HTML into a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-tables/insert-table-from-html/
---

In this tutorial, we will learn how to insert a table into a Word document from HTML using Aspose.Words for .NET. We will follow a step by step guide to understand the code and implement this feature. By the end of this tutorial, you will be able to insert tables from HTML into your Word documents programmatically.

## Step 1: Project Setup
1. Launch Visual Studio and create a new C# project.
2. Add a reference to the Aspose.Words for .NET library.

## Step 2: Creating the document and initializing the document generator
To start working with the document and document generator, follow these steps:

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Document creation
Document doc = new Document();

// Initialize the document generator
DocumentBuilder builder = new DocumentBuilder(doc);
```

Be sure to replace "YOUR DOCUMENTS DIRECTORY" with the actual path to your documents directory.

## Step 3: Inserting the table from HTML
Next, we will insert the table into the document using HTML code. Use the following code:

```csharp
builder.InsertHtml("<table>" +
"<tr>" +
"<td>Line 1, Cell 1</td>" +
"<td>Line 1, Cell 2</td>" +
"</tr>" +
"<tr>" +
"<td>Line 2, Cell 1</td>" +
"<td>Line 2, Cell 2</td>" +
"</tr>" +
"</table>");
```

Here we use the `InsertHtml` method of the document builder to insert the HTML containing the table. The specified HTML creates a table with two rows and two cells in each row. You can customize the content of the table by modifying the HTML code according to your needs.

## Step 4: Saving the modified document
Finally, we need to save the modified document with the table inserted from HTML. Use the following code:

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

Be sure to specify the correct path and filename for the output document.

### Sample source code for Insert Table From Html using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Note that AutoFitSettings does not apply to tables inserted from HTML.
	builder.InsertHtml("<table>" +
					   "<tr>" +
					   "<td>Row 1, Cell 1</td>" +
					   "<td>Row 1, Cell 2</td>" +
					   "</tr>" +
					   "<tr>" +
					   "<td>Row 2, Cell 2</td>" +
					   "<td>Row 2, Cell 2</td>" +
					   "</tr>" +
					   "</table>");
	doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

## Conclusion
In this tutorial, we learned how to insert a table into a Word document from HTML using Aspose.Words for .NET. By following this step-by-step guide and implementing the provided C# code, you can insert tables from HTML into your Word documents programmatically. This feature allows you to convert and import tabular data from HTML sources into your Word documents.

