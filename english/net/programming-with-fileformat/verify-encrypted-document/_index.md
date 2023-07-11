---
title: Verify Encrypted Word Document
linktitle: Verify Encrypted Word Document
second_title: Aspose.Words Document Processing API
description: Step-by-step guide to verify a word document is encrypted with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-fileformat/verify-encrypted-document/
---

This article provides a step-by-step guide on how to use the Encrypted Word Document Verification feature with Aspose.Words for .NET. We will explain each part of the code in detail. At the end of this tutorial, you will be able to understand how to check if a document is encrypted.

Before you start, make sure you have installed and configured the Aspose.Words for .NET library in your project. You can find the library and installation instructions on the Aspose website.

## Step 1: Define the document directory

To start, you need to define the path to the directory where your documents are located. Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your documents directory.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Detect file format

Next, we use the `DetectFileFormat` method of the `FileFormatUtil` class to detect the file format information. In this example, we assume that the encrypted document is called "Encrypted.docx" and is located in the specified documents directory.

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
```

## Step 3: Check if the document is encrypted

We use the `IsEncrypted` property of the `FileFormatInfo` object to check if the document is encrypted. This property returns `true` if the document is encrypted, otherwise it returns `false`. We display the result in the console.

```csharp
Console.WriteLine(info.IsEncrypted);
```

That's all ! You have successfully checked if a document is encrypted using Aspose.Words for .NET.

### Example source code for verifying encrypted documents with Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
	Console.WriteLine(info.IsEncrypted);
            
        
```

## Frequently Asked Questions

### Q: What are the steps to verify an encrypted Word document?

The steps to verify an encrypted Word document are as follows:

Define the document directory.

Detect the file format.

Check if the document is encrypted.

### Q: How can I set the document directory?
To set the documents directory, you need to replace `"YOUR DOCUMENT DIRECTORY"` with the actual path of your documents directory in the following code:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

### Q: How to detect file format?
You can use the `DetectFileFormat` method of the `FileFormatUtil` class to detect file format information. In the following example, we assume that the encrypted document is called "Encrypted.docx" and is located in the specified documents directory:

```csharp
FileFormatInfo info = FileFormatUtil.DetectFileFormat(dataDir + "Encrypted.docx");
```

### Q: How to check if the document is encrypted?
You can use the `IsEncrypted` property of the `FileFormatInfo` object to check if the document is encrypted. This property returns `true` if the document is encrypted, otherwise it returns `false`. The result is displayed in the console:

```csharp
Console.WriteLine(info.IsEncrypted);
```

### Q: How to check if a document is encrypted using Aspose.Words for .NET?
By following the steps mentioned in this tutorial and running the provided source code, you can check if a document is encrypted using Aspose.Words for .NET.

