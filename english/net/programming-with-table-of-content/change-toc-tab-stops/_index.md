---
title: Change Toc Tab Stops
linktitle: Change Toc Tab Stops
second_title: Aspose.Words Document Processing API
description: Learn how to change table of contents tabs in a Word document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-table-of-content/change-toc-tab-stops/
---
Aspose.Words for .NET is a powerful library for creating, editing, and manipulating Word documents in a C# application. Among the functionalities offered by Aspose.Words, there is the possibility of modifying the tabs used in a table of contents of a Word document. In this guide, we'll show you how to use the C# source code of Aspose.Words for .NET to change tabs in a document's table of contents.

## Understanding the Aspose.Words library

Before diving into the code, it's important to understand the Aspose.Words library for .NET. Aspose.Words is a popular library that makes working with Word documents easy and efficient. It offers a wide range of features for creating, editing, and manipulating Word documents, including changing table of contents tabs.

## Loading the document containing the table of contents

The first step is to load the Word document containing the table of contents you want to modify. Use the Document class to load the document from the source file. Here is an example :

```csharp
Document doc = new Document(dataDir + "Table of contents.docx");
```

In this example, we load the document "Table of contents.docx" located in the documents directory.

## Changing tabs in the table of contents

Once the document is loaded, we go through each paragraph of the document and check if it is formatted using the Table of Contents (TOC) result styles. If so, we modify the tabs used to align the page numbers. Here's how:

```csharp
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
         para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
     {
         TabStop tab = para.ParagraphFormat.TabStops[0];
         para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
         para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
     }
}
```

In this example, we're using a loop to loop through each paragraph in the document. We then check if the paragraph is formatted using the Table of Contents Result (TOC) styles. If so, we access the first tab used in this paragraph and modify it by removing the old tab and adding a new tab with a modified position.

## Save modified document

Once you have made the necessary changes to the tabs in the table of contents, you can save the modified document using the Save method of the Document class. Here is an example :

```csharp
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

In this example, we save the modified document as "WorkingWithTableOfContent.ChangeTocTabStops.docx".

### Sample source code for "Edit Table of Contents Tabs" feature with Aspose.Words for .NET

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Load the document containing the table of contents
Document doc = new Document(dataDir + "Table of contents.docx");

// Modify the tabs of the table of contents
foreach(Paragraph para in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (para.ParagraphFormat.Style.StyleIdentifier >= StyleIdentifier.Toc1 &&
         para.ParagraphFormat.Style.StyleIdentifier <= StyleIdentifier.Toc9)
     {
         TabStop tab = para.ParagraphFormat.TabStops[0];
         para.ParagraphFormat.TabStops.RemoveByPosition(tab.Position);
         para.ParagraphFormat.TabStops.Add(tab.Position - 50, tab.Alignment, tab.Leader);
     }
}

// Save the modified document
doc.Save(dataDir + "WorkingWithTableOfContent.ChangeTocTabStops.docx");
```

## Conclusion

In this guide, we have covered how to use Aspose.Words for .NET to change the tabs in the table of contents of a Word document using the provided C# source code. By following the steps provided, you can easily customize the table of contents tabs in your Word documents in your C# application. Aspose.Words offers tremendous flexibility and power to work with the styles and formatting of your documents, allowing you to create attractive and professional Word documents.
