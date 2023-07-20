---
title: Insert Table Of Contents In Word Document
linktitle: Insert Table Of Contents In Word Document
second_title: Aspose.Words Document Processing API
description: Learn how to insert a table of contents in Word documents using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/add-content-using-documentbuilder/insert-table-of-contents/
---
In this comprehensive tutorial, you will learn how to insert a table of contents into a Word document using Aspose.Words for .NET. We will guide you through the process and provide you with the necessary C# code snippets. By the end of this guide, you will be able to generate a table of contents with appropriate headings and page numbers.

## Prerequisites
Before we begin, ensure that you have the following prerequisites:
- Aspose.Words for .NET library installed on your system.

## Step 1: Create a New Document and DocumentBuilder
To start, create a new document using the Document class and initialize a DocumentBuilder object:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2: Insert a Table of Contents
Next, use the InsertTableOfContents method of the DocumentBuilder class to insert a table of contents. Specify the required formatting options within the method:

```csharp
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");
```

## Step 3: Add Document Content
After inserting the table of contents, add the actual document content. Set the appropriate heading styles using StyleIdentifier:

```csharp
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;
builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;
builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");
```

## Step 4: Update the Table of Contents
The newly inserted table of contents will be initially empty. To populate it, update the fields in the document:

```csharp
doc.UpdateFields();
```

## Step 5: Save the Document
After inserting the table of contents and updating the fields, save the document to a file using the Save method of the Document class:

```csharp
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

### Example Source Code for Insert Table of Contents using Aspose.Words for .NET
Here is the complete source code for inserting a table of contents using Aspose.Words for .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Initialize DocumentBuilder with Document object
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insert table of contenta
builder.InsertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// Start the actual document content on the second page.
builder.InsertBreak(BreakType.PageBreak);

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 1.1");
builder.Writeln("Heading 1.2");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;

builder.Writeln("Heading 2");
builder.Writeln("Heading 3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.1");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading3;

builder.Writeln("Heading 3.1.1");
builder.Writeln("Heading 3.1.2");
builder.Writeln("Heading 3.1.3");

builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading2;

builder.Writeln("Heading 3.2");
builder.Writeln("Heading 3.3");


// The newly inserted table of contents will be initially empty.
// It needs to be populated by updating the fields in the document.
doc.UpdateFields();


doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
```

## Conclusion

Congratulations! You have successfully learned how to insert a table of contents into a Word document using Aspose.Words for .NET. By following this step-by-step guide and utilizing the provided source code, you can now generate a table of contents with appropriate headings and page numbers for your documents.

### FAQ's for insert table of contents in word document

#### Q: Can I customize the appearance of the table of contents?

A: Yes, you can customize the appearance of the table of contents by modifying the formatting options specified in the `InsertTableOfContents` method. The parameters allow you to control the page numbers, indentation, and other styles.

#### Q: What if I want to include specific heading levels in the table of contents?

A: You can specify the desired heading levels to be included in the table of contents by adjusting the value within the `InsertTableOfContents` method. For example, using `"\\o \"1-3\""` will include heading levels 1 to 3.

#### Q: Can I update the table of contents automatically if I make changes to the document content?

A: Yes, you can update the table of contents automatically by calling the `UpdateFields` method on the document. This will ensure that any changes made to the document content, such as adding or removing headings, are reflected in the table of contents.

#### Q: How can I style the heading levels in the table of contents differently?

A: You can style the heading levels differently by using different paragraph styles for each heading level. By assigning different `StyleIdentifier` values to the `ParagraphFormat` of the `DocumentBuilder`, you can create distinct styles for each heading level.

#### Q: Is it possible to add additional formatting to the headings in the table of contents?

A: Yes, you can add additional formatting to the headings in the table of contents, such as font styles, colors, or other properties. By adjusting the `Font` properties of the `DocumentBuilder`, you can apply custom formatting to the headings.
