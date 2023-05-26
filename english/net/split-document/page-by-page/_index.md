---
title: Page By Page
linktitle: Page By Page
second_title: Aspose.Words for .NET API Reference
description: Step-by-step guide to explain the C# source code of Aspose.Words Page by Page feature for .NET
type: docs
weight: 10
url: /net/split-document/page-by-page/
---

In this tutorial, we will walk you through how to split a Word document into individual pages using the Page by Page feature of Aspose.Words for .NET. Follow the steps below to understand the source code and get separate documents for each page.

## Step 1: Loading the document

To get started, specify the directory for your document and load the document into a Document object. Here's how:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Large document.docx");
```

## Step 2: Divide the document by page

Now we'll iterate through each page of the document and break the document into individual pages. Here's how:

```csharp
int pageCount = doc. PageCount;

for (int page = 0; page < pageCount; page++)
{
// Save each page as a separate document.
Document extractedPage = doc.ExtractPages(page, 1);
extractedPage.Save(dataDir + $"SplitDocument.PageParPage_{page + 1}.docx");
}
```

## Step 3: Merge documents

Once you have separate documents for each page, you can merge them if needed. Here's how:

```csharp
MergeDocuments();
```

### Example source code for Page By Page using Aspose.Words for .NET

Here is the complete source code for the Page by Page feature of Aspose.Words for .NET:

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Big document.docx");

	int pageCount = doc.PageCount;

	for (int page = 0; page < pageCount; page++)
	{
		// Save each page as a separate document.
		Document extractedPage = doc.ExtractPages(page, 1);
		extractedPage.Save(dataDir + $"SplitDocument.PageByPage_{page + 1}.docx");
	}
	

	MergeDocuments();

```

With this code you will be able to split a Word document into individual pages using Aspose.Words for .NET. You can also merge separate documents if needed.


