---
title: Keep Source Together
linktitle: Keep Source Together
second_title: Aspose.Words Document Processing API
description: Learn how to merge Word documents using Aspose.Words for .NET while preserving formatting. This comprehensive guide covers everything from setup to execution.
type: docs
weight: 10
url: /net/join-and-append-documents/keep-source-together/
---
## Introduction

In today's digital age, manipulating Word documents programmatically is essential across various industries. Aspose.Words for .NET empowers developers to automate document handling tasks efficiently. This comprehensive guide will walk you through the process of merging documents while preserving source formatting using Aspose.Words for .NET.

## Prerequisites

Before diving into document merging with Aspose.Words for .NET, ensure you have the following:

- Visual Studio: Integrated Development Environment (IDE) for .NET development.
- Aspose.Words for .NET: Installed and set up in your development environment.
- Familiarity with C#: Basic understanding of C# programming language.

## Import Namespaces

To begin, import the necessary namespaces:

```csharp
using Aspose.Words;
using Aspose.Words.DocumentBuilder;
```

## Step 1: Load Documents

Firstly, load the source and destination documents into Aspose.Words `Document` objects.

```csharp
// Path to your document directory
string dataDir = "YOUR_DOCUMENT_DIRECTORY/";

// Load source and destination documents
Document srcDoc = new Document(dataDir + "Document source.docx");
Document dstDoc = new Document(dataDir + "Document destination with list.docx");
```

## Step 2: Set Section Start

Configure the section start to ensure the source document content flows continuously after the destination document.

```csharp
// Set the source document to appear straight after the destination document's content
srcDoc.FirstSection.PageSetup.SectionStart = SectionStart.Continuous;
```

## Step 3: Keep Paragraphs Together

To maintain the formatting integrity, mark each paragraph in the source document to stay with the next paragraph.

```csharp
foreach (Paragraph para in srcDoc.GetChildNodes(NodeType.Paragraph, true))
{
    para.ParagraphFormat.KeepWithNext = true;
}
```

## Step 4: Append Documents

Merge the documents using the `AppendDocument` method, ensuring to retain the source document's formatting.

```csharp
dstDoc.AppendDocument(srcDoc, ImportFormatMode.KeepSourceFormatting);
```

## Step 5: Save Merged Document

Finally, save the merged document to the desired location.

```csharp
dstDoc.Save(dataDir + "JoinAndAppendDocuments.KeepSourceTogether.docx");
```

## Conclusion

In conclusion, Aspose.Words for .NET simplifies the task of merging Word documents while preserving the original formatting seamlessly. This capability is crucial for applications requiring automated document processing.

## FAQ's

### Can Aspose.Words for .NET merge documents of different formats?
Yes, it can merge documents regardless of their format, maintaining source formatting.

### Does Aspose.Words for .NET support merging large documents efficiently?
Absolutely, it handles large documents with optimal performance.

### Is there a trial version available for Aspose.Words for .NET?
Yes, you can download a free trial [here](https://releases.aspose.com/).

### How can I get technical support for Aspose.Words for .NET?
Technical support is available through the [Aspose.Words forum](https://forum.aspose.com/c/words/8).

### Can I purchase a temporary license for Aspose.Words for .NET?
Yes, you can acquire a temporary license [here](https://purchase.aspose.com/temporary-license/).
