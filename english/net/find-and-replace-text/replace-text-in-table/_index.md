---
title: Replace Text In Table
linktitle: Replace Text In Table
second_title: Aspose.Words Document Processing API
description: Learn how to replace text in a table in a Word document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/find-and-replace-text/replace-text-in-table/
---

In this article, we will explore the above C# source code to understand how to use Replace Text In Table function in Aspose.Words for .NET library. This feature allows you to find and replace specific text inside a table in a Word document.

## Prerequisites

- Basic knowledge of the C# language.
- .NET development environment with Aspose.Words library installed.

## Step 1: Load the document

Before we start using text replacement in a table, we need to load the document into Aspose.Words for .NET. This can be done using the `Document` class and specifying the document file path:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Tables.docx");
```

## Step 2: Access the board

Once the document is loaded, we need to navigate to the table where we want to perform the text replacement. In our example, we use the `GetChild` method with the `NodeType.Table` parameter to get the first table in the document:

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## Step 3: Perform Text Replacement

Now we use the `Range.Replace` method to perform the text replacement in the array. In our example, we replace all occurrences of the word "Carrots" with "Eggs" using the `FindReplaceOptions` option with the `FindReplaceDirection.Forward` search direction. Additionally, we replace the value "50" with "20" in the last cell of the last row of the table:

```csharp
table.Range.Replace("Carrots", "Eggs", new FindReplaceOptions(FindReplaceDirection.Forward));
table.LastRow.LastCell.Range.Replace("50", "20", new FindReplaceOptions(FindReplaceDirection.Forward));
```

## Step 4: Save the edited document

Finally, we save the modified document to a specified directory using the `Save` method:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextInTable.docx");
```

Aspose.Words for .NET We followed a step-by-step guide to load a document, access the table, perform the text replacement and save the modified document.

### Example source code for Replace Text In Table using Aspose.Words for .NET

Here is the full sample source code to demonstrate using text replacement in a table with Aspose.Words for .NET:

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Tables.docx");

	Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

	table.Range.Replace("Carrots", "Eggs", new FindReplaceOptions(FindReplaceDirection.Forward));
	table.LastRow.LastCell.Range.Replace("50", "20", new FindReplaceOptions(FindReplaceDirection.Forward));

	doc.Save(dataDir + "FindAndReplace.ReplaceTextInTable.docx");
    
```

## Conclusion

In this article, we explored the C# source code to understand how to use Aspose's Replace Text In Table function.

