---
title: Get Paragraph Style Separator
linktitle: Get Paragraph Style Separator
second_title: Aspose.Words Document Processing API
description: Learn how to get the paragraph style separator with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/document-formatting/get-paragraph-style-separator/
---

In this tutorial, we are going to walk you through how to use the Get Paragraph Style Separator feature with Aspose.Words for .NET. Follow the steps below to understand the source code and apply the changes.

## Step 1: Loading the document

To get started, specify the directory for your documents and load the document into a Document object. Here's how:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Document.docx");
```

## Step 2: Finding Paragraph Style Separators

We will now loop through all the paragraphs in the document and check if a paragraph is a style separator. Here's how:

```csharp
foreach(Paragraph paragraph in doc.GetChildNodes(NodeType.Paragraph, true))
{
     if (paragraph.BreakIsStyleSeparator)
     {
         Console.WriteLine("Separator found!");
     }
}
```

### Example source code for Get Paragraph Style Separator using Aspose.Words for .NET

Here is the complete source code for the Get Paragraph Style Separator feature with Aspose.Words for .NET:

```csharp

            Document doc = new Document(MyDir + "Document.docx");

            foreach (Paragraph paragraph in doc.GetChildNodes(NodeType.Paragraph, true))
            {
                if (paragraph.BreakIsStyleSeparator)
                {
                    Console.WriteLine("Separator Found!");
                }
            }
        
```

With this code you will be able to find the paragraph style separators in a document using Aspose.Words for .NET.


