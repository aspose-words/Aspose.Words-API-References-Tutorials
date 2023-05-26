---
title: By Page Range
linktitle: By Page Range
second_title: Aspose.Words for .NET API Reference
description: Easily extract by page range from a Word document using Aspose.Words for .NET Step-by-step guide.
type: docs
weight: 10
url: /net/split-document/by-page-range/
---

## Introduction
In this tutorial, we will guide you step by step to understand and use the "By Page Range" functionality of Aspose.Words for .NET. This feature allows you to extract a specific part of a large Word document using a given page range. We will provide you with complete source code and Markdown output formats to make it easier for you to understand and use later.

## Requirements
Before you begin, make sure you have the following in place:

1. Aspose.Words for .NET installed on your development machine.
2. A large Word file from which you want to extract a specific part.

Now that we've covered the requirements, we can move on to the steps for using the By Page Range feature.

## Step 1: Document initialization and loading
Once you have set up your development environment, you need to initialize and load the Word document from which you want to extract a specific part. Here is the code to use:

```csharp
// The path to the documents directory.
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document doc = new Document(dataDir + "Name_of_large_document.docx");
```

Be sure to replace "YOUR_DOCUMENTS_DIRECTORY" with the actual path to your documents directory and "Name_of_large_document.docx" with the name of your large Word file.

## Step 2: Extracting the part of the document
Now that we have loaded the document, we can extract the specific part using the `ExtractPages` function with the desired page range. Here's how to do it:

```csharp
Document extractedPages = doc.ExtractPages(3, 6);
```

In this example, we extract pages 3-6 from the original document. You can adjust the page numbers according to your needs.

## Step 3: Save the extracted part
Once we have extracted the desired pages, we can save them in a new Word document. Here's how:

```csharp
extractedPages.Save(dataDir + "Document_Extraits.ParRangeDePages.docx");
```

Be sure to replace "Document_Extraits.ParPlageDePages.docx" with the desired name for your output file.

### Example source code for By Page Range using Aspose.Words for .NET

```csharp

            // The path to the documents directory.
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            Document doc = new Document(MyDir + "Big document.docx");
            
            // Get part of the document.
            Document extractedPages = doc.ExtractPages(3, 6);
            extractedPages.Save(dataDir + "SplitDocument.ByPageRange.docx");
            
        
```

## Conclusion
Congratulation ! You have learned how to use the "By Page Range" from Aspose.Words for .NET. Now you can easily extract specific parts of a large Word document using a given page range. Feel free to experiment more with Aspose's other powerful features. .Words to meet your specific needs.


