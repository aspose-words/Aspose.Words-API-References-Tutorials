---
title: Insert Ole Object In Word With Ole Package
linktitle: Insert Ole Object In Word With Ole Package
second_title: Aspose.Words Document Processing API
description: Learn how to insert an OLE object with an OLE package into a document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-oleobjects-and-activex/insert-ole-object-with-ole-package/
---

Here is a step-by-step guide to explain the C# source code below that illustrates how to insert an OLE object in word with an OLE package using Aspose.Words for .NET.

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

## Step 3: Insert an OLE object with an OLE package
Use the Document Generator's `InsertOleObject` method to insert an OLE object with an OLE package into the document. Specify the data stream, object type, display options, and other necessary settings.

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}
```

## Step 4: Save the document
Use the document's `Save` method to save the document to a file.

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

### Sample source code for inserting an OLE object with an OLE package with Aspose.Words for .NET

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "Zip file.zip");
using (Stream stream = new MemoryStream(bs))
{
     Shape shape = builder.InsertOleObject(stream, "Package", true, null);
     OlePackage olePackage = shape.OleFormat.OlePackage;
     olePackage.FileName = "filename.zip";
     olePackage.DisplayName = "displayname.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

This is a complete code sample for inserting an OLE object with an OLE package with Aspose.Words for .NET. Be sure to import the necessary references and follow the steps previously described to integrate this code into your project.

## Conclusion

In conclusion, we have gone through a step-by-step guide to insert an OLE object into a Word document with an OLE package using Aspose.Words for .NET.

By following these steps, you will be able to successfully insert OLE objects with OLE packages into your Word documents using Aspose.Words for .NET. Be sure to import the necessary references and follow the instructions carefully to get the desired results.

### FAQ's for insert ole object in word with ole package

#### Q: What credentials do I need to import to use Aspose.Words for .NET?

A: To use Aspose.Words for .NET, you need to import the following references:

```csharp
using Aspose.Words;
using Aspose.Words.Drawing;
using System.IO;
```

#### Q: How to create a new document and a document generator?

A: You can create a new document using the `Document` class and a document builder using the `DocumentBuilder` class, as shown below:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

#### Q: How to insert an OLE object with an OLE package into the document?

A: Use the `InsertOleObject` method of the document builder (`DocumentBuilder`) to insert an OLE object with an OLE package into the document. Specify the data stream, object type, display options, and other necessary settings. Here is an example :

```csharp
byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}
```

#### Q: How to save the document?

A: Use the document `Save` method to save the document to a file. Here is an example :

```csharp
doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

#### Q: Can you provide a complete example of inserting an OLE object with an OLE package with Aspose.Words for .NET?

A: Here is a complete sample code to insert an OLE object with an OLE package using Aspose.Words for .NET. Be sure to import the necessary references and follow the steps previously described to integrate this code into your project:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

byte[] bs = File.ReadAllBytes(MyDir + "File_zip.zip");
using (Stream stream = new MemoryStream(bs))
{
      Shape shape = builder.InsertOleObject(stream, "Package", true, null);
      OlePackage olePackage = shape.OleFormat.OlePackage;
      olePackage.FileName = "file_name.zip";
      olePackage.DisplayName = "display_name.zip";
}

doc.Save("Path_to_your_directory/WorkingWithOleObjectsAndActiveX.InsertOleObjectWithOlePackage.docx");
```

This concludes our tutorial on inserting an OLE object with an OLE package into a Word document using Aspose.Words for .NET. Feel free to import the necessary references and follow the steps described to integrate this code into your project. If you have any further questions, please don't hesitate to contact us.
