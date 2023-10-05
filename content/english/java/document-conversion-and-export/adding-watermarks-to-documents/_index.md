---
title: Adding Watermarks to Documents in Aspose.Words for Java
linktitle: Adding Watermarks to Documents
second_title: Aspose.Words Java Document Processing API
description: Learn how to add watermarks to documents in Aspose.Words for Java. Customize text and image watermarks for professional-looking documents.
type: docs
weight: 15
url: /java/document-conversion-and-export/adding-watermarks-to-documents/
---

## Introduction to Adding Watermarks to Documents in Aspose.Words for Java

In this tutorial, we will explore how to add watermarks to documents using the Aspose.Words for Java API. Watermarks are a useful way to label documents with text or graphics to indicate their status, confidentiality, or other relevant information. We will cover both text and image watermarks in this guide.

## Setting up Aspose.Words for Java

Before we start adding watermarks to documents, we need to set up Aspose.Words for Java. Follow these steps to get started:

1. Download Aspose.Words for Java from [here](https://releases.aspose.com/words/java/).
2. Add the Aspose.Words for Java library to your Java project.
3. Import the necessary classes in your Java code.

Now that we have the library set up let's proceed to add watermarks.

## Step 1: Adding Text Watermarks

Text watermarks are a common choice when you want to add textual information to your documents. Here's how you can add a text watermark using Aspose.Words for Java:

```java
// Create a Document instance
Document doc = new Document("Document.docx");

// Define TextWatermarkOptions
TextWatermarkOptions options = new TextWatermarkOptions();
options.setFontFamily("Arial");
options.setFontSize(36f);
options.setColor(Color.BLACK);
options.setLayout(WatermarkLayout.HORIZONTAL);
options.setSemitransparent(false);

// Set the watermark text and options
doc.getWatermark().setText("Test", options);

// Save the document with the watermark
doc.save("DocumentWithWatermark.docx");
```

## Step 2: Adding Image Watermarks

In addition to text watermarks, you can also add image watermarks to your documents. Here's how to add an image watermark:

```java
// Create a Document instance
Document doc = new Document("Document.docx");

// Load the image for the watermark
byte[] imageBytes = Files.readAllBytes(Paths.get("watermark.png"));
Shape watermark = new Shape(doc, ShapeType.IMAGE);
watermark.getImageData().setImage(imageBytes);

// Set the watermark size and position
watermark.setWidth(200.0);
watermark.setHeight(100.0);
watermark.setRelativeHorizontalPosition(RelativeHorizontalPosition.CENTER);
watermark.setRelativeVerticalPosition(RelativeVerticalPosition.CENTER);

// Add the watermark to the document
doc.getFirstSection().getBody().getFirstParagraph().appendChild(watermark);

// Save the document with the watermark
doc.save("DocumentWithImageWatermark.docx");
```

## Step 3: Customizing Watermarks

You can customize watermarks by adjusting their appearance and position. For text watermarks, you can change the font, size, color, and layout. For image watermarks, you can modify their size and position as demonstrated in the previous examples.

## Step 4: Removing Watermarks

To remove watermarks from a document, you can use the following code:

```java
// Create a Document instance
Document doc = new Document("DocumentWithWatermark.docx");

// Remove the watermark
for (Shape shape : doc.getShapes())
{
    if (shape.getName().contains("Watermark"))
    {
        shape.remove();
    }
}

// Save the document without the watermark
doc.save("DocumentWithoutWatermark.docx");
```

## Complete Source Code for Adding Watermarks to Documents in Aspose.Words for Java

```java
	Document doc = new Document("Your Directory Path" + "Document.docx");
	TextWatermarkOptions options = new TextWatermarkOptions();
	{
		options.setFontFamily("Arial");
		options.setFontSize(36f);
		options.setColor(Color.BLACK);
		options.setLayout(WatermarkLayout.HORIZONTAL);
		options.isSemitrasparent(false);
	}
	doc.getWatermark().setText("Test", options);
	doc.save("Your Directory Path" + "WorkWithWatermark.AddTextWatermarkWithSpecificOptions.docx");
}
@Test
public void addAndRemoveWatermark() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Document.docx");
	insertWatermarkText(doc, "CONFIDENTIAL");
	doc.save("Your Directory Path" + "TestFile.Watermark.docx");
	removeWatermarkText(doc);
	doc.save("Your Directory Path" + "WorkWithWatermark.RemoveWatermark.docx");
}
/// <summary>
/// Inserts a watermark into a document.
/// </summary>
/// <param name="doc">The input document.</param>
/// <param name="watermarkText">Text of the watermark.</param>
private void insertWatermarkText(Document doc, String watermarkText) throws Exception
{
	// Create a watermark shape, this will be a WordArt shape.
	Shape watermark = new Shape(doc, ShapeType.TEXT_PLAIN_TEXT); { watermark.setName("Watermark"); }
	watermark.getTextPath().setText(watermarkText);
	watermark.getTextPath().setFontFamily("Arial");
	watermark.setWidth(500.0);
	watermark.setHeight(100.0);
	// Text will be directed from the bottom-left to the top-right corner.
	watermark.setRotation(-40);
	// Remove the following two lines if you need a solid black text.
	watermark.setFillColor(Color.GRAY);
	watermark.setStrokeColor(Color.GRAY);
	// Place the watermark in the page center.
	watermark.setRelativeHorizontalPosition(RelativeHorizontalPosition.PAGE);
	watermark.setRelativeVerticalPosition(RelativeVerticalPosition.PAGE);
	watermark.setWrapType(WrapType.NONE);
	watermark.setVerticalAlignment(VerticalAlignment.CENTER);
	watermark.setHorizontalAlignment(HorizontalAlignment.CENTER);
	// Create a new paragraph and append the watermark to this paragraph.
	Paragraph watermarkPara = new Paragraph(doc);
	watermarkPara.appendChild(watermark);
	// Insert the watermark into all headers of each document section.
	for (Section sect : (Iterable<Section>) doc.getSections())
	{
		// There could be up to three different headers in each section.
		// Since we want the watermark to appear on all pages, insert it into all headers.
		insertWatermarkIntoHeader(watermarkPara, sect, HeaderFooterType.HEADER_PRIMARY);
		insertWatermarkIntoHeader(watermarkPara, sect, HeaderFooterType.HEADER_FIRST);
		insertWatermarkIntoHeader(watermarkPara, sect, HeaderFooterType.HEADER_EVEN);
	}
}
private void insertWatermarkIntoHeader(Paragraph watermarkPara, Section sect,
	/*HeaderFooterType*/int headerType)
{
	HeaderFooter header = sect.getHeadersFooters().getByHeaderFooterType(headerType);
	if (header == null)
	{
		// There is no header of the specified type in the current section, so we need to create it.
		header = new HeaderFooter(sect.getDocument(), headerType);
		sect.getHeadersFooters().add(header);
	}
	// Insert a clone of the watermark into the header.
	header.appendChild(watermarkPara.deepClone(true));
}
private void removeWatermarkText(Document doc)
{
	for (HeaderFooter hf : (Iterable<HeaderFooter>) doc.getChildNodes(NodeType.HEADER_FOOTER, true))
	{
		for (Shape shape : (Iterable<Shape>) hf.getChildNodes(NodeType.SHAPE, true))
		{
			if (shape.getName().contains("WaterMark"))
			{
				shape.remove();
			}
		}
	}
```

## Conclusion

In this tutorial, we've learned how to add watermarks to documents using Aspose.Words for Java. Whether you need to add text or image watermarks, Aspose.Words provides the tools to customize and manage them efficiently. You can also remove watermarks when they are no longer needed, ensuring your documents are clean and professional.

## FAQ's

### How can I change the font of a text watermark?

To change the font of a text watermark, modify the `setFontFamily` property in the `TextWatermarkOptions`. For example:

```java
options.setFontFamily("Times New Roman");
```

### Can I add multiple watermarks to a single document?

Yes, you can add multiple watermarks to a document by creating multiple `Shape` objects with different settings and adding them to the document.

### Is it possible to rotate a watermark?

Yes, you can rotate a watermark by setting the `setRotation` property in the `Shape` object. Positive values rotate the watermark clockwise, and negative values rotate it counterclockwise.

### How can I make a watermark semi-transparent?

To make a watermark semi-transparent, set the `setSemitransparent` property to `true` in the `TextWatermarkOptions`.

### Can I add watermarks to specific sections of a document?

Yes, you can add watermarks to specific sections of a document by iterating through the sections and adding the watermark to the desired sections.
