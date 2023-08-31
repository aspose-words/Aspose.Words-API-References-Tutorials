---
title: Detect Document File Format
linktitle: Detect Document File Format
second_title: Aspose.Words Document Processing API
description: Step by step guide to detect document file format with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-fileformat/detect-file-format/
---

This article provides a step by step guide on how to use the document file format detection feature with Aspose.Words for .NET. We will explain each part of the code in detail. At the end of this tutorial, you will be able to understand how to detect the format of different document files.

Before you start, make sure you have installed and configured the Aspose.Words for .NET library in your project. You can find the library and installation instructions on the Aspose website.

## Step 1: Define directories

To start, you need to define the directories where you want to store the files according to their format. Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to your documents directory. We create the "Supported", "Unknown", "Encrypted" and "Pre97" directories if they do not already exist.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string supportedDir = dataDir + "Supported";
string unknownDir = dataDir + "Unknown";
string encryptedDir = dataDir + "Encrypted";
string pre97Dir = dataDir + "Pre97";

// Create the directories if they don't already exist.
if (Directory.Exists(supportedDir) == false)
Directory.CreateDirectory(supportedDir);
if (Directory.Exists(unknownDir) == false)
Directory.CreateDirectory(unknownDir);
if (Directory.Exists(encryptedDir) == false)
Directory.CreateDirectory(encryptedDir);
if (Directory.Exists(pre97Dir) == false)
Directory.CreateDirectory(pre97Dir);
```

## Step 2: Browse Files

Then we use the `GetFiles` method of the `Directory` class to get the list of files in the specified directory. We also use a `Where` clause to exclude a specific file named "Corrupted document.docx".

```csharp
IEnumerable<string> fileList = Directory.GetFiles(MyDir).Where(name => !name.EndsWith("Corrupted document.docx"));
```

## Step 3: Detect the format of each file

We loop through each file in the list and use the `DetectFileFormat` method of the `FileFormatUtil` class to detect the format of the file. We also display the detected document type.

```csharp
foreach (string fileName in fileList)
{
string nameOnly = Path. GetFileName(fileName);
Console.Write(nameOnly);

FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

// Display the document type
switch (info.LoadFormat)
{
LoadFormat.Doc box:
Console.WriteLine("\tDocument Microsoft Word 97-2003.");
break;
LoadFormat.Dot box:
Console.WriteLine("\tMicrosoft Word 97-2003 template.");
break;
LoadFormat.Docx box:
Console.WriteLine("\tDocument Office Open XML WordprocessingML without macros.");
break;
// ... Add cases for other supported document formats
LoadFormat.Unknown case:
Console.WriteLine("\tFormat in

known.");
break;
}

if (info.IsEncrypted)
{
Console.WriteLine("\tAn encrypted document.");
File.Copy(fileName, Path.Combine(encryptedDir, nameOnly), true);
}
else
{
switch (info.LoadFormat)
{
LoadFormat.DocPreWord60 box:
File.Copy(fileName, Path.Combine(pre97Dir, nameOnly), true);
break;
LoadFormat.Unknown case:
File.Copy(fileName, Path.Combine(unknownDir, nameOnly), true);
break;
default:
File.Copy(fileName, Path.Combine(supportedDir, nameOnly), true);
break;
}
}
}
```

That's all ! You have successfully detected the format of different document files using Aspose.Words for .NET.

### Example source code for file format detection with Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	string supportedDir = dataDir + "Supported";
	string unknownDir = dataDir + "Unknown";
	string encryptedDir = dataDir + "Encrypted";
	string pre97Dir = dataDir + "Pre97";

	// Create the directories if they do not already exist.
	if (Directory.Exists(supportedDir) == false)
		Directory.CreateDirectory(supportedDir);
	if (Directory.Exists(unknownDir) == false)
		Directory.CreateDirectory(unknownDir);
	if (Directory.Exists(encryptedDir) == false)
		Directory.CreateDirectory(encryptedDir);
	if (Directory.Exists(pre97Dir) == false)
		Directory.CreateDirectory(pre97Dir);

	
	IEnumerable<string> fileList = Directory.GetFiles(MyDir).Where(name => !name.EndsWith("Corrupted document.docx"));
	
	foreach (string fileName in fileList)
	{
		string nameOnly = Path.GetFileName(fileName);
		
		Console.Write(nameOnly);
		
		FileFormatInfo info = FileFormatUtil.DetectFileFormat(fileName);

		// Display the document type
		switch (info.LoadFormat)
		{
			case LoadFormat.Doc:
				Console.WriteLine("\tMicrosoft Word 97-2003 document.");
				break;
			case LoadFormat.Dot:
				Console.WriteLine("\tMicrosoft Word 97-2003 template.");
				break;
			case LoadFormat.Docx:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Free Document.");
				break;
			case LoadFormat.Docm:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Enabled Document.");
				break;
			case LoadFormat.Dotx:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Free Template.");
				break;
			case LoadFormat.Dotm:
				Console.WriteLine("\tOffice Open XML WordprocessingML Macro-Enabled Template.");
				break;
			case LoadFormat.FlatOpc:
				Console.WriteLine("\tFlat OPC document.");
				break;
			case LoadFormat.Rtf:
				Console.WriteLine("\tRTF format.");
				break;
			case LoadFormat.WordML:
				Console.WriteLine("\tMicrosoft Word 2003 WordprocessingML format.");
				break;
			case LoadFormat.Html:
				Console.WriteLine("\tHTML format.");
				break;
			case LoadFormat.Mhtml:
				Console.WriteLine("\tMHTML (Web archive) format.");
				break;
			case LoadFormat.Odt:
				Console.WriteLine("\tOpenDocument Text.");
				break;
			case LoadFormat.Ott:
				Console.WriteLine("\tOpenDocument Text Template.");
				break;
			case LoadFormat.DocPreWord60:
				Console.WriteLine("\tMS Word 6 or Word 95 format.");
				break;
			case LoadFormat.Unknown:
				Console.WriteLine("\tUnknown format.");
				break;
		}
		

		if (info.IsEncrypted)
		{
			Console.WriteLine("\tAn encrypted document.");
			File.Copy(fileName, Path.Combine(encryptedDir, nameOnly), true);
		}
		else
		{
			switch (info.LoadFormat)
			{
				case LoadFormat.DocPreWord60:
					File.Copy(fileName, Path.Combine(pre97Dir, nameOnly), true);
					break;
				case LoadFormat.Unknown:
					File.Copy(fileName, Path.Combine(unknownDir, nameOnly), true);
					break;
				default:
					File.Copy(fileName, Path.Combine(supportedDir, nameOnly), true);
					break;
			}
		}
	}
	

```

### FAQ for Document file format detection

#### How to detect the format of a document file using Aspose.Words for .NET?

To detect the format of a document file using Aspose.Words for .NET, you can follow the steps provided in the tutorial. Using the `DetectFileFormat` method of the `FileFormatUtil` class will allow you to detect the format of the document file. This will allow you to determine whether it is a Microsoft Word 97-2003 document, a template, an Office Open XML WordprocessingML document, or other supported formats. The code provided in the tutorial will walk you through implementing this feature.

#### What document formats does Aspose.Words for .NET support?

Aspose.Words for .NET supports a variety of document formats including Microsoft Word 97-2003 documents (DOC), Templates (DOT), Office Open XML WordprocessingML documents (DOCX), Office Open XML WordprocessingML documents with macros (DOCM), Office Open XML WordprocessingML templates without macros (DOTX), Office Open XML WordprocessingML templates with macros (DOTM), Flat OPC documents, RTF documents, Microsoft Word 2003 WordprocessingML documents, HTML documents, MHTML (Web archive) documents, OpenDocument Text (ODT) documents, OpenDocument Text (OTT) templates, MS Word 6 or Word 95 documents, and unknown document formats.

#### How to handle encrypted document files during format detection?

When detecting the format of a document file, you can use the `IsEncrypted` property of the `FileFormatInfo` object to check if the file is encrypted. If the file is encrypted, you can take additional steps to handle this specific case, such as copying the file to a directory dedicated to encrypted documents. You can use the `File.Copy` method to do this.

#### What actions should be taken when the format of a document is unknown?

When the format of a document is unknown, you can decide to handle it in a way specific to your application. In the example provided in the tutorial, the document is copied into a specific directory dedicated to documents of unknown format. You can customize this action to suit your specific needs.

#### Are there any other features of Aspose.Words for .NET that can be used in conjunction with document format detection?

Yes, Aspose.Words for .NET offers many other features for processing and manipulating Word documents. For example, you can use the library to extract text, images, or metadata from documents, apply formatting changes, merge documents, convert documents to different formats, and more.