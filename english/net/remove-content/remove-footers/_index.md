---
title: Remove Footers
linktitle: Remove Footers
second_title: Aspose.Words Document Processing API
description: Learn how to easily remove footers from Word documents with Aspose.Words for .NET. Follow our step-by-step guide for efficient handling of DOCX files.
type: docs
weight: 10
url: /net/remove-content/remove-footers/
---
When it comes to working with Word documents in your .NET application, Aspose.Words is a powerful and versatile tool that can help you easily manipulate DOCX files. In this article, we'll explore a specific feature of Aspose.Words: removing footers.

## Understanding Aspose.Words for .NET

Aspose.Words for .NET is a powerful class library for creating, modifying, converting and manipulating Word documents in .NET applications. It offers a wide range of features including managing headers, footers, images, text formatting and more.

## Purpose of Removing Footers in Aspose.Words

There may be instances where you want to remove footers from a Word document. This may be due to various reasons, such as the need to delete sensitive information, to adapt the document for another use or simply to eliminate unwanted elements. Aspose.Words makes this task much easier by giving you an easy and efficient way to remove footers from your documents.

## Step 1: Set the Document Directory Path

Before you start, make sure you have set your document directory in the "dataDir" variable. This will allow you to specify the exact location where your DOCX file is located.

```csharp
string dataDir = "PATH_TO_YOUR_DOCUMENT_DIRECTORY";
```

## Step 2: Load the Document

The first step is to load the document into an object of type Document. This will allow you to access and manipulate the contents of the document.

```csharp
Document doc = new Document(dataDir + "Name_of_document.docx");
```

Be sure to replace "Name_of_document.docx" with the actual name of your document.

## Step 3: Iterate Through Sections

A Word document can contain multiple sections, and each section can have its own footers. We have to go through each section of the document to get to the footers.

```csharp
foreach (Section section in doc)
{
     // Code to remove footers
}
```

## Step 4: Remove Footers

Now that we have navigated to a specific section, we can remove the footers from that section. In Aspose.Words, there are different types of possible footers, such as "FooterFirst" (for first page), "FooterPrimary" (for odd pages) and "FooterEven" (for even pages). We need to check and remove all these types of footers.

```csharp
HeaderFooter footer = section.HeadersFooters[HeaderFooterType.Footer

First];
footer?.Remove();

footer = section.HeadersFooters[HeaderFooterType.FooterPrimary];
footer?.Remove();

footer = section.HeadersFooters[HeaderFooterType.FooterEven];
footer?.Remove();
```

## Step 5: Save the Modified Document

Once we're done removing the footers, we can save the edited document to a separate file.

```csharp
doc.Save(dataDir + "Name_of_modified_document.docx");
```

Don't forget to specify the name and location of the modified file in "Name_of_modified_document.docx".

### Sample source code for Remove Footers using Aspose.Words for .NET 
```csharp

// Path to your document directory 
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
Document doc = new Document(dataDir + "Header and footer types.docx");

foreach (Section section in doc)
{
	// Up to three different footers are possible in a section (for first, even and odd pages)
	// we check and delete all of them.
	HeaderFooter footer = section.HeadersFooters[HeaderFooterType.FooterFirst];
	footer?.Remove();

	// Primary footer is the footer used for odd pages.
	footer = section.HeadersFooters[HeaderFooterType.FooterPrimary];
	footer?.Remove();

	footer = section.HeadersFooters[HeaderFooterType.FooterEven];
	footer?.Remove();
}

doc.Save(dataDir + "RemoveContent.RemoveFooters.docx");
            
        
```

## Conclusion

In this article, we explored how to remove footers from a Word document using Aspose.Words for .NET. By following the steps provided, you can easily manipulate your documents and remove unwanted footers. Aspose.Words offers a powerful and convenient solution for working with Word documents in your .NET application.


