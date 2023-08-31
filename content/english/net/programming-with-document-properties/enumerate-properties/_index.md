---
title: Enumerate Properties
linktitle: Enumerate Properties
second_title: Aspose.Words Document Processing API
description: Step-by-step guide to enumerating document properties with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-document-properties/enumerate-properties/
---

In this tutorial, we will walk you through the C# source code to enumerate document properties with Aspose.Words for .NET. This feature allows you to access built-in and custom properties of a document.

## Step 1: Project Setup

To get started, create a new C# project in your favorite IDE. Make sure the Aspose.Words for .NET library is referenced in your project.

## Step 2: Loading the document

In this step, we will load the Word document whose properties we want to list. Use the following code to load the document:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Properties.docx");
```

Replace `"YOUR DOCUMENTS DIRECTORY"` with the actual path of the directory where your document is located.

## Step 3: Enumerating properties

Now let's list the document properties, both built-in and custom properties. Use the following code:

```csharp
Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
Console.WriteLine("2. Built-in Properties");

foreach(DocumentProperty prop in doc.BuiltInDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);

Console.WriteLine("3. Custom Properties");

foreach(DocumentProperty prop in doc.CustomDocumentProperties)
Console.WriteLine("{0}:{1}", prop.Name, prop.Value);
```

This code displays the document name and then lists the built-in and custom properties displaying their name and value.

### Example source code for Enumerate Properties using Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Properties.docx");
	
	Console.WriteLine("1. Document name: {0}", doc.OriginalFileName);
	Console.WriteLine("2. Built-in Properties");
	
	foreach (DocumentProperty prop in doc.BuiltInDocumentProperties)
		Console.WriteLine("{0} : {1}", prop.Name, prop.Value);

	Console.WriteLine("3. Custom Properties");
	
	foreach (DocumentProperty prop in doc.CustomDocumentProperties)
		Console.WriteLine("{0} : {1}", prop.Name, prop.Value);
		
```

Be sure to specify the correct document path in the `dataDir` variable.

You have now learned how to enumerate document properties using Aspose.Words for .NET. By following the step-by-step guide provided in this tutorial, you can easily access and view the properties of your own documents.


