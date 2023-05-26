---
title: Create New Document
linktitle: Create New Document
second_title: Aspose.Words for .NET API Reference
description: Learn how to create a new Word document and add content using Aspose.Words for .NET. Step-by-step guide.
type: docs
weight: 10
url: /net/add-content-using-documentbuilder/create-new-document/
---

In this step-by-step tutorial, you will learn how to create a new Word document from scratch using Aspose.Words for .NET. We will guide you through the process and provide you with the necessary C# code snippets. By the end of this guide, you will be able to generate a new document and add content to it using the DocumentBuilder class.

## Prerequisites
Before we begin, ensure that you have the following prerequisites:
- Aspose.Words for .NET library installed on your system.

## Step 1: Create a New Document
To start, create a new document using the Document class:

```csharp
Document doc = new Document();
```

## Step 2: Add Content to the Document
Next, use a DocumentBuilder object to add content to the document. Initialize the DocumentBuilder with the newly created document:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello World!");
```

## Step 3: Save the Document
After adding the desired content, save the document to a file using the Save method of the Document class:

```csharp
doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.CreateNewDocument.docx");
```

## Example Source Code for Creating a New Document using Aspose.Words for .NET
Here is the complete source code for creating a new document using Aspose.Words for .NET:

```csharp
Document doc = new Document();

// Use a document builder to add content to the document.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello World!");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.CreateNewDocument.docx");
```

## Conclusion

Congratulations! You have successfully learned how to create a new Word document using Aspose.Words for .NET. By following the step-by-step guide and utilizing the provided source code, you can now generate new documents programmatically and add content to them using the DocumentBuilder class.

Now you can confidently create and customize Word documents according to your specific requirements.

### Example source code for Creating a New Document using Aspose.Words for .NET:

```csharp
Document doc = new Document();

// Use a document builder to add content to the document.
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Writeln("Hello World!");

doc.Save(ArtifactsDir + "AddContentUsingDocumentBuilder.CreateNewDocument.docx");
```

Remember to adjust the file path and name in the code to save the document to the desired location on your system.


