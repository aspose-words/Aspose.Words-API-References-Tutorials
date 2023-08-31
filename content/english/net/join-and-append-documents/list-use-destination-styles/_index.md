---
title: List Use Destination Styles
linktitle: List Use Destination Styles
second_title: Aspose.Words Document Processing API
description: Learn how to join and append Word documents while preserving destination document's list styles using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/join-and-append-documents/list-use-destination-styles/
---

This tutorial will guide you through the process of using the List Use Destination Styles feature of Aspose.Words for .NET. This feature allows you to join and append Word documents while using the list styles of the destination document.

## Prerequisites

Before you begin, make sure you have the following:

1. Aspose.Words for .NET installed. You can download it from the Aspose website or install it via NuGet.
2. Visual Studio or any other C# development environment.

## Step 1: Initialize the Document Directories

First, you need to set the path to your document directory. Modify the value of the `dataDir` variable to the path where your documents are located.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Load the Source and Destination Documents

Next, you need to load the source and destination documents using the Aspose.Words `Document` class. Update the file names in the `Document` constructor according to your document names.

```csharp
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Step 3: Set the Source Document to Continue after the Destination Document

To ensure that the content from the source document continues after the end of the destination document, you need to set the `SectionStart` property of the first section in the source document to `SectionStart.Continuous`.

```csharp
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Step 4: Handle List Formatting

To handle list formatting, you will iterate through each paragraph in the source document and check if it is a list item. If it is, you will compare the list ID with the existing lists in the destination document. If a list with the same ID exists, you will create a copy of the list in the source document and update the paragraph's list format to use the copied list.

```csharp
Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();

foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    if (para.IsListItem)
    {
        int listId = para.ListFormat.List.ListId;
        if (dstDoc.Lists.GetListByListId(listId) != null)
        {
            Aspose.Words.Lists.List currentList;
            if (newLists.ContainsKey(listId))
            {
                currentList = newLists[listId];
            }
            else
            {
                currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
                newLists.Add(listId, currentList);
            }
            para.ListFormat.List = currentList;
        }
    }
}
```

## Step 5: Append the Source Document to the Destination Document

Now, you can append the source document to the destination document using the `AppendDocument` method of the `Document` class. The `ImportFormatMode.UseDestinationStyles` parameter ensures that the destination document's list styles are used during the append operation.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
```

## Step 6: Save the Final Document

Finally, save the merged document with the List Use Destination Styles feature enabled using the `Save` method of the `Document` class.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

### Example source code for List Use Destination Styles using Aspose.Words for .NET 

Here's the full source code for the "List Use Destination Styles" feature in C# using Aspose.Words for .NET:


```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document srcDoc = new Document(dataDir + "Document source.docx");
	Document dstDoc = new Document(dataDir + "Document destination with list.docx");
	// Set the source document to continue straight after the end of the destination document.
	srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
	// Keep track of the lists that are created.
	Dictionary<int, Aspose.Words.Lists.List> newLists = new Dictionary<int, Aspose.Words.Lists.List>();
	foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
	{
		if (para.IsListItem)
		{
			int listId = para.ListFormat.List.ListId;
			// Check if the destination document contains a list with this ID already. If it does, then this may
			// cause the two lists to run together. Create a copy of the list in the source document instead.
			if (dstDoc.Lists.GetListByListId(listId) != null)
			{
				Aspose.Words.Lists.List currentList;
				// A newly copied list already exists for this ID, retrieve the stored list,
				// and use it on the current paragraph.
				if (newLists.ContainsKey(listId))
				{
					currentList = newLists[listId];
				}
				else
				{
					// Add a copy of this list to the document and store it for later reference.
					currentList = srcDoc.Lists.AddCopy(para.ListFormat.List);
					newLists.Add(listId, currentList);
				}
				// Set the list of this paragraph to the copied list.
				para.ListFormat.List = currentList;
			}
		}
	}
	// Append the source document to end of the destination document.
	dstDoc.AppendDocument(srcDoc, ImportFormatMode.UseDestinationStyles);
	dstDoc.Save(dataDir + "JoinAndAppendDocuments.ListUseDestinationStyles.docx");
```

That's it! You have successfully implemented the List Use Destination Styles feature using Aspose.Words for .NET. The final document will contain the merged content with the list styles from the destination document.