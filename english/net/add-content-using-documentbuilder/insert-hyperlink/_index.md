---
title: Insert Hyperlink
linktitle: Insert Hyperlink
second_title: Aspose.Words Document Processing API
description: Learn how to insert hyperlinks in Word documents using Aspose.Words for .NET Step-by-step guide.
type: docs
weight: 10
url: /net/add-content-using-documentbuilder/insert-hyperlink/
---

In this comprehensive tutorial, you will learn how to insert hyperlinks into a Word document using Aspose.Words for .NET. We will guide you through the process and provide you with the necessary C# code snippets. By the end of this guide, you will be able to add clickable hyperlinks to your documents.

## Prerequisites
Before we begin, ensure that you have the following prerequisites:
- Aspose.Words for .NET library installed on your system.

## Step 1: Create a New Document and DocumentBuilder
To start, create a new document using the Document class and initialize a DocumentBuilder object:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2: Insert a Hyperlink
Next, use the Write method of the DocumentBuilder class to add text, and format the hyperlink by setting the color and underline properties:

```csharp
builder.Write("Please make sure to visit ");
builder.Font.Color = Color.Blue;
builder.Font.Underline = Underline.Single;

builder.InsertHyperlink("Aspose Website", "http://www.aspose.com", false);

builder.Font.ClearFormatting();
builder.Write(" for more information.");
```

## Step 3: Save the Document
After inserting the hyperlink, save the document to a file using the Save method of the Document class:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHyperlink.docx");
```

## Example Source Code for Insert Hyperlink using Aspose.Words for .NET
Here is the complete source code for inserting a hyperlink using Aspose.Words for .NET:

Hyperlinks are a powerful way to enhance the interactivity and usefulness of your Word documents. They can be used to reference external resources, provide additional information, or create navigational elements within the document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Please make sure to visit ");
builder.Font.Color = Color.Blue;
builder.Font.Underline = Underline.Single;

builder.InsertHyperlink("Aspose Website", "http://www.aspose.com", false);

builder.Font.ClearFormatting();
builder.Write(" for more information.");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.InsertHyperlink.docx");
```

Remember to adjust the code according to your specific requirements, including the hyperlink text and URL. Enhance it with additional formatting or functionality as needed.

## Conclusion
Congratulations! You have successfully learned how to insert hyperlinks into a Word document using Aspose.Words for .NET. By following the step-by-step guide and utilizing the provided source code, you can now add clickable hyperlinks to your documents, directing readers to external websites or specific URLs.


