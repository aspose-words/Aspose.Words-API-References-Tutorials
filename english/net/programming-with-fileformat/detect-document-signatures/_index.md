---
title: Detect Digital Signature on Word Document
linktitle: Detect Digital Signature on Word Document
second_title: Aspose.Words Document Processing API
description: Step-by-step guide to detect digital signature on word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-fileformat/detect-document-signatures/
---

This article provides a step by step guide on how to use the Digital Signature on Word Document detection feature with Aspose.Words for .NET. We will explain each part of the code in detail. At the end of this tutorial, you will be able to understand how to detect digital signatures in a document.

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
## Conclusion

This tutorial has provided you a step by step guide on how to detect digital signature on word document using digital signature detection feature with Aspose.Words for .NET. Each part of the code has been explained in detail, allowing you to understand how to detect digital signatures in a document.

### FAQ for Detecting digital signature on Word document

#### How to detect the presence of a digital signature on a Word document using Aspose.Words for .NET?

To detect the presence of a digital signature on a Word document using Aspose.Words for .NET, you can follow the steps provided in the tutorial. Using the `DetectFileFormat` method of the `FileFormatUtil` class will allow you to detect file format information. Then you can check the `HasDigitalSignature` property of the `FileFormatInfo` object to determine if the document contains a digital signature. If a digital signature is detected, you can display a message stating that signatures will be lost if the document is opened/saved with Aspose.Words.

#### How to specify the directory containing the documents in which to search for the digital signature?

To specify the directory containing the documents in which you want to search for the digital signature, you must modify the `dataDir` variable in the code. Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your documents directory.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

#### What is the impact of opening/saving a document with Aspose.Words on digital signatures?

When you open or save a document with Aspose.Words, the digital signatures present in the document will be lost. This is due to changes made to the document while processing with Aspose.Words. If you need to preserve digital signatures, you should take this into account and use another method to manage documents containing digital signatures.

#### What other features of Aspose.Words for .NET can be used in conjunction with digital signature detection?

Aspose.Words for .NET offers a variety of features for processing and manipulating Word documents. In addition to detecting digital signatures, you can use the library to extract text, images, or metadata from documents, apply formatting changes, merge documents, convert documents to different formats, and much more . You can explore the official documentation of Aspose.Words for .NET to discover all the features available and find the ones that best suit your needs.

#### What are the limitations of detecting digital signatures with Aspose.Words for .NET?

Digital signature detection with Aspose.Words for .NET is limited to detecting the presence of signatures in a document. However, Aspose.Words does not provide functionality to verify the authenticity or integrity of digital signatures. To perform more advanced operations on digital signatures, you will need to use other specialized tools or libraries.
