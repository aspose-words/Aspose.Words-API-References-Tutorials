---
title: Bind SDT to Custom Xml Part
linktitle: Bind SDT to Custom Xml Part
second_title: Aspose.Words for .NET API Reference
description: Learn how to bind a SDT to a Custom Xml Part using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-sdt/bind-sdt-to-custom-xml-part/
---

This tutorial demonstrates how to bind a Structured Document Tag (SDT) to a Custom Xml Part using Aspose.Words for .NET. SDTs allow you to add structured content controls to a Word document, and CustomXmlParts provide a way to store custom XML data associated with the document.

## Prerequisites
To follow this tutorial, you need to have the following:

- Aspose.Words for .NET library installed.
- Basic knowledge of C# and XML.

## Step 1: Set up the Document Directory
Begin by setting up the path to your document directory. Replace `"YOUR DOCUMENT DIRECTORY"` with the actual path to the directory where you want to save the document.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Create a Document and CustomXmlPart
Create a new instance of the `Document` class and a `CustomXmlPart` to store the custom XML data. The custom XML should be in valid XML format. In this example, we use a simple XML string `<root><text>Hello, World!</text></root>`.

```csharp
Document doc = new Document();
CustomXmlPart xmlPart = doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
```

## Step 3: Add a StructuredDocumentTag (SDT) to the Document
Add a `StructuredDocumentTag` to the document to serve as the content control. Specify the `SdtType` as `PlainText` and the `MarkupLevel` as `Block` to create a block-level SDT.

```csharp
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
doc.FirstSection.Body.AppendChild(sdt);
```

## Step 4: Set the XML Mapping for the SDT
Map the SDT to the `CustomXmlPart` by using the `SetMapping` method of the `XmlMapping` property. Specify the `CustomXmlPart`, the XPath expression to locate the desired XML node, and the namespace prefix if necessary. In this example, we map the SDT to `/root[1]/text[1]`.

```csharp
sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
```

## Step 5: Save the Document
Save the modified document to the specified directory using the `Save` method. Provide the desired filename with the appropriate file extension. In this example, we save the document as "WorkingWithSdt.BindSDTtoCustomXmlPart.doc".

```csharp
doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

### Example source code for Bind Sd Tto Custom Xml Part using Aspose.Words for .NET 

```csharp
	// Path to your document directory 
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	CustomXmlPart xmlPart =
		doc.CustomXmlParts.Add(Guid.NewGuid().ToString("B"), "<root><text>Hello, World!</text></root>");
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PlainText, MarkupLevel.Block);
	doc.FirstSection.Body.AppendChild(sdt);
	sdt.XmlMapping.SetMapping(xmlPart, "/root[1]/text[1]", "");
	doc.Save(dataDir + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
```

That's it! You have successfully bound an SDT to a CustomXmlPart in your Word document using Aspose.Words for .NET.
