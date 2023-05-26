---
title: Export Into Markdown With Table Content Alignment
linktitle: Export Into Markdown With Table Content Alignment
second_title: Aspose.Words for .NET API Reference
description: Learn how to export table content with different alignments to Markdown files using Aspose.Words for .NET. 
type: docs
weight: 10
url: /net/programming-with-markdownsaveoptions/export-into-markdown-with-table-content-alignment/
---
Here is a step-by-step guide to explain the following C# source code that helps export content to a Markdown file with table content alignment using the Aspose.Words library for .NET. Make sure you have included the Aspose.Words library in your project before using this code.

## Step 1: Set document directory path

```csharp
// The path to the documents directory.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
```

Be sure to specify the correct path to your documents directory where the edited document will be saved.

## Step 2: Create a document and a document generator

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Here we create an instance of the `Document` class and an instance of the `DocumentBuilder` class which will allow us to manipulate the document and add elements.

## Step 3: Insert cells in the table with different paragraph alignments

```csharp
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
builder.Write("Cell1");
builder. InsertCell();
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Write("Cell2");
```

We use the Document Builder to insert cells into the table and set different paragraph alignments for each cell.

## Step 4: Set Markdown export options and save the modified document

```csharp
MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
{
     TableContentAlignment = TableContentAlignment.Left
};
doc.Save(dataDir + "Content_table_left_alignment.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Right;
doc.Save(dataDir + "Content_table_right_alignment.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Center;
doc.Save(dataDir + "Content_table_alignment_center.md", saveOptions);

saveOptions.TableContentAlignment = TableContentAlignment.Auto;
doc.Save(dataDir + "Content_table_auto_alignment.md", saveOptions);
```

We set the Markdown export options with different table content alignments, then save the modified document using each alignment option.

### Example source code to export to Markdown with table content alignment using Aspose.Words for .NET

```csharp

            
	// The path to the documents directory.
    string dataDir = "YOUR DOCUMENT DIRECTORY";
	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Right;
	builder.Write("Cell1");
	builder.InsertCell();
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Write("Cell2");

	// Makes all paragraphs inside the table to be aligned.
	MarkdownSaveOptions saveOptions = new MarkdownSaveOptions
	{
		TableContentAlignment = TableContentAlignment.Left
	};
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.LeftTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Right;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.RightTableContentAlignment.md", saveOptions);

	saveOptions.TableContentAlignment = TableContentAlignment.Center;
	doc.Save(ArtifactsDir + "WorkingWithMarkdownSaveOptions.CenterTableContentAlignment.md", saveOptions);

	// The alignment in this case will be taken from the first paragraph in corresponding table column.
	saveOptions.TableContentAlignment = TableContentAlignment.Auto;
	
	// Save the modified document
	doc.Save(dataDir + "WorkingWithMarkdownSaveOptions.AutoTableContentAlignment.md", saveOptions);
            
        
```

