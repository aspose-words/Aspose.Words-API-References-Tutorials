---
title: Insert Ole Object As Icon Using Stream
linktitle: Insert Ole Object As Icon Using Stream
second_title: Aspose.Words Document Processing API
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

## Conclusion

The step-by-step guide above explains how to insert an OLE object as an icon in a Word document using a flow with Aspose.Words for .NET. By following the steps described, you will be able to integrate this functionality into your project. Be sure to import the necessary references, create a new document and document generator, insert the OLE object as an icon from the stream, then save the document. Use the sample code provided as a starting point and customize it to your needs.

### FAQ's

#### Q. How to import the necessary references to use Aspose.Words for .NET?

A. To import the necessary references, you must follow these steps:

Add the following `using` statements at the top of your source file:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```
Make sure you have added the Aspose.Words library to your project.

#### Q. How to create a new document and document builder using Aspose.Words for .NET?

A. To create a new document and document generator, you can follow these steps:

Use the `Document` class to create a new document:

```csharp
Document doc = new Document();
```
Use the `DocumentBuilder` class to create a document builder associated with the previously created document:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### Q. How to insert an OLE object as an icon from a stream using Aspose.Words for .NET?

A. To insert an OLE object as an icon from a stream, you can follow these steps:

Use the `InsertOleObjectAsIcon` method of the document generator to insert the OLE object:

```csharp
using (MemoryStream stream = new MemoryStream(File.ReadAllBytes(MyDir + "Presentation.pptx")))
{
  builder.InsertOleObjectAsIcon(stream, "Package", ImagesDir + "Logo icon.ico", "My embedded file");
}
```

#### Q. How to save the document in a file?

A. To save the document to a file, you can use the `Save` method of the document specifying the destination path:

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectAsIconUsingStream.docx");
```

#### Q. How do I embed the code for inserting an OLE object as an icon from a stream into my project?

A. To embed the code for inserting an OLE object as an icon from a stream into your project, follow these steps:
- Import the necessary references by adding the appropriate `using` statements.
- Create a new document and a document builder using the `Document` and `DocumentBuilder` classes.
- Use the code for inserting the OLE object as an icon from a stream.
- Save the document using the `Save` method with the appropriate destination path.

By following these steps, you will be able to successfully insert an OLE object as an icon from a stream using Aspose.Words for .NET. Be sure to follow the instructions and import the necessary references to get the desired results.
