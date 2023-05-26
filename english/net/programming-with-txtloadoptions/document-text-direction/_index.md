---
title: Document Text Direction
linktitle: Document Text Direction
second_title: Aspose.Words for .NET API Reference
description: Learn how to specify text direction in your documents with Aspose.Words for .NET. Improve display for right-to-left languages.
type: docs
weight: 10
url: /net/programming-with-txtloadoptions/document-text-direction/
---

In this tutorial, we will explore the C# source code provided for the "Document Text Direction" feature with Aspose.Words for .NET. This feature lets you specify the direction of text in a document, which is especially useful for languages that are written from right to left, such as Hebrew or Arabic.

## Step 1: Setting up the environment

Before you begin, make sure you've set up your development environment with Aspose.Words for .NET. Make sure you've added the necessary references and imported the appropriate namespaces.

## Step 2: Configuring upload options

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection. Auto };
```

In this step, we configure the document loading options. We create a new `TxtLoadOptions` object and set the `DocumentDirection` property to `DocumentDirection.Auto`. This value tells Aspose.Words to automatically determine the text direction based on the content of the document.

## Step 3: Loading the document

```csharp
Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);
```

In this step, we load the document using the `Document` method and passing the path to the text file to load. We also use the specified loading options.

## Step 4: Manipulate the paragraph and display the text direction

```csharp
Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);
```

In this step, we access the first paragraph of the document using the `FirstSection` and `Body` properties. Next, we access the `ParagraphFormat.Bidi` property to get the text direction of the paragraph. We then display this value in the console.

## Step 5: Save the document

```csharp
doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
```

In this last step, we save the resulting document in .docx format using the `Save` method and passing the path to the output file.

Now you can run the source code to load the text document and determine the text direction. The resulting document will be saved in the specified directory with the name "WorkingWithTxtLoadOptions.DocumentTextDirection.docx".

### Sample source code for document text direction functionality with Aspose.Words for .NET.


```csharp

            
// Path to your document directory
string dataDir = "YOUR DOCUMENT DIRECTORY";

TxtLoadOptions loadOptions = new TxtLoadOptions { DocumentDirection = DocumentDirection.Auto };

Document doc = new Document(dataDir + "Hebrew text.txt", loadOptions);

Paragraph paragraph = doc.FirstSection.Body.FirstParagraph;
Console.WriteLine(paragraph.ParagraphFormat.Bidi);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DocumentTextDirection.docx");
            
        
```

## Conclusion

In this tutorial, we explored the document text direction feature in Aspose.Words for .NET. We learned how to specify the direction of text in a document, especially for languages that are written from right to left, such as Hebrew or Arabic.

This feature is essential to ensure that text is displayed correctly in multilingual documents. By using the appropriate loading options, Aspose.Words can automatically detect the direction of text and apply it to the document.

With Aspose.Words, you can easily manipulate the direction of text in your documents, providing a smooth and intuitive reading experience for users.

It is important to note that this feature is especially useful when working with languages that require specific text direction. Aspose.Words makes this task easy by providing powerful tools to manage the direction of text in your documents.

Remember to use the appropriate loading options, such as setting automatic text direction, to get the results you want in your documents.

Aspose.Words for .NET offers many advanced features for document manipulation and generation. By further exploring the documentation and examples provided by Aspose.Words, you will be able to fully exploit the capabilities of this powerful library.

So, don't hesitate to integrate document text direction into your Aspose.Words for .NET projects and take advantage of its benefits to create attractive and high-quality multilingual documents.