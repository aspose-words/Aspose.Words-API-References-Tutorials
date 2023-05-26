---
title: Insert Ole Object As Icon Using Stream
linktitle: Insert Ole Object As Icon Using Stream
second_title: Aspose.Words for .NET API Reference
description: Learn how to insert an OLE object as an icon using a stream with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-oleobjects-and-activex/insert-ole-object-as-icon-using-stream/
---

Here is a step by step guide to explain the C# source code below that illustrates how to insert an OLE object as an icon using a stream with Aspose.Words for .NET.

## Step 1: Import the necessary references
Before you begin, make sure you have imported the necessary references to use Aspose.Words for .NET into your project. This includes importing the Aspose.Words library and adding the required namespaces to your source file.

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

## Step 2: Create a new document and document generator
In this step, we will create a new document using the `Document` class and a document builder using the `DocumentBuilder` class.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 3: Insert an OLE object as an icon from a stream
Use the Document Builder's `InsertOleObjectAsIcon` method to insert an OLE object as an icon from a stream into the document. Specify the data stream, object type, icon path, and embedded object name.

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

## Step 4: Save the document
Use the document's `Save` method to save the document to a file.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

### Example source code for inserting an OLE object as an icon using a stream with Aspose.Words for .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
     builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

This is a complete code sample for inserting an OLE object as an icon using a stream with Aspose.Words for .NET. Be sure to import the necessary references and follow the steps previously described to integrate this code into your project.
