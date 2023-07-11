---
title: Insert Ole Object In Word Document
linktitle: Insert Ole Object In Word Document
second_title: Aspose.Words Document Processing API
description: Learn how to insert an OLE object in word document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-oleobjects-and-activex/insert-ole-object/
---

Here is a step by step guide to explain the C# source code below that illustrates how to insert an OLE object in word document using Aspose.Words for .NET.

## Step 1: Import the necessary references
Before you begin, make sure you have imported the necessary references to use Aspose.Words for .NET into your project. This includes importing the Aspose.Words library and adding the required namespaces to your source file.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Step 2: Create a new document and document generator
In this step, we will create a new document using the `Document` class and a document builder using the `DocumentBuilder` class.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 3: Insert an OLE object
Use the Document Builder's `InsertOleObject` method to insert an OLE object into the document. Specify the OLE object URL, object type, display options, and other necessary settings.

```csharp
builder. InsertOleObject("http://www.aspose.com", "htmlfile", true, true, null);
```

## Step 4: Save the document
Use the document's `Save` method to save the document to a file.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

### Example source code for inserting an OLE object with Aspose.Words for .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com", "htmlfile", true, true, null);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

This is a complete code sample for inserting an OLE object with Aspose.Words for .NET. Be sure to import the necessary references and follow the steps previously described to integrate this code into your project.

## Conclusion

In conclusion, inserting OLE objects into a Word document is a powerful feature offered by Aspose.Words for .NET. Using this library, you can easily embed OLE objects such as HTML files, Excel spreadsheets, PowerPoint presentations, etc., into your Word documents.

In this article, we have gone through a step-by-step guide to explain the source code in C# that illustrates how to insert an OLE object into a Word document. We covered the necessary references, creating a new document and a document generator, and the steps to insert an OLE object and save the document.

### FAQ's for inserting an OLE object into a Word document

#### Q: What credentials do I need to import to use Aspose.Words for .NET?

A: To use Aspose.Words for .NET, you need to import the following references:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### Q: How to create a new document and a document generator?

A: You can create a new document using the `Document` class and a document builder using the `DocumentBuilder` class, as shown below:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### Q: How to insert an OLE object in the document?

A: Use the `InsertOleObject` method of the document builder (`DocumentBuilder`) to insert an OLE object into the document. Specify the OLE object URL, object type, display options, and other necessary settings. Here is an example :

```csharp
builder. InsertOleObject("http://www.aspose.com", "htmlfile", true, true, null);
```

#### Q: How to save the document?

A: Use the document `Save` method to save the document to a file. Here is an example :

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

#### Q: Can you provide a complete example of inserting an OLE object with Aspose.Words for .NET?

A: Here is a complete sample code to insert an OLE object with Aspose.Words for .NET. Be sure to import the necessary references and follow the steps previously described to integrate this code into your project:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder. InsertOleObject("http://www.aspose.com", "htmlfile", true, true, null);

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObject.docx");
```

