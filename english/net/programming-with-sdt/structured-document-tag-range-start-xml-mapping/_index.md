---
title: Structured Document Tag Range Start Xml Mapping
linktitle: Structured Document Tag Range Start Xml Mapping
second_title: Aspose.Words for .NET API Reference
description: Learn how to set up XML mapping for a structured document tag range start in a Word document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-sdt/structured-document-tag-range-start-xml-mapping/
---

This tutorial explains how to set up XML mapping for a structured document tag range start in a Word document using Aspose.Words for .NET. XML mapping allows you to display specific parts of an XML data source within the content control.

## Prerequisites
To follow this tutorial, you need to have the following:

- Aspose.Words for .NET library installed.
- Basic knowledge of C# and working with Word documents.

## Step 1: Set up the Document Directory
Start by setting up the path to your document directory. Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to the directory where your document is located.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Load the Document and Create XML Part
Load the Word document using the `Document` constructor, passing the path to the document as a parameter. Create an XML part that contains the data you want to display within the structured document tag.

```csharp
Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
string xmlPartId = Guid.NewGuid().ToString("B");
string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
```

## Step 3: Set XML Mapping for Structured Document Tag
Retrieve the structured document tag range start from the document. Then, set the XML mapping for the structured document tag to display a specific part of the custom XML part using an XPath expression.

```csharp
StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
```

## Step 4: Save the Document
Save the modified document to the specified directory using the `Save` method. Provide the desired filename with the appropriate file extension. In this example, we save the document as "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx".

```csharp
doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

### Example source code for Structured Document Tag Range Start Xml Mapping using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Multi-section structured document tags.docx");
	// Construct an XML part that contains data and add it to the document's CustomXmlPart collection.
	string xmlPartId = Guid.NewGuid().ToString("B");
	string xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
	CustomXmlPart xmlPart = doc.CustomXmlParts.Add(xmlPartId, xmlPartContent);
	Console.WriteLine(Encoding.UTF8.GetString(xmlPart.Data));
	// Create a StructuredDocumentTag that will display the contents of our CustomXmlPart in the document.
	StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.GetChild(NodeType.StructuredDocumentTagRangeStart, 0, true);
	// If we set a mapping for our StructuredDocumentTag,
	// it will only display a part of the CustomXmlPart that the XPath points to.
	// This XPath will point to the contents second "<text>" element of the first "<root>" element of our CustomXmlPart.
	sdtRangeStart.XmlMapping.SetMapping(xmlPart, "/root[1]/text[2]", null);
	doc.Save(dataDir + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

That's it! You have successfully set up XML mapping for a structured document tag range start in your Word document using Aspose.Words for .NET.
