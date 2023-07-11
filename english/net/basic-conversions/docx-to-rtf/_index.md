---
title: Convert Docx To Rtf
linktitle: Convert Docx To Rtf
second_title: Aspose.Words Document Processing API
description: Learn how to convert Word documents from Docx to RTF format using Aspose.Words for .NET. Step-by-step tutorial with example source code.
type: docs
weight: 10
url: /net/basic-conversions/docx-to-rtf/
---

In this step-by-step tutorial, we will guide you on how to use Aspose.Words for .NET to convert a Word document in Docx format to RTF. We will explain the provided C# source code and show you how to implement it in your own projects.

To get started, ensure that you have Aspose.Words for .NET installed and set up in your development environment. If you haven't done so, download and install the library from the official website.

## Step 1: Reading the Document from Stream

First, open a stream to read the Docx document:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Stream stream = File.OpenRead(MyDir + "Document.docx");
```

## Step 2: Loading the Document

Next, load the document from the stream:

```csharp
Document doc = new Document(stream);
```

## Step 3: Closing the Stream

Since the document is loaded into memory, you can close the stream:

```csharp
stream.Close();
```

## Step 4: Performing Operations on the Document

At this point, you can perform any desired operations on the document.

## Step 5: Saving the Document in RTF Format

To save the document in RTF format, save it to a memory stream:

```csharp
MemoryStream dstStream = new MemoryStream();
doc.Save(dstStream, SaveFormat.Rtf);
```

## Step 6: Rewinding the Stream

Before writing the memory stream to a file, rewind its position back to zero:

```csharp
dstStream.Position = 0;
```

## Step 7: Writing the Stream to File

Finally, write the memory stream to an RTF file:

```csharp
File.WriteAllBytes(dataDir + "BaseConversions.DocxToRtf.rtf", dstStream.ToArray());
```

That's it! You have successfully converted a Word document in Docx format to RTF using Aspose.Words for .NET.

### Example source code for Docx To Rtf using Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Read only access is enough for Aspose.Words to load a document.
	Stream stream = File.OpenRead(MyDir + "Document.docx");

	Document doc = new Document(stream);
	// You can close the stream now, it is no longer needed because the document is in memory.
	stream.Close();

	// ... do something with the document.

	// Convert the document to a different format and save to stream.
	MemoryStream dstStream = new MemoryStream();
	doc.Save(dstStream, SaveFormat.Rtf);

	// Rewind the stream position back to zero so it is ready for the next reader.
	dstStream.Position = 0;

	File.WriteAllBytes(dataDir + "BaseConversions.DocxToRtf.rtf", dstStream.ToArray());
	
```

Feel free to use this code in your own projects and modify it according to your specific requirements.

### FAQs

#### How can I convert a DOCX file to RTF format?

To convert a DOCX file to RTF format, you can use various software tools or libraries that provide this functionality. One such reliable tool is Aspose.Words for .NET. It offers a simple and efficient way to convert DOCX files to RTF format programmatically. You can use the library's API to load the DOCX file and save it in the desired RTF format.

#### Are there any limitations to the conversion process?

The limitations of the conversion process depend on the specific tool or library you are using. Some tools may have restrictions on the size or complexity of the input document. It's important to choose a tool that can handle the requirements of your conversion task.

#### Can I preserve the formatting and layout of the original document?

Yes, with the Aspose.Words, you can preserve the formatting and layout of the original document during the conversion process. Aspose.Words for .NET, for example, provides comprehensive support for maintaining the formatting, styles, and other elements of the DOCX file in the converted RTF document.

#### Is Aspose a reliable tool for DOCX to RTF conversion?

Yes, Aspose.Words for .NET is a highly reliable tool for DOCX to RTF conversion. It is widely used by developers and businesses worldwide for its robust features and excellent performance. The library offers extensive documentation, regular updates, and dedicated technical support, making it a trusted choice for document conversion tasks.
