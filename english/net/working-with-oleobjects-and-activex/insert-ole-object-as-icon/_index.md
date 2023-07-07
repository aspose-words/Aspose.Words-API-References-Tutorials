---
title: Insert Ole Object In Word Document As Icon
linktitle: Insert Ole Object In Word Document As Icon
second_title: Aspose.Words for .NET API Reference
description: Learn how to insert an OLE object in word document as icon with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-oleobjects-and-activex/insert-ole-object-as-icon/
---

Here is a step by step guide to explain the C# source code below that illustrates how to insert an OLE object in word document as icon using Aspose.Words for .NET.

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

## Step 3: Insert an OLE object as an icon
Use the Document Builder's `InsertOleObjectAsIcon` method to insert an OLE object as an icon into the document. Specify the OLE file path, display flag, icon path, and embedded object name.

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

## Step 4: Save the document
Use the document's `Save` method to save the document to a file.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

### Example source code for inserting an OLE object as an icon with Aspose.Words for .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```

This is a complete code sample for inserting an OLE object as an icon with Aspose.Words for .NET. Be sure to import the necessary references and follow the steps previously described to integrate this code into your project.

## Conclusion

In conclusion, we explored a step-by-step guide to insert an OLE object as an icon in a Word document using Aspose.Words for .NET.

By following these steps, you will be able to successfully insert an OLE object as an icon in your Word documents using Aspose.Words for .NET. Be sure to import the necessary references and follow the instructions carefully to get the desired results.

### FAQ's for insert ole object in word document as icon

#### Q. What references are needed to insert an OLE object as an icon in a Word document using Aspose.Words for .NET?

A: You need to import the following references into your project to use Aspose.Words for .NET:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
```

#### Q. How to create a new document and document generator in Aspose.Words for .NET?

A: You can create a new document using the `Document` class and a document builder using the `DocumentBuilder` class. Here is an example :

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### Q. How to insert an OLE object as an icon in the document?

A: Use the Document Builder's `InsertOleObjectAsIcon` method to insert an OLE object as an icon. Specify the OLE file path, display flag, icon path, and embedded object name. Here is an example :

```csharp
builder.InsertOleObjectAsIcon(MyDir + "Presentation.pptx", false, ImagesDir + "Logo icon.ico", "My embedded file");
```

#### Q. How to save the document with the OLE object inserted as an icon?

A: Use the document `Save` method to save the document to a file. Here is an example :

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIcon.docx");
```
