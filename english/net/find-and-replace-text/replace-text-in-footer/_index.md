---
title: Replace Text In Footer
linktitle: Replace Text In Footer
second_title: Aspose.Words for .NET API Reference
description: Learn how to replace text in the footer of Word documents using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/find-and-replace-text/replace-text-in-footer/
---

In this article, we will explore the above C# source code to understand how to use Replace Text In Footer function in Aspose.Words for .NET library. This feature allows you to find and replace specific text in the footers of Word documents.

## Prerequisites

- Basic knowledge of the C# language.
- .NET development environment with Aspose.Words library installed.

## Step 1: Load the document

Before we start using text replacement in the footer, we need to load the document into Aspose.Words for .NET. This can be done using the `Document` class and specifying the document file path:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Footer.docx");
```

## Step 2: Access the footer

Once the document is loaded, we need to access the footer to perform the text replacement. In our example, we use the `HeadersFooters` property of the first section of the document to get the collection of headers/footers. Next, we select the main footer using the `HeaderFooterType.FooterPrimary` index:

```csharp
HeaderFooterCollection headersFooters = doc.FirstSection.HeadersFooters;
HeaderFooter footer = headersFooters[HeaderFooterType.FooterPrimary];
```

## Step 3: Configure search and replace options

Now we will configure find and replace options using a `FindReplaceOptions` object. In our example, we set `MatchCase` to `false` to ignore case when searching, and `FindWholeWordsOnly` to `false` to allow parts of words to be searched and replaced:

```csharp
FindReplaceOptions options = new FindReplaceOptions { MatchCase = false, FindWholeWordsOnly = false };
```

## Step 4: Replace text in footer

We use the `Range.Replace` method to perform text replacement in the footer. In our example, we replace the phrase "(C) 2006 Aspose Pty Ltd." by "Copyright (C) 2020 by Aspose Pty Ltd." :

```csharp
footer

.Range.Replace("(C) 2006 Aspose Pty Ltd.", "Copyright (C) 2020 by Aspose Pty Ltd.", options);
```

## Step 5: Save the edited document

Finally, we save the modified document to a specified directory using the `Save` method:

```csharp
doc.Save(dataDir + "FindAndReplace.ReplaceTextInFooter.docx");
```

### Example source code for Replace Text In Footer using Aspose.Words for .NET

Here is the full sample source code to demonstrate the use of footer text replacement with Aspose.Words for .NET:

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Footer.docx");

	HeaderFooterCollection headersFooters = doc.FirstSection.HeadersFooters;
	HeaderFooter footer = headersFooters[HeaderFooterType.FooterPrimary];

	FindReplaceOptions options = new FindReplaceOptions { MatchCase = false, FindWholeWordsOnly = false };

	footer.Range.Replace("(C) 2006 Aspose Pty Ltd.", "Copyright (C) 2020 by Aspose Pty Ltd.", options);

	doc.Save(dataDir + "FindAndReplace.ReplaceTextInFooter.docx");
            
        
```

## Conclusion

In this article, we explored the C# source code to understand how to use the Replace Text In Footer function of Aspose.Words for .NET. We followed a step-by-step guide to load a document, access the footer, configure search and replace options, perform text replacement, and save the edited document.

