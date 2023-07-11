---
title: Insert Break
linktitle: Insert Break
second_title: Aspose.Words Document Processing API
description: Learn how to insert page breaks in Word documents using Aspose.Words for .NET. Step-by-step guide.
type: docs
weight: 10
url: /net/add-content-using-documentbuilder/insert-break/
---

In this comprehensive example, you will learn how to insert page breaks into a Word document using the InsertBreak method in Aspose.Words for .NET. We will guide you through the process and provide you with the necessary C# code snippets. By the end of this guide, you will be able to control page breaks within your document.

## Prerequisites
Before we begin, ensure that you have the following prerequisites:
- Aspose.Words for .NET library installed on your system.

## Step 1: Create a New Document and DocumentBuilder
To start, create a new document using the Document class and initialize a DocumentBuilder object:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2: Insert Content and Page Breaks
Next, use the Writeln method of the DocumentBuilder class to add content to the document. To insert a page break, use the InsertBreak method with the BreakType.PageBreak parameter:

```csharp
builder.Writeln("This is page 1.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 2.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 3.");
```

## Step 3: Save the Document
After inserting the content and page breaks, save the document to a file using the Save method of the Document class:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertBreak.docx");
```

### Example Source Code for Insert Break using Aspose.Words for .NET
Here is the complete source code for inserting page breaks using Aspose.Words for .NET:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Writeln("This is page 1.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 2.");
builder.InsertBreak(BreakType.PageBreak);

builder.Writeln("This is page 3.");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertBreak.docx");
```

Remember to adjust the code according to your specific requirements and enhance it with additional functionality as needed.


## Conclusion
Congratulations! You have successfully learned how to insert page breaks into a Word document using Aspose.Words for .NET. By following the step-by-step guide and utilizing the provided source code, you can now control the pagination and layout of your document by inserting page breaks at desired positions.

