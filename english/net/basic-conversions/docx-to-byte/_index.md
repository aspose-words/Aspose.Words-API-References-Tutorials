---
title: Docx To Byte
linktitle: Docx To Byte
second_title: Aspose.Words for .NET API Reference
description: Learn how to convert Word documents from Docx to byte array using Aspose.Words for .NET. Step-by-step tutorial with example source code.
type: docs
weight: 10
url: /net/basic-conversions/docx-to-byte/
---

In this step-by-step tutorial, we will guide you on how to use Aspose.Words for .NET to convert a Word document in Docx format to a byte array. We will explain the provided C# source code and show you how to implement it in your own projects.

To get started, ensure that you have Aspose.Words for .NET installed and set up in your development environment. If you haven't done so, download and install the library from the official website.

## Step 1: Initializing the MemoryStream

First, create an instance of the `MemoryStream` class to store the converted document as a byte array:

```csharp
MemoryStream outStream = new MemoryStream();
```

## Step 2: Saving the Document to MemoryStream

Next, use the `Save` method of the `Document` class to save the document to the `MemoryStream` in Docx format:

```csharp
doc.Save(outStream, SaveFormat.Docx);
```

## Step 3: Converting MemoryStream to Byte Array

To convert the `MemoryStream` containing the Docx document to a byte array, use the `ToArray` method:

```csharp
byte[] docBytes = outStream.ToArray();
```

## Step 4: Initializing the MemoryStream from Byte Array

Now, initialize a new instance of `MemoryStream` using the byte array obtained in the previous step:

```csharp
MemoryStream inStream = new MemoryStream(docBytes);
```

## Step 5: Creating Document from MemoryStream

Finally, create a new `Document` object from the `MemoryStream`:

```csharp
Document docFromBytes = new Document(inStream);
```

That's it! You have successfully converted a Word document in Docx format to a byte array using Aspose.Words for .NET.

### Example source code for Docx To Byte using Aspose.Words for .NET

```csharp

	// MemoryStream outStream = new MemoryStream();
	doc.Save(outStream, SaveFormat.Docx);

	byte[] docBytes = outStream.ToArray();
	MemoryStream inStream = new MemoryStream(docBytes);

	Document docFromBytes = new Document(inStream);
	
```

Feel free to use this code in your own projects and modify it according to your specific requirements.