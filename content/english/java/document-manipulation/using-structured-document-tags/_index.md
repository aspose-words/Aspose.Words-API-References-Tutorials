---
title: Using Structured Document Tags (SDT) in Aspose.Words for Java
linktitle: Using Structured Document Tags (SDT) in Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: Learn how to use Structured Document Tags (SDT) in Aspose.Words for Java with this comprehensive guide. Create, modify, and bind SDTs to custom XML data.
type: docs
weight: 19
url: /java/document-manipulation/using-structured-document-tags/
---

## Introduction to Using Structured Document Tags (SDT) in Aspose.Words for Java

Structured Document Tags (SDT) are a powerful feature in Aspose.Words for Java that allow you to create and manipulate structured content within your documents. In this comprehensive guide, we will walk you through the various aspects of using SDTs in Aspose.Words for Java. Whether you are a beginner or an experienced developer, you will find valuable insights and practical examples in this article.

## Getting Started

Before we dive into the details, let's set up our environment and create a basic SDT. In this section, we'll cover the following topics:

- Creating a new document
- Adding a Structured Document Tag
- Saving the document

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Create a Structured Document Tag of type CHECKBOX
StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.CHECKBOX, MarkupLevel.INLINE);
builder.insertNode(sdtCheckBox);

// Save the document
doc.save("WorkingWithSDT.docx");
```

## Checking the Current State of a Checkbox SDT

Once you've added a checkbox SDT to your document, you might want to check its current state programmatically. This can be useful when you need to validate user input or perform specific actions based on the checkbox state.

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtCheckBox = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

if (sdtCheckBox.getSdtType() == SdtType.CHECKBOX) {
    // Checkbox is checked
    sdtCheckBox.setChecked(true);
}

doc.save("UpdatedDocument.docx");
```

## Modifying Content Controls

In this section, we'll explore how to modify content controls within your document. We'll cover three types of content controls: Plain Text, Drop-Down List, and Picture.

### Modifying Plain Text Content Control

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtPlainText = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

if (sdtPlainText.getSdtType() == SdtType.PLAIN_TEXT) {
    // Clear the existing content
    sdtPlainText.removeAllChildren();

    // Add new text
    Paragraph para = (Paragraph) sdtPlainText.appendChild(new Paragraph(doc));
    Run run = new Run(doc, "New text goes here");
    para.appendChild(run);
}

doc.save("ModifiedDocument.docx");
```

### Modifying Drop-Down List Content Control

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtDropDown = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

if (sdtDropDown.getSdtType() == SdtType.DROP_DOWN_LIST) {
    // Select the second item from the list
    SdtListItem secondItem = sdtDropDown.getListItems().get(2);
    sdtDropDown.getListItems().setSelectedValue(secondItem);
}

doc.save("ModifiedDocument.docx");
```

### Modifying Picture Content Control

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdtPicture = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);
Shape shape = (Shape) sdtPicture.getChild(NodeType.SHAPE, 0, true);

if (shape.hasImage()) {
    // Replace the image with a new one
    shape.getImageData().setImage("Watermark.png");
}

doc.save("ModifiedDocument.docx");
```

## Creating a ComboBox Content Control

A ComboBox Content Control allows users to select from a predefined list of options. Let's create one in our document.

```java
Document doc = new Document();
StructuredDocumentTag sdtComboBox = new StructuredDocumentTag(doc, SdtType.COMBO_BOX, MarkupLevel.BLOCK);
sdtComboBox.getListItems().add(new SdtListItem("Choose an item", "-1"));
sdtComboBox.getListItems().add(new SdtListItem("Item 1", "1"));
sdtComboBox.getListItems().add(new SdtListItem("Item 2", "2"));
doc.getFirstSection().getBody().appendChild(sdtComboBox);

doc.save("ComboBoxDocument.docx");
```

## Working with Rich Text Content Control

Rich Text Content Controls are perfect for adding formatted text to your documents. Let's create one and set its content.

```java
Document doc = new Document();
StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RICH_TEXT, MarkupLevel.BLOCK);
Paragraph para = new Paragraph(doc);
Run run = new Run(doc);
run.setText("Hello World");
run.getFont().setColor(Color.GREEN);
para.getRuns().add(run);
sdtRichText.getChildNodes().add(para);
doc.getFirstSection().getBody().appendChild(sdtRichText);

