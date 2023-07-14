---
title: Replace Text In Footer
linktitle: Replace Text In Footer
second_title: Aspose.Words Document Processing API
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

### FAQ's

#### Q: What is the "Replace Text In Footer" feature in Aspose.Words for .NET?

A: The "Replace Text In Footer" feature in Aspose.Words for .NET allows you to find and replace specific text in the footers of Word documents. It enables you to modify the content of the footer by replacing a particular phrase, word, or pattern with the desired text.

#### Q: How can I load a Word document using Aspose.Words for .NET?

A: To load a Word document using Aspose.Words for .NET, you can use the `Document` class and specify the document file path. Here's an example of C# code to load a document:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Footer.docx");
```

#### Q: How can I access the footer of a document in Aspose.Words for .NET?

A: Once the document is loaded, you can access the footer to perform text replacement. In Aspose.Words for .NET, you can use the `HeadersFooters` property of the first section of the document to get the collection of headers/footers. Then, you can select the main footer using the `HeaderFooterType.FooterPrimary` index:

```csharp
HeaderFooterCollection headersFooters = doc.FirstSection.HeadersFooters;
HeaderFooter footer = headersFooters[HeaderFooterType.FooterPrimary];
```

#### Q: How can I configure search and replace options for text replacement in the footer using Aspose.Words for .NET?

A: To configure search and replace options for text replacement in the footer using Aspose.Words for .NET, you can create a `FindReplaceOptions` object and set the desired properties. For example, you can set `MatchCase` to `false` to ignore case when searching and `FindWholeWordsOnly` to `false` to allow parts of words to be searched and replaced:

```csharp
FindReplaceOptions options = new FindReplaceOptions { MatchCase = false, FindWholeWordsOnly = false };
```

#### Q: How can I perform text replacement in the footer using Aspose.Words for .NET?

A: To perform text replacement in the footer using Aspose.Words for .NET, you can use the `Range.Replace` method on the footer's range. This method allows you to specify the text to find and the replacement text. Here's an example:

```csharp
footer.Range.Replace("(C) 2006 Aspose Pty Ltd.", "Copyright (C) 2020 by Aspose Pty Ltd.", options);
```

#### Q: Can I perform text replacement in multiple footers of a document using Aspose.Words for .NET?

A: Yes, you can perform text replacement in multiple footers of a document using Aspose.Words for .NET. You can iterate over the `HeaderFooterCollection` and apply the text replacement on each footer individually. This allows you to replace specific text in all footers present in the document.

#### Q: What does the example source code demonstrate for the "Replace Text In Footer" feature in Aspose.Words for .NET?

A: The example source code demonstrates the use of the "Replace Text In Footer" feature in Aspose.Words for .NET. It shows how to load a document, access the footer, configure search and replace options, perform text replacement in the footer, and save the modified document.

#### Q: Are there any limitations or considerations when replacing text in footers using Aspose.Words for .NET?

A: When replacing text in footers using Aspose.Words for .NET, it's important to consider the formatting and layout of the footer. If the replacement text significantly differs in length or formatting, it may affect the appearance of the footer. Ensure that the replacement text aligns with the overall design and structure of the footer to maintain a consistent layout.

#### Q: Can I use regular expressions for text replacement in footers with Aspose.Words for .NET?

A: Yes, you can use regular expressions for text replacement in footers with Aspose.Words for .NET. By constructing a regular expression pattern, you can perform more advanced and flexible matching for replacing text in the footer. This allows you to handle complex search patterns and perform dynamic replacements based on captured groups or patterns.

#### Q: Can I replace text in other parts of the document besides footers using Aspose.Words for .NET?

A: Yes, you can replace text in other parts of the document besides footers using Aspose.Words for .NET. The `Range.Replace` method can be used to replace text in different document sections, headers, body, or any other desired location. Simply target the appropriate range or region within the document and perform the text replacement operation accordingly.
