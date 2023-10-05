---
title: Adding Content using DocumentBuilder in Aspose.Words for Java
linktitle: Adding Content using DocumentBuilder in Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: Master Document Creation with Aspose.Words for Java. A Step-by-Step Guide to Adding Text, Tables, Images, and More. Create Stunning Word Documents Effortlessly.
type: docs
weight: 26
url: /java/document-manipulation/adding-content-using-documentbuilder/
---

## Introduction to Adding Content using DocumentBuilder in Aspose.Words for Java

In this step-by-step guide, we'll explore how to use Aspose.Words for Java's DocumentBuilder to add various types of content to a Word document. We'll cover inserting text, tables, horizontal rules, form fields, HTML, hyperlinks, table of contents, inline and floating images, paragraphs, and more. Let's get started!

## Prerequisites

Before you begin, make sure you have the Aspose.Words for Java library set up in your project. You can download it from [here](https://releases.aspose.com/words/java/).

## Step 1: Adding Text

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insert a simple text paragraph
builder.write("This is a simple text paragraph.");

// Save the document
doc.save("path/to/your/document.docx");
```

## Step 2: Adding Tables

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Start a table
Table table = builder.startTable();

// Insert cells and content
builder.insertCell();
builder.write("Cell 1");

builder.insertCell();
builder.write("Cell 2");

// End the table
builder.endTable();

// Save the document
doc.save("path/to/your/document.docx");
```

## Step 3: Adding Horizontal Rule

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insert a horizontal rule
builder.insertHorizontalRule();

// Save the document
doc.save("path/to/your/document.docx");
```

## Step 4: Adding Form Fields

### Text Input Form Field

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insert a text input form field
builder.insertTextInput("TextInput", TextFormFieldType.REGULAR, "", "Default text", 0);

// Save the document
doc.save("path/to/your/document.docx");
```

### Check Box Form Field

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insert a check box form field
builder.insertCheckBox("CheckBox", true, true, 0);

// Save the document
doc.save("path/to/your/document.docx");
```

### Combo Box Form Field

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Define items for the combo box
String[] items = { "Option 1", "Option 2", "Option 3" };

// Insert a combo box form field
builder.insertComboBox("DropDown", items, 0);

// Save the document
doc.save("path/to/your/document.docx");
```

## Step 5: Adding HTML

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insert HTML content
builder.insertHtml("<p>This is an HTML paragraph.</p>");

// Save the document
doc.save("path/to/your/document.docx");
```

## Step 6: Adding Hyperlinks

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insert a hyperlink
builder.write("Visit ");
builder.getFont().setColor(Color.BLUE);
builder.getFont().setUnderline(Underline.SINGLE);
builder.insertHyperlink("Aspose Website", "http://www.aspose.com", false);
builder.getFont().clearFormatting();
builder.write(" for more information.");

// Save the document
doc.save("path/to/your/document.docx");
```

## Step 7: Adding a Table of Contents

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insert a table of contents
builder.insertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// Add document content
// ...

// Update the table of contents
doc.updateFields();

// Save the document
doc.save("path/to/your/document.docx");
```

## Step 8: Adding Images

### Inline Image

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insert an inline image
builder.insertImage("path/to/your/image.png");

// Save the document
doc.save("path/to/your/document.docx");
```

### Floating Image

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insert a floating image
builder.insertImage("path/to/your/image.png", RelativeHorizontalPosition.MARGIN, 100.0, RelativeVerticalPosition.MARGIN, 100.0, 200.0, 100.0, WrapType.SQUARE);

// Save the document
doc.save("path/to/your/document.docx");
```

## Step 9: Adding Paragraphs

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Set paragraph formatting
Font font = builder.getFont();
font.setSize(16.0);
font.setBold(true);
font.setColor(Color.BLUE);
font.setName("Arial");
font.setUnderline(Underline.DASH);

ParagraphFormat paragraphFormat = builder.getParagraphFormat();
paragraphFormat.setFirstLineIndent(8.0);
paragraphFormat.setAlignment(ParagraphAlignment.JUSTIFY);
paragraphFormat.setKeepTogether(true);

// Insert a paragraph
builder.writeln("This is a formatted paragraph.");

// Save the document
doc.save("path/to/your/document.docx");
```

## Step 10: Moving the Cursor

You can control the cursor position within the document using various methods like `moveToParagraph`, `moveToCell`, and more. Here's an example:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Move the cursor to a specific paragraph
builder.moveToParagraph(2, 0);

// Add content at the new cursor position
builder.writeln("This is the 3rd paragraph.");
```

These are some common operations you can perform using Aspose.Words for Java's DocumentBuilder. Explore the library's documentation for more advanced features and customization options. Happy document creation!

## Complete Source Code For Adding Content using DocumentBuilder in Aspose.Words for Java

```java
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.startBookmark("FineBookmark");
	builder.writeln("This is just a fine bookmark.");
	builder.endBookmark("FineBookmark");
	doc.save("Your Directory Path" + "WorkingWithBookmarks.DocumentBuilderInsertBookmark.docx");
}
@Test
public void buildTable() throws Exception
{
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.startTable();
	builder.insertCell();
	table.autoFit(AutoFitBehavior.FIXED_COLUMN_WIDTHS);
	builder.getCellFormat().setVerticalAlignment(CellVerticalAlignment.CENTER);
	builder.write("This is row 1 cell 1");
	builder.insertCell();
	builder.write("This is row 1 cell 2");
	builder.endRow();
	builder.insertCell();
	builder.getRowFormat().setHeight(100.0);
	builder.getRowFormat().setHeightRule(HeightRule.EXACTLY);
	builder.getCellFormat().setOrientation(TextOrientation.UPWARD);
	builder.writeln("This is row 2 cell 1");
	builder.insertCell();
	builder.getCellFormat().setOrientation(TextOrientation.DOWNWARD);
	builder.writeln("This is row 2 cell 2");
	builder.endRow();
	builder.endTable();
	doc.save("Your Directory Path" + "AddContentUsingDocumentBuilder.BuildTable.docx");
}
@Test
public void insertHorizontalRule() throws Exception
{
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.writeln("Insert a horizontal rule shape into the document.");
	builder.insertHorizontalRule();
	doc.save("Your Directory Path" + "AddContentUsingDocumentBuilder.InsertHorizontalRule.docx");
}
@Test
public void horizontalRuleFormat() throws Exception
{
	DocumentBuilder builder = new DocumentBuilder();
	Shape shape = builder.insertHorizontalRule();
	HorizontalRuleFormat horizontalRuleFormat = shape.getHorizontalRuleFormat();
	horizontalRuleFormat.setAlignment(HorizontalRuleAlignment.CENTER);
	horizontalRuleFormat.setWidthPercent(70.0);
	horizontalRuleFormat.setHeight(3.0);
	horizontalRuleFormat.setColor(Color.BLUE);
	horizontalRuleFormat.setNoShade(true);
	builder.getDocument().save("Your Directory Path" + "AddContentUsingDocumentBuilder.HorizontalRuleFormat.docx");
}
@Test
public void insertBreak() throws Exception
{
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.writeln("This is page 1.");
	builder.insertBreak(BreakType.PAGE_BREAK);
	builder.writeln("This is page 2.");
	builder.insertBreak(BreakType.PAGE_BREAK);
	builder.writeln("This is page 3.");
	doc.save("Your Directory Path" + "AddContentUsingDocumentBuilder.InsertBreak.docx");
}
@Test
public void insertTextInputFormField() throws Exception
{
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.insertTextInput("TextInput", TextFormFieldType.REGULAR, "", "Hello", 0);
	doc.save("Your Directory Path" + "AddContentUsingDocumentBuilder.InsertTextInputFormField.docx");
}
@Test
public void insertCheckBoxFormField() throws Exception
{
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.insertCheckBox("CheckBox", true, true, 0);
	doc.save("Your Directory Path" + "AddContentUsingDocumentBuilder.InsertCheckBoxFormField.docx");
}
@Test
public void insertComboBoxFormField() throws Exception
{
	String[] items = { "One", "Two", "Three" };
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.insertComboBox("DropDown", items, 0);
	doc.save("Your Directory Path" + "AddContentUsingDocumentBuilder.InsertComboBoxFormField.docx");
}
@Test
public void insertHtml() throws Exception
{
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.insertHtml(
		"<P align='right'>Paragraph right</P>" +
		"<b>Implicit paragraph left</b>" +
		"<div align='center'>Div center</div>" +
		"<h1 align='left'>Heading 1 left.</h1>");
	doc.save("Your Directory Path" + "AddContentUsingDocumentBuilder.InsertHtml.docx");
}
@Test
public void insertHyperlink() throws Exception
{
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.write("Please make sure to visit ");
	builder.getFont().setColor(Color.BLUE);
	builder.getFont().setUnderline(Underline.SINGLE);
	builder.insertHyperlink("Aspose Website", "http://www.aspose.com", false);
	builder.getFont().clearFormatting();
	builder.write(" for more information.");
	doc.save("Your Directory Path" + "AddContentUsingDocumentBuilder.InsertHyperlink.docx");
}
@Test
public void insertTableOfContents() throws Exception
{
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.insertTableOfContents("\\o \"1-3\" \\h \\z \\u");
	// Start the actual document content on the second page.
	builder.insertBreak(BreakType.PAGE_BREAK);
	builder.getParagraphFormat().setStyleIdentifier(StyleIdentifier.HEADING_1);
	builder.writeln("Heading 1");
	builder.getParagraphFormat().setStyleIdentifier(StyleIdentifier.HEADING_2);
	builder.writeln("Heading 1.1");
	builder.writeln("Heading 1.2");
	builder.getParagraphFormat().setStyleIdentifier(StyleIdentifier.HEADING_1);
	builder.writeln("Heading 2");
	builder.writeln("Heading 3");
	builder.getParagraphFormat().setStyleIdentifier(StyleIdentifier.HEADING_2);
	builder.writeln("Heading 3.1");
	builder.getParagraphFormat().setStyleIdentifier(StyleIdentifier.HEADING_3);
	builder.writeln("Heading 3.1.1");
	builder.writeln("Heading 3.1.2");
	builder.writeln("Heading 3.1.3");
	builder.getParagraphFormat().setStyleIdentifier(StyleIdentifier.HEADING_2);
	builder.writeln("Heading 3.2");
	builder.writeln("Heading 3.3");
	// The newly inserted table of contents will be initially empty.
	// It needs to be populated by updating the fields in the document.
	doc.updateFields();
	doc.save("Your Directory Path" + "AddContentUsingDocumentBuilder.InsertTableOfContents.docx");
}
@Test
public void insertInlineImage() throws Exception
{
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.insertImage(getImagesDir() + "Transparent background logo.png");
	doc.save("Your Directory Path" + "AddContentUsingDocumentBuilder.InsertInlineImage.docx");
}
@Test
public void insertFloatingImage() throws Exception
{
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.insertImage(getImagesDir() + "Transparent background logo.png",
		RelativeHorizontalPosition.MARGIN,
		100.0,
		RelativeVerticalPosition.MARGIN,
		100.0,
		200.0,
		100.0,
		WrapType.SQUARE);
	doc.save("Your Directory Path" + "AddContentUsingDocumentBuilder.InsertFloatingImage.docx");
}
@Test
public void insertParagraph() throws Exception
{
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Font font = builder.getFont();
	font.setSize(16.0);
	font.setBold(true);
	font.setColor(Color.BLUE);
	font.setName("Arial");
	font.setUnderline(Underline.DASH);
	ParagraphFormat paragraphFormat = builder.getParagraphFormat();
	paragraphFormat.setFirstLineIndent(8.0);
	paragraphFormat.setAlignment(ParagraphAlignment.JUSTIFY);
	paragraphFormat.setKeepTogether(true);
	builder.writeln("A whole paragraph.");
	doc.save("Your Directory Path" + "AddContentUsingDocumentBuilder.InsertParagraph.docx");
}
@Test
public void insertTCField() throws Exception
{
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.insertField("TC \"Entry Text\" \\f t");
	doc.save("Your Directory Path" + "AddContentUsingDocumentBuilder.InsertTCField.docx");
}
@Test
public void insertTCFieldsAtText() throws Exception
{
	Document doc = new Document();
	FindReplaceOptions options = new FindReplaceOptions();
	options.getApplyFont().setHighlightColor(Color.ORANGE);
	options.setReplacingCallback(new InsertTCFieldHandler("Chapter 1", "\\l 1"));
	doc.getRange().replace(Pattern.compile("The Beginning"), "", options);
}
public final static class InsertTCFieldHandler implements IReplacingCallback
{
	// Store the text and switches to be used for the TC fields.
	private /*final*/ String mFieldText;
	private /*final*/ String mFieldSwitches;
	/// <summary>
	/// The display text and switches to use for each TC field. Display name can be an empty string or null.
	/// </summary>
	public InsertTCFieldHandler(String text, String switches)
	{
		mFieldText = text;
		mFieldSwitches = switches;
	}
	public /*ReplaceAction*/int /*IReplacingCallback.*/replacing(ReplacingArgs args) throws Exception
	{
		DocumentBuilder builder = new DocumentBuilder((Document) args.getMatchNode().getDocument());
		builder.moveTo(args.getMatchNode());
		// If the user-specified text to be used in the field as display text, then use that,
		// otherwise use the match string as the display text.
		String insertText = !mFieldText.isEmpty() ? mFieldText : args.getMatch().group();
		builder.insertField(MessageFormat.format("TC \"{0}\" {1}", insertText, mFieldSwitches));
		return ReplaceAction.SKIP;
	}
}
@Test
public void cursorPosition() throws Exception
{
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Node curNode = builder.getCurrentNode();
	Paragraph curParagraph = builder.getCurrentParagraph();
	System.out.println("\nCursor move to paragraph: " + curParagraph.getText());
}
@Test
public void moveToNode() throws Exception
{
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Start a bookmark and add content to it using a DocumentBuilder.
	builder.startBookmark("MyBookmark");
	builder.writeln("Bookmark contents.");
	builder.endBookmark("MyBookmark");
	// The node that the DocumentBuilder is currently at is past the boundaries of the bookmark.
	Assert.assertEquals(doc.getRange().getBookmarks().get(0).getBookmarkEnd(), builder.getCurrentParagraph().getFirstChild());
	// If we wish to revise the content of our bookmark with the DocumentBuilder, we can move back to it like this.
	builder.moveToBookmark("MyBookmark");
	// Now we're located between the bookmark's BookmarkStart and BookmarkEnd nodes, so any text the builder adds will be within it.
	Assert.assertEquals(doc.getRange().getBookmarks().get(0).getBookmarkStart(), builder.getCurrentParagraph().getFirstChild());
	// We can move the builder to an individual node,
	// which in this case will be the first node of the first paragraph, like this.
	builder.moveTo(doc.getFirstSection().getBody().getFirstParagraph().getChildNodes(NodeType.ANY, false).get(0));
	Assert.assertEquals(NodeType.BOOKMARK_START, builder.getCurrentNode().getNodeType());
	Assert.assertTrue(builder.isAtStartOfParagraph());
	// A shorter way of moving the very start/end of a document is with these methods.
	builder.moveToDocumentEnd();
	Assert.assertTrue(builder.isAtEndOfParagraph());
	builder.moveToDocumentStart();
	Assert.assertTrue(builder.isAtStartOfParagraph());
}
@Test
public void moveToDocumentStartEnd() throws Exception
{
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Move the cursor position to the beginning of your document.
	builder.moveToDocumentStart();
	System.out.println("\nThis is the beginning of the document.");
	// Move the cursor position to the end of your document.
	builder.moveToDocumentEnd();
	System.out.println("\nThis is the end of the document.");
}
@Test
public void moveToSection() throws Exception
{
	Document doc = new Document();
	doc.appendChild(new Section(doc));
	// Move a DocumentBuilder to the second section and add text.
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.moveToSection(1);
	builder.writeln("Text added to the 2nd section.");
	// Create document with paragraphs.
	doc = new Document("Your Directory Path" + "Paragraphs.docx");
	ParagraphCollection paragraphs = doc.getFirstSection().getBody().getParagraphs();
	Assert.assertEquals(22, paragraphs.getCount());
	// When we create a DocumentBuilder for a document, its cursor is at the very beginning of the document by default,
	// and any content added by the DocumentBuilder will just be prepended to the document.
	builder = new DocumentBuilder(doc);
	Assert.assertEquals(0, paragraphs.indexOf(builder.getCurrentParagraph()));
	// You can move the cursor to any position in a paragraph.
	builder.moveToParagraph(2, 10);
	Assert.assertEquals(2, paragraphs.indexOf(builder.getCurrentParagraph()));
	builder.writeln("This is a new third paragraph. ");
	Assert.assertEquals(3, paragraphs.indexOf(builder.getCurrentParagraph()));
}
@Test
public void moveToHeadersFooters() throws Exception
{
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Specify that we want headers and footers different for first, even and odd pages.
	builder.getPageSetup().setDifferentFirstPageHeaderFooter(true);
	builder.getPageSetup().setOddAndEvenPagesHeaderFooter(true);
	// Create the headers.
	builder.moveToHeaderFooter(HeaderFooterType.HEADER_FIRST);
	builder.write("Header for the first page");
	builder.moveToHeaderFooter(HeaderFooterType.HEADER_EVEN);
	builder.write("Header for even pages");
	builder.moveToHeaderFooter(HeaderFooterType.HEADER_PRIMARY);
	builder.write("Header for all other pages");
	// Create two pages in the document.
	builder.moveToSection(0);
	builder.writeln("Page1");
	builder.insertBreak(BreakType.PAGE_BREAK);
	builder.writeln("Page2");
	doc.save("Your Directory Path" + "AddContentUsingDocumentBuilder.MoveToHeadersFooters.docx");
}
@Test
public void moveToParagraph() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Paragraphs.docx");
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.moveToParagraph(2, 0);
	builder.writeln("This is the 3rd paragraph.");
}
@Test
public void moveToTableCell() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Tables.docx");
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Move the builder to row 3, cell 4 of the first table.
	builder.moveToCell(0, 2, 3, 0);
	builder.write("\nCell contents added by DocumentBuilder");
	Table table = (Table)doc.getChild(NodeType.TABLE, 0, true);
	Assert.assertEquals(table.getRows().get(2).getCells().get(3), builder.getCurrentNode().getParentNode().getParentNode());
	Assert.assertEquals("Cell contents added by DocumentBuilderCell 3 contents", table.getRows().get(2).getCells().get(3).getText().trim());
}
@Test
public void moveToBookmarkEnd() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Bookmarks.docx");
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.moveToBookmark("MyBookmark1", false, true);
	builder.writeln("This is a bookmark.");
}
@Test
public void moveToMergeField() throws Exception
{
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Insert a field using the DocumentBuilder and add a run of text after it.
	Field field = builder.insertField("MERGEFIELD field");
	builder.write(" Text after the field.");
	// The builder's cursor is currently at end of the document.
	Assert.assertNull(builder.getCurrentNode());
	// We can move the builder to a field like this, placing the cursor at immediately after the field.
	builder.moveToField(field, true);
	// Note that the cursor is at a place past the FieldEnd node of the field, meaning that we are not actually inside the field.
	// If we wish to move the DocumentBuilder to inside a field,
	// we will need to move it to a field's FieldStart or FieldSeparator node using the DocumentBuilder.MoveTo() method.
	Assert.assertEquals(field.getEnd(), builder.getCurrentNode().getPreviousSibling());
	builder.write(" Text immediately after the field.");
```

## Conclusion

In this comprehensive guide, we have explored the capabilities of Aspose.Words for Java's DocumentBuilder to add various types of content to Word documents. We've covered text, tables, horizontal rules, form fields, HTML, hyperlinks, table of contents, images, paragraphs, and cursor movement.

## FAQ's

### Q: What is Aspose.Words for Java?

A: Aspose.Words for Java is a Java library that allows developers to create, modify, and manipulate Microsoft Word documents programmatically. It provides a wide range of features for document generation, formatting, and content insertion.

### Q: How can I add a table of contents to my document?

A: To add a table of contents, use the `DocumentBuilder` to insert a table of contents field into your document. Make sure to update the fields in the document after adding content to populate the table of contents. Here's an example:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insert a table of contents field
builder.insertTableOfContents("\\o \"1-3\" \\h \\z \\u");

// Add document content
// ...

// Update the table of contents
doc.updateFields();
```

### Q: How do I insert images into a document using Aspose.Words for Java?

A: You can insert images, both inline and floating, using the `DocumentBuilder`. Here are examples of both:

#### Inline Image:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insert an inline image
builder.insertImage("path/to/your/image.png");
```

#### Floating Image:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Insert a floating image
builder.insertImage("path/to/your/image.png", RelativeHorizontalPosition.MARGIN, 100.0, RelativeVerticalPosition.MARGIN, 100.0, 200.0, 100.0, WrapType.SQUARE);
```

### Q: Can I format text and paragraphs when adding content?

A: Yes, you can format text and paragraphs using the `DocumentBuilder`. You can set font properties, paragraph alignment, indentation, and more. Here's an example:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Set font and paragraph formatting
Font font = builder.getFont();
font.setSize(16.0);
font.setBold(true);
font.setColor(Color.BLUE);
font.setName("Arial");
font.setUnderline(Underline.DASH);

ParagraphFormat paragraphFormat = builder.getParagraphFormat();
paragraphFormat.setFirstLineIndent(8.0);
paragraphFormat.setAlignment(ParagraphAlignment.JUSTIFY);
paragraphFormat.setKeepTogether(true);

// Insert a formatted paragraph
builder.writeln("This is a formatted paragraph.");
```

### Q: How can I move the cursor to a specific location within the document?

A: You can control the cursor position using methods like `moveToParagraph`, `moveToCell`, and more. Here's an example:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Move the cursor to a specific paragraph
builder.moveToParagraph(2, 0);

// Add content at the new cursor position
builder.writeln("This is the 3rd paragraph.");
```

These are some common questions and answers to help you get started with Aspose.Words for Java's DocumentBuilder. If you have more questions or need further assistance, refer to the library's documentation or seek help from the Aspose.Words community and support resources.