doc.save("RichTextDocument.docx");
```

## Setting Content Control Styles

You can apply styles to content controls to enhance the visual appearance of your document. Let's see how to set the style of a content control.

```java
Document doc = new Document("WorkingWithSDT.docx");
StructuredDocumentTag sdt = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);

// Apply a custom style
Style style = doc.getStyles().getByStyleIdentifier(StyleIdentifier.QUOTE);
sdt.setStyle(style);

doc.save("StyledDocument.docx");
```

## Binding an SDT to Custom XML Data

In some scenarios, you may need to bind an SDT to custom XML data for dynamic content generation. Let's explore how to achieve this.

```java
Document doc = new Document();
CustomXmlPart xmlPart = doc.getCustomXmlParts().add(UUID.randomUUID().toString(), "<root><text>Hello, World!</text></root>");
StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PLAIN_TEXT, MarkupLevel.BLOCK);
doc.getFirstSection().getBody().appendChild(sdt);
sdt.getXmlMapping().setMapping(xmlPart, "/root[1]/text[1]", "");

doc.save("CustomXMLBinding.docx");
```

## Creating a Table with Repeating Sections Mapped to Custom XML Data

Tables with repeating sections can be extremely useful for presenting structured data. Let's create such a table and map it to custom XML data.

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
CustomXmlPart xmlPart = doc.getCustomXmlParts().add("Books", "<books>...</books>");
Table table = builder.startTable();
builder.insertCell();
builder.write("Title");
builder.insertCell();
builder.write("Author");
builder.endRow();
builder.endTable();

StructuredDocumentTag repeatingSectionSdt = new StructuredDocumentTag(doc, SdtType.REPEATING_SECTION, MarkupLevel.ROW);
repeatingSectionSdt.getXmlMapping().setMapping(xmlPart, "/books[1]/book", "");
table.appendChild(repeatingSectionSdt);

StructuredDocumentTag repeatingSectionItemSdt = new StructuredDocumentTag(doc, SdtType.REPEATING_SECTION_ITEM, MarkupLevel.ROW);
repeatingSectionSdt.appendChild(repeatingSectionItemSdt);

Row row = new Row(doc);
repeatingSectionItemSdt.appendChild(row);

StructuredDocumentTag titleSdt = new StructuredDocumentTag(doc, SdtType.PLAIN_TEXT, MarkupLevel.CELL);
titleSdt.getXmlMapping().setMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
row.appendChild(titleSdt);

StructuredDocumentTag authorSdt = new StructuredDocumentTag(doc, SdtType.PLAIN_TEXT, MarkupLevel.CELL);
authorSdt.getXmlMapping().setMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
row.appendChild(authorSdt);

doc.save("RepeatingTableDocument.docx");
```

## Working with Multi-Section Structured Document Tags

Structured Document Tags can span multiple sections in a document. In this section, we'll explore how to work with multi-section SDTs.

```java
Document doc = new Document("MultiSectionDocument.docx");
NodeCollection tags = doc.getChildNodes(NodeType.STRUCTURED_DOCUMENT_TAG_RANGE_START, true);

for (StructuredDocumentTagRangeStart tag : tags) {
    System.out.println(tag.getTitle());
}

doc.save("ModifiedMultiSectionDocument.docx");
```

## Complete Source Code For Using Structured Document Tags (SDT) in Aspose.Words for Java

