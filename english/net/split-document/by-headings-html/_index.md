---
title: Split Word Document By Headings Html
linktitle: By Headings Html
second_title: Aspose.Words Document Processing API
description: Step-by-step guide to explain the C# source code of the split word document By Heading HTML feature of Aspose.Words for .NET
type: docs
weight: 10
url: /net/split-document/by-headings-html/
---
In this tutorial, we will walk you through how to split a Word document into smaller parts using the By HTML Heading feature of Aspose.Words for .NET. Follow the steps below to understand the source code and generate separate HTML documents based on Heading.

## Step 1: Loading the document

To get started, specify the directory for your document and load the document into a Document object. Here's how:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");
```

## Step 2: Dividing the document by Heading in HTML format

Now we will set save options to split the document into smaller parts based on Heading in HTML format. Here's how:

```csharp
HtmlSaveOptions options = new HtmlSaveOptions
{
// Split the document into smaller parts, in this case separating it by title.
DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};

doc.Save(dataDir + "SplitDocument.ParTitresHtml.html", options);
```

### Example source code for By Headings HTML using Aspose.Words for .NET

Here is the complete source code for the By HTML Heading feature of Aspose.Words for .NET:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(MyDir + "Rendering.docx");

HtmlSaveOptions options = new HtmlSaveOptions
{
	// Split a document into smaller parts, in this instance split by heading.
	DocumentSplitCriteria = DocumentSplitCriteria.HeadingParagraph
};


doc.Save(dataDir + "SplitDocument.ByHeadingsHtml.html", options);
```

With this code, you will be able to split a Word document into smaller parts using Aspose.Words for .NET, based on headings. You can then generate separate HTML documents for each part.

## Conclusion

In this tutorial, we learned how to split a Word document into smaller parts using the By HTML Heading feature of Aspose.Words for .NET. By specifying the `DocumentSplitCriteria` as `HeadingParagraph` in the `HtmlSaveOptions`, we were able to generate separate HTML documents based on the headings present in the original document.

Splitting a document by headings can be useful for organizing and managing content, especially in large documents with multiple sections. Aspose.Words for .NET provides a reliable and efficient solution for handling document splitting and generating output in various formats.

Feel free to explore additional features and options provided by Aspose.Words for .NET to further enhance your document processing capabilities and streamline your workflow.

### FAQs

#### How can I split a Word document into smaller parts based on headings using Aspose.Words for .NET?

To split a Word document based on headings, you can use the By HTML Heading feature of Aspose.Words for .NET. Follow the provided source code and set the `DocumentSplitCriteria` to `HeadingParagraph` in the `HtmlSaveOptions` object. This will split the document into smaller parts at each heading.

#### What formats can I split the Word document into?

The provided source code demonstrates splitting the Word document into smaller parts in HTML format. However, Aspose.Words for .NET supports various output formats, including DOCX, PDF, EPUB, and more. You can modify the code and specify the desired output format in the `HtmlSaveOptions` object accordingly.

#### Can I choose a different criteria for splitting the document?

Yes, you can choose a different criteria for splitting the document based on your requirements. Aspose.Words for .NET provides several criteria options, such as `HeadingParagraph`, `Page`, `Section`, and more. Modify the `DocumentSplitCriteria` property in the `HtmlSaveOptions` object to select the appropriate criteria for splitting.

#### How can I customize the output HTML for the split parts?

Aspose.Words for .NET allows you to customize the output HTML for the split parts by specifying additional options in the `HtmlSaveOptions` object. You can control various aspects such as CSS styles, images, fonts, and more. Refer to the Aspose.Words documentation for more details on customizing the HTML output.

#### Can I split the document based on multiple criteria?

Yes, you can split the document based on multiple criteria by combining the criteria options accordingly. For example, you can split the document by both heading and page by setting the `DocumentSplitCriteria` property to `HeadingParagraph | Page`. This will split the document at each heading and each page, creating smaller parts based on both criteria.
