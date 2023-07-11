---
title: Change Style Of Toc Level
linktitle: Change Style Of Toc Level
second_title: Aspose.Words Document Processing API
description: Learn how to easily change the style of a table of contents level in a Word document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-table-of-content/change-style-of-toc-level/
---

Aspose.Words for .NET is a powerful library for creating, editing, and manipulating Word documents in a C# application. Among the features offered by Aspose.Words is the ability to change the style of a specific level of a document's table of contents. In this guide, we will show you how to use the C# source code of Aspose.Words for .NET to change the style of a level of the table of contents of a Word document.

## Understanding the Aspose.Words library

Before diving into the code, it's important to understand the Aspose.Words library for .NET. Aspose.Words is a popular library that makes working with Word documents easy and efficient. It offers a wide range of features for creating, editing and manipulating Word documents, including changing the style of the table of contents.

## Creating a new document

The first step is to create a new Word document where you want to change the table of contents style. Use the Document class to create a new document. Here is an example :

```csharp
Document doc = new Document();
```

In this example, we are creating a new empty document.

## Changing the style of a table of contents level

Once the document is created, you can access document styles and change the style used for a specific level of the table of contents. In this example, we will modify the style used for the first level of the table of contents. Here's how:

```csharp
doc.Styles[StyleIdentifier.Toc1].Font.Bold = true;
```

In this example, we use the Styles property of the Document class to access document styles. Next, we use the StyleIdentifier.Toc1 style identifier to access the style used for the first level of the table of contents. Finally, we modify the Font.Bold property of the style to make it bold.

## Save modified document

Once you have made the necessary modifications to the style of the table of contents, you can save the modified document using the Save method of the Document class. Here is an example :

```csharp
doc.Save(dataDir + "WorkingWithChangeStyleOfTocLevel.ModifiedDocument.docx");
```

In this example, we save the modified document as "WorkingWithChangeStyleOfTocLevel.ModifiedDocument.docx".

## Example source code for the "Change the style of a table of contents level" feature with Aspose.Words for .NET

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Create a new document
Document doc = new Document();

// Modification of the style of the first level of the table of contents
doc.Styles[StyleIdentifier.Toc1].Font.Bold = true;

// Save the modified document
doc.Save(dataDir + "WorkingWithChangeStyleOfTocLevel.ModifiedDocument.docx");
```

## Conclusion

In this guide, we explained how to use Aspose.Words for .NET to change the style of a level of the table of contents of a Word document using the provided C# source code. By following the steps provided, you can easily customize the style of the table of contents in your Word documents in your C# application. Aspose.Words offers tremendous flexibility and power to work with the styles and formatting of your documents, allowing you to create attractive and professional Word documents.
