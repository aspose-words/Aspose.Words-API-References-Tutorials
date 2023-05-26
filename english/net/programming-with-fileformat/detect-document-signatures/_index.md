---
title: Detect Document Signatures
linktitle: Detect Document Signatures
second_title: Aspose.Words for .NET API Reference
description: Step-by-step guide to detect digital signatures in a document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-fileformat/detect-document-signatures/
---

This article provides a step by step guide on how to use the document signature detection feature with Aspose.Words for .NET. We will explain each part of the code in detail. At the end of this tutorial, you will be able to understand how to detect digital signatures in a document.

Before you start, make sure you have installed and configured the Aspose.Words for .NET library in your project. You can find the library and installation instructions on the Aspose website.

## Step 1: Define the document directory

To start, you need to define the path to the directory where your documents are located. Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your documents directory.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Detect digital signatures

Next, we use the `DetectFileFormat` method of the `FileFormatUtil` class to detect the file format information. In this example, we assume the document is called "Digitally signed.docx" and is located in the specified documents directory.

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Digitally signed.docx");
```

## Step 3: Check for digital signatures

We check if the document contains digital signatures using the `HasDigitalSignature` property of the `FileFormatInfo` object. If digital signatures are detected, we display a message indicating that the signatures will be lost if the document is opened/saved with Aspose.Words.

```csharp
if (info.HasDigitalSignature)
{
	Console.WriteLine(
		$"Document {Path.GetFileName(dataDir + "Digitally signed.docx")} has digital signatures, " +
		"they will be lost if you open/save this document with Aspose.Words.");
}
```

That's all ! You have successfully detected digital signatures in a document using Aspose.Words for .NET.

### Example source code for detecting document signatures with Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Digitally signed.docx");

	if (info.HasDigitalSignature)
	{
		Console.WriteLine(
			$"Document {Path.GetFileName(dataDir + "Digitally signed.docx")} has digital signatures, " +
			"they will be lost if you open/save this document with Aspose.Words.");
	}
	
        
```