```java
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	StructuredDocumentTag sdtCheckBox = new StructuredDocumentTag(doc, SdtType.CHECKBOX, MarkupLevel.INLINE);
	builder.insertNode(sdtCheckBox);
	doc.save("Your Directory Path" + "WorkingWithSdt.CheckBoxTypeContentControl.docx", SaveFormat.DOCX);
}
@Test
public void currentStateOfCheckBox() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Structured document tags.docx");
	// Get the first content control from the document.
	StructuredDocumentTag sdtCheckBox =
		(StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);
	if (sdtCheckBox.getSdtType() == SdtType.CHECKBOX)
		sdtCheckBox.setChecked(true);
	doc.save("Your Directory Path" + "WorkingWithSdt.CurrentStateOfCheckBox.docx");
}
@Test
public void modifyContentControls() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Structured document tags.docx");
	for (StructuredDocumentTag sdt : (Iterable<StructuredDocumentTag>) doc.getChildNodes(NodeType.STRUCTURED_DOCUMENT_TAG, true))
	{
		switch (sdt.getSdtType())
		{
			case SdtType.PLAIN_TEXT:
			{
				sdt.removeAllChildren();
				Paragraph para = (Paragraph) sdt.appendChild(new Paragraph(doc));
				Run run = new Run(doc, "new text goes here");
				para.appendChild(run);
				break;
			}
			case SdtType.DROP_DOWN_LIST:
			{
				SdtListItem secondItem = sdt.getListItems().get(2);
				sdt.getListItems().setSelectedValue(secondItem);
				break;
			}
			case SdtType.PICTURE:
			{
				Shape shape = (Shape) sdt.getChild(NodeType.SHAPE, 0, true);
				if (shape.hasImage())
				{
					shape.getImageData().setImage(getImagesDir() + "Watermark.png");
				}
				break;
			}
		}
	}
	doc.save("Your Directory Path" + "WorkingWithSdt.ModifyContentControls.docx");
}
@Test
public void comboBoxContentControl() throws Exception
{
	Document doc = new Document();
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.COMBO_BOX, MarkupLevel.BLOCK);
	sdt.getListItems().add(new SdtListItem("Choose an item", "-1"));
	sdt.getListItems().add(new SdtListItem("Item 1", "1"));
	sdt.getListItems().add(new SdtListItem("Item 2", "2"));
	doc.getFirstSection().getBody().appendChild(sdt);
	doc.save("Your Directory Path" + "WorkingWithSdt.ComboBoxContentControl.docx");
}
@Test
public void richTextBoxContentControl() throws Exception
{
	Document doc = new Document();
	StructuredDocumentTag sdtRichText = new StructuredDocumentTag(doc, SdtType.RICH_TEXT, MarkupLevel.BLOCK);
	Paragraph para = new Paragraph(doc);
	Run run = new Run(doc);
	run.setText("Hello World");
	run.getFont().setColor(Color.GREEN);
	para.getRuns().add(run);
	sdtRichText.getChildNodes().add(para);
	doc.getFirstSection().getBody().appendChild(sdtRichText);
	doc.save("Your Directory Path" + "WorkingWithSdt.RichTextBoxContentControl.docx");
}
@Test
public void setContentControlColor() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);
	sdt.setColor(Color.RED);
	doc.save("Your Directory Path" + "WorkingWithSdt.SetContentControlColor.docx");
}
@Test
public void clearContentsControl() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);
	sdt.clear();
	doc.save("Your Directory Path" + "WorkingWithSdt.ClearContentsControl.doc");
}
@Test
public void bindSdTtoCustomXmlPart() throws Exception
{
	Document doc = new Document();
	CustomXmlPart xmlPart =
		doc.getCustomXmlParts().add(UUID.randomUUID().toString(), "<root><text>Hello, World!</text></root>");
	StructuredDocumentTag sdt = new StructuredDocumentTag(doc, SdtType.PLAIN_TEXT, MarkupLevel.BLOCK);
	doc.getFirstSection().getBody().appendChild(sdt);
	sdt.getXmlMapping().setMapping(xmlPart, "/root[1]/text[1]", "");
	doc.save("Your Directory Path" + "WorkingWithSdt.BindSDTtoCustomXmlPart.doc");
}
@Test
public void setContentControlStyle() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Structured document tags.docx");
	StructuredDocumentTag sdt = (StructuredDocumentTag) doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG, 0, true);
	Style style = doc.getStyles().getByStyleIdentifier(StyleIdentifier.QUOTE);
	sdt.setStyle(style);
	doc.save("Your Directory Path" + "WorkingWithSdt.SetContentControlStyle.docx");
}
@Test
public void creatingTableRepeatingSectionMappedToCustomXmlPart() throws Exception
{
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	CustomXmlPart xmlPart = doc.getCustomXmlParts().add("Books",
		"<books><book><title>Everyday Italian</title><author>Giada De Laurentiis</author></book>" +
		"<book><title>Harry Potter</title><author>J K. Rowling</author></book>" +
		"<book><title>Learning XML</title><author>Erik T. Ray</author></book></books>");
	Table table = builder.startTable();
	builder.insertCell();
	builder.write("Title");
	builder.insertCell();
	builder.write("Author");
	builder.endRow();
	builder.endTable();
	StructuredDocumentTag repeatingSectionSdt =
		new StructuredDocumentTag(doc, SdtType.REPEATING_SECTION, MarkupLevel.ROW);
	repeatingSectionSdt.getXmlMapping().setMapping(xmlPart, "/books[1]/book", "");
	table.appendChild(repeatingSectionSdt);
	StructuredDocumentTag repeatingSectionItemSdt = 
		new StructuredDocumentTag(doc, SdtType.REPEATING_SECTION_ITEM, MarkupLevel.ROW);
	repeatingSectionSdt.appendChild(repeatingSectionItemSdt);
	Row row = new Row(doc);
	repeatingSectionItemSdt.appendChild(row);
	StructuredDocumentTag titleSdt =
		new StructuredDocumentTag(doc, SdtType.PLAIN_TEXT, MarkupLevel.CELL);
	titleSdt.getXmlMapping().setMapping(xmlPart, "/books[1]/book[1]/title[1]", "");
	row.appendChild(titleSdt);
	StructuredDocumentTag authorSdt =
		new StructuredDocumentTag(doc, SdtType.PLAIN_TEXT, MarkupLevel.CELL);
	authorSdt.getXmlMapping().setMapping(xmlPart, "/books[1]/book[1]/author[1]", "");
	row.appendChild(authorSdt);
	doc.save("Your Directory Path" + "WorkingWithSdt.CreatingTableRepeatingSectionMappedToCustomXmlPart.docx");
}
@Test
public void multiSection() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Multi-section structured document tags.docx");
	NodeCollection tags = doc.getChildNodes(NodeType.STRUCTURED_DOCUMENT_TAG_RANGE_START, true);
	for (StructuredDocumentTagRangeStart tag : (Iterable<StructuredDocumentTagRangeStart>) tags)
		System.out.println(tag.getTitle());
}
@Test
public void structuredDocumentTagRangeStartXmlMapping() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Multi-section structured document tags.docx");
	// Construct an XML part that contains data and add it to the document's CustomXmlPart collection.
	String xmlPartId = UUID.randomUUID().toString();
	String xmlPartContent = "<root><text>Text element #1</text><text>Text element #2</text></root>";
	CustomXmlPart xmlPart = doc.getCustomXmlParts().add(xmlPartId, xmlPartContent);
	System.out.println(new String(xmlPart.getData(), StandardCharsets.US_ASCII));
	// Create a StructuredDocumentTag that will display the contents of our CustomXmlPart in the document.
	StructuredDocumentTagRangeStart sdtRangeStart = (StructuredDocumentTagRangeStart)doc.getChild(NodeType.STRUCTURED_DOCUMENT_TAG_RANGE_START, 0, true);
	// If we set a mapping for our StructuredDocumentTag,
	// it will only display a part of the CustomXmlPart that the XPath points to.
	// This XPath will point to the contents second "<text>" element of the first "<root>" element of our CustomXmlPart.
	sdtRangeStart.getXmlMapping().setMapping(xmlPart, "/root[1]/text[2]", null);
	doc.save("Your Directory Path" + "WorkingWithSdt.StructuredDocumentTagRangeStartXmlMapping.docx");
```

## Conclusion

Structured Document Tags in Aspose.Words for Java provide a versatile way to manage and format content within your documents. Whether you need to create templates, forms, or dynamic documents, SDTs offer the flexibility and control you require. By following the examples and guidelines provided in this article, you can harness the power of SDTs to enhance your document processing tasks.

## FAQ's

### What is the purpose of Structured Document Tags (SDTs)?

Structured Document Tags (SDTs) serve the purpose of organizing and formatting content within documents, making it easier to create templates, forms, and structured documents.

### How can I check the current state of a Checkbox SDT?

You can check the current state of a Checkbox SDT using the `setChecked` method, as demonstrated in the article.

### Can I apply styles to Content Controls?

Yes, you can apply styles to Content Controls to customize their appearance in the document.

### Is it possible to bind an SDT to custom XML data?

Yes, you can bind an SDT to custom XML data, allowing for dynamic content generation and data mapping.

### What are Repeating Sections in SDTs?

Repeating Sections in SDTs allow you to create tables with dynamic data, where rows can be repeated based on the mapped XML data.
