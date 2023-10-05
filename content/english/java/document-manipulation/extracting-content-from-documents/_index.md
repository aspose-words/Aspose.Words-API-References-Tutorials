---
title: Extracting Content from Documents in Aspose.Words for Java
linktitle: Extracting Content from Documents in Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: Learn how to extract content from documents with ease using Aspose.Words for Java. Our step-by-step guide and code samples simplify the process.
type: docs
weight: 13
url: /java/document-manipulation/extracting-content-from-documents/
---

## Introduction to Extracting Content from Documents in Aspose.Words for Java

In the world of document processing, extracting content from documents is a common requirement. Whether you need to extract text, tables, images, or specific document elements, Aspose.Words for Java provides powerful tools to make this task a breeze. In this comprehensive guide, we will walk you through the process of extracting content from documents using Aspose.Words for Java. 

## Prerequisites

Before we dive into the extraction process, make sure you have the following prerequisites in place:

1. Aspose.Words for Java: You should have Aspose.Words for Java installed and set up in your Java development environment. You can download it from [here](https://releases.aspose.com/words/java/).

2. A Document to Extract Content From: For this guide, we will use a sample document named "Extract content.docx." Make sure you have a similar document ready for extraction.

## Extracting Content Between Block-Level Nodes

```java
// Java code sample for extracting content between block-level nodes
Document doc = new Document("Your Directory Path" + "Extract content.docx");
Paragraph startPara = (Paragraph) doc.getLastSection().getChild(NodeType.PARAGRAPH, 2, true);
Table endTable = (Table) doc.getLastSection().getChild(NodeType.TABLE, 0, true);
ArrayList<Node> extractedNodes = ExtractContentHelper.extractContent(startPara, endTable, true);
Collections.reverse(extractedNodes);
while (extractedNodes.size() > 0) {
    endTable.getParentNode().insertAfter((Node) extractedNodes.get(0), endTable);
    extractedNodes.remove(0);
}
doc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenBlockLevelNodes.docx");
```

## Extracting Content Between Bookmarks

```java
// Java code sample for extracting content between bookmarks
Document doc = new Document("Your Directory Path" + "Extract content.docx");
Bookmark bookmark = doc.getRange().getBookmarks().get("Bookmark1");
BookmarkStart bookmarkStart = bookmark.getBookmarkStart();
BookmarkEnd bookmarkEnd = bookmark.getBookmarkEnd();
ArrayList<Node> extractedNodesInclusive = ExtractContentHelper.extractContent(bookmarkStart, bookmarkEnd, true);
Document dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodesInclusive);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenBookmark.IncludingBookmark.docx");
ArrayList<Node> extractedNodesExclusive = ExtractContentHelper.extractContent(bookmarkStart, bookmarkEnd, false);
dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodesExclusive);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenBookmark.WithoutBookmark.docx");
```

## Extracting Content Between Comment Ranges

```java
// Java code sample for extracting content between comment ranges
Document doc = new Document("Your Directory Path" + "Extract content.docx");
CommentRangeStart commentStart = (CommentRangeStart) doc.getChild(NodeType.COMMENT_RANGE_START, 0, true);
CommentRangeEnd commentEnd = (CommentRangeEnd) doc.getChild(NodeType.COMMENT_RANGE_END, 0, true);
ArrayList<Node> extractedNodesInclusive = ExtractContentHelper.extractContent(commentStart, commentEnd, true);
Document dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodesInclusive);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenCommentRange.IncludingComment.docx");
ArrayList<Node> extractedNodesExclusive = ExtractContentHelper.extractContent(commentStart, commentEnd, false);
dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodesExclusive);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenCommentRange.WithoutComment.docx");
```

## Extracting Content Between Paragraphs

```java
// Java code sample for extracting content between paragraphs
Document doc = new Document("Your Directory Path" + "Extract content.docx");
Paragraph startPara = (Paragraph) doc.getFirstSection().getBody().getChild(NodeType.PARAGRAPH, 6, true);
Paragraph endPara = (Paragraph) doc.getFirstSection().getBody().getChild(NodeType.PARAGRAPH, 10, true);
ArrayList<Node> extractedNodes = ExtractContentHelper.extractContent(startPara, endPara, true);
Document dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodes);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenParagraphs.docx");
```

## Extracting Content Between Paragraph Styles

```java
// Java code sample for extracting content between paragraph styles
Document doc = new Document("Your Directory Path" + "Extract content.docx");
ArrayList<Paragraph> parasStyleHeading1 = ExtractContentHelper.paragraphsByStyleName(doc, "Heading 1");
ArrayList<Paragraph> parasStyleHeading3 = ExtractContentHelper.paragraphsByStyleName(doc, "Heading 3");
Node startPara1 = parasStyleHeading1.get(0);
Node endPara1 = parasStyleHeading3.get(0);
ArrayList<Node> extractedNodes = ExtractContentHelper.extractContent(startPara1, endPara1, false);
Document dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodes);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenParagraphStyles.docx");
```

## Extracting Content Between Runs

```java
// Java code sample for extracting content between runs
Document doc = new Document("Your Directory Path" + "Extract content.docx");
Paragraph para = (Paragraph) doc.getChild(NodeType.PARAGRAPH, 7, true);
Run startRun = para.getRuns().get(1);
Run endRun = para.getRuns().get(4);
ArrayList<Node> extractedNodes = ExtractContentHelper.extractContent(startRun, endRun, true);
Node node = (Node) extractedNodes.get(0);
System.out.println(node.toString(SaveFormat.TEXT));
```

## Extracting Content Using DocumentVisitor

```java
// Java code sample for extracting content using DocumentVisitor
Document doc = new Document("Your Directory Path" + "Absolute position tab.docx");
MyDocToTxtWriter myConverter = new MyDocToTxtWriter();
doc.accept(myConverter);
System.out.println(myConverter.getText());
```

## Extracting Content Using Field

```java
// Java code sample for extracting content using Field
Document doc = new Document("Your Directory Path" + "Extract content.docx");
DocumentBuilder builder = new DocumentBuilder(doc);
builder.moveToMergeField("Fullname", false, false);
FieldStart startField = (FieldStart) builder.getCurrentNode();
Paragraph endPara = (Paragraph) doc.getFirstSection().getChild(NodeType.PARAGRAPH, 5, true);
ArrayList<Node> extractedNodes = ExtractContentHelper.extractContent(startField, endPara, false);
Document dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodes);
dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentUsingField.docx");
```

## Extracting Table of Contents

```java
// Java code sample for extracting table of contents
Document doc = new Document("Your Directory Path" + "Table of contents.docx");
for (Field field : doc.getRange().getFields()) {
    if (field.getType() == FieldType.FIELD_HYPERLINK) {
        FieldHyperlink hyperlink = (FieldHyperlink) field;
        if (hyperlink.getSubAddress() != null && hyperlink.getSubAddress().startsWith("_Toc")) {
            Paragraph tocItem = (Paragraph) field.getStart().getAncestor(NodeType.PARAGRAPH);
            System.out.println(tocItem.toString(SaveFormat.TEXT).trim());
            System.out.println("------------------");
            Bookmark bm = doc.getRange().getBookmarks().get(hyperlink.getSubAddress());
            Paragraph pointer = (Paragraph) bm.getBookmarkStart().getAncestor(NodeType.PARAGRAPH);
            System.out.println(pointer.toString(SaveFormat.TEXT));
        }
    }
}
```

## Extracting Text Only

```java
// Java code sample for extracting text only
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.insertField("MERGEFIELD Field");
System.out.println("GetText() Result: " + doc.getText());
System.out.println("ToString() Result: " + doc.toString(SaveFormat.TEXT));
```

## Extracting Content Based on Styles

```java
// Java code sample for extracting content based on styles
Document doc = new Document("Your Directory Path" + "Styles.docx");
final String PARA_STYLE = "Heading 1";
final String RUN_STYLE = "Intense Emphasis";
ArrayList<Paragraph> paragraphs = paragraphsByStyleName(doc, PARA_STYLE);
System.out.println("Paragraphs with \"{paraStyle}\" styles ({paragraphs.Count}):");
for (Paragraph paragraph : paragraphs)
    System.out.println(paragraph.toString(SaveFormat.TEXT));
ArrayList<Run> runs = runsByStyleName(doc, RUN_STYLE);
System.out.println("\nRuns with \"{runStyle}\" styles ({runs.Count}):");
for (Run run : runs)
    System.out.println(run.getRange().getText());
}

public ArrayList<Paragraph> paragraphsByStyleName(Document doc, String styleName) {
    ArrayList<Paragraph> paragraphsWithStyle = new ArrayList<Paragraph>();
    NodeCollection paragraphs = doc.getChildNodes(NodeType.PARAGRAPH, true);
    for (Paragraph paragraph : (Iterable<Paragraph>) paragraphs) {
        if (paragraph.getParagraphFormat().getStyle().getName().equals(styleName))
            paragraphsWithStyle.add(paragraph);
    }
    return paragraphsWithStyle;
}

public ArrayList<Run> runsByStyleName(Document doc, String styleName) {
    ArrayList<Run> runsWithStyle = new ArrayList<Run>();
    NodeCollection runs = doc.getChildNodes(NodeType.RUN, true);
    for (Run run : (Iterable<Run>) runs) {
        if (run.getFont().getStyle().getName().equals(styleName))
            runsWithStyle.add(run);
    }
    return runsWithStyle;
}
```

## Extracting and Printing Text

```java
// Java code sample for extracting and printing text
Document doc = new Document("Your Directory Path" + "Tables.docx");
Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
System.out.println("Contents of the table: ");
System.out.println(table.getRange().getText());
System.out.println("\nContents of the row: ");
System.out.println(table.getRows().get(1).getRange().getText());
System.out.println("\nContents of the cell: ");
System.out.println(table.getLastRow().getLastCell().getRange().getText());
```

## Extracting Images to Files

```java
// Java code sample for extracting images to files
Document doc = new Document("Your Directory Path" + "Images.docx");
NodeCollection shapes = doc.getChildNodes(NodeType.SHAPE, true);
int imageIndex = 0;
for (Shape shape : (Iterable<Shape>) shapes) {
    if (shape.hasImage()) {
        String imageFileName = MessageFormat.format("Image.ExportImages.{0}_{1}",
                imageIndex, FileFormatUtil.imageTypeToExtension(shape.getImageData().getImageType()));
        shape.getImageData().save("Your Directory Path" + imageFileName);
        imageIndex++;
    }
}
```

## Complete Source Code For Extracting Content from Documents in Aspose.Words for Java

```java
	Document doc = new Document("Your Directory Path" + "Extract content.docx");
	Paragraph startPara = (Paragraph) doc.getLastSection().getChild(NodeType.PARAGRAPH, 2, true);
	Table endTable = (Table) doc.getLastSection().getChild(NodeType.TABLE, 0, true);
	// Extract the content between these nodes in the document. Include these markers in the extraction.
	ArrayList<Node> extractedNodes = ExtractContentHelper.extractContent(startPara, endTable, true);
	// Let's reverse the array to make inserting the content back into the document easier.
	Collections.reverse(extractedNodes);
	while (extractedNodes.size() > 0) {
		// Insert the last node from the reversed list.
		endTable.getParentNode().insertAfter((Node) extractedNodes.get(0), endTable);
		// Remove this node from the list after insertion.
		extractedNodes.remove(0);
	}
	doc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenBlockLevelNodes.docx");
}
@Test
public void extractContentBetweenBookmark() throws Exception {
	Document doc = new Document("Your Directory Path" + "Extract content.docx");
	Section section = doc.getSections().get(0);
	section.getPageSetup().setLeftMargin(70.85);
	// Retrieve the bookmark from the document.
	Bookmark bookmark = doc.getRange().getBookmarks().get("Bookmark1");
	// We use the BookmarkStart and BookmarkEnd nodes as markers.
	BookmarkStart bookmarkStart = bookmark.getBookmarkStart();
	BookmarkEnd bookmarkEnd = bookmark.getBookmarkEnd();
	// Firstly, extract the content between these nodes, including the bookmark.
	ArrayList<Node> extractedNodesInclusive = ExtractContentHelper.extractContent(bookmarkStart, bookmarkEnd, true);
	Document dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodesInclusive);
	dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenBookmark.IncludingBookmark.docx");
	// Secondly, extract the content between these nodes this time without including the bookmark.
	ArrayList<Node> extractedNodesExclusive = ExtractContentHelper.extractContent(bookmarkStart, bookmarkEnd, false);
	dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodesExclusive);
	dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenBookmark.WithoutBookmark.docx");
}
@Test
public void extractContentBetweenCommentRange() throws Exception {
	Document doc = new Document("Your Directory Path" + "Extract content.docx");
	// This is a quick way of getting both comment nodes.
	// Your code should have a proper method of retrieving each corresponding start and end node.
	CommentRangeStart commentStart = (CommentRangeStart) doc.getChild(NodeType.COMMENT_RANGE_START, 0, true);
	CommentRangeEnd commentEnd = (CommentRangeEnd) doc.getChild(NodeType.COMMENT_RANGE_END, 0, true);
	// Firstly, extract the content between these nodes including the comment as well.
	ArrayList<Node> extractedNodesInclusive = ExtractContentHelper.extractContent(commentStart, commentEnd, true);
	Document dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodesInclusive);
	dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenCommentRange.IncludingComment.docx");
	// Secondly, extract the content between these nodes without the comment.
	ArrayList<Node> extractedNodesExclusive = ExtractContentHelper.extractContent(commentStart, commentEnd, false);
	dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodesExclusive);
	dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenCommentRange.WithoutComment.docx");
}
@Test
public void extractContentBetweenParagraphs() throws Exception {
	Document doc = new Document("Your Directory Path" + "Extract content.docx");
	Paragraph startPara = (Paragraph) doc.getFirstSection().getBody().getChild(NodeType.PARAGRAPH, 6, true);
	Paragraph endPara = (Paragraph) doc.getFirstSection().getBody().getChild(NodeType.PARAGRAPH, 10, true);
	// Extract the content between these nodes in the document. Include these markers in the extraction.
	ArrayList<Node> extractedNodes = ExtractContentHelper.extractContent(startPara, endPara, true);
	Document dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodes);
	dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenParagraphs.docx");
}
@Test
public void extractContentBetweenParagraphStyles() throws Exception {
	Document doc = new Document("Your Directory Path" + "Extract content.docx");
	// Gather a list of the paragraphs using the respective heading styles.
	ArrayList<Paragraph> parasStyleHeading1 = ExtractContentHelper.paragraphsByStyleName(doc, "Heading 1");
	ArrayList<Paragraph> parasStyleHeading3 = ExtractContentHelper.paragraphsByStyleName(doc, "Heading 3");
	// Use the first instance of the paragraphs with those styles.
	Node startPara1 = parasStyleHeading1.get(0);
	Node endPara1 = parasStyleHeading3.get(0);
	// Extract the content between these nodes in the document. Don't include these markers in the extraction.
	ArrayList<Node> extractedNodes = ExtractContentHelper.extractContent(startPara1, endPara1, false);
	Document dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodes);
	dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentBetweenParagraphStyles.docx");
}
@Test
public void extractContentBetweenRuns() throws Exception {
	Document doc = new Document("Your Directory Path" + "Extract content.docx");
	Paragraph para = (Paragraph) doc.getChild(NodeType.PARAGRAPH, 7, true);
	Run startRun = para.getRuns().get(1);
	Run endRun = para.getRuns().get(4);
	// Extract the content between these nodes in the document. Include these markers in the extraction.
	ArrayList<Node> extractedNodes = ExtractContentHelper.extractContent(startRun, endRun, true);
	Node node = (Node) extractedNodes.get(0);
	System.out.println(node.toString(SaveFormat.TEXT));
}
@Test
public void extractContentUsingDocumentVisitor() throws Exception {
	Document doc = new Document("Your Directory Path" + "Absolute position tab.docx");
	MyDocToTxtWriter myConverter = new MyDocToTxtWriter();
	// This is the well known Visitor pattern. Get the model to accept a visitor.
	// The model will iterate through itself by calling the corresponding methods.
	// On the visitor object (this is called visiting). 
	// Note that every node in the object model has the accept method so the visiting
	// can be executed not only for the whole document, but for any node in the document.
	doc.accept(myConverter);
	// Once the visiting is complete, we can retrieve the result of the operation,
	// That in this example, has accumulated in the visitor.
	System.out.println(myConverter.getText());
}
/// <summary>
/// Simple implementation of saving a document in the plain text format. Implemented as a Visitor.
/// </summary>
static class MyDocToTxtWriter extends DocumentVisitor {
	public MyDocToTxtWriter() {
		mIsSkipText = false;
		mBuilder = new StringBuilder();
	}
	/// <summary>
	/// Gets the plain text of the document that was accumulated by the visitor.
	/// </summary>
	public String getText() {
		return mBuilder.toString();
	}
	/// <summary>
	/// Called when a Run node is encountered in the document.
	/// </summary>
	public /*override*/ /*VisitorAction*/int visitRun(Run run) {
		appendText(run.getText());
		// Let the visitor continue visiting other nodes.
		return VisitorAction.CONTINUE;
	}
	/// <summary>
	/// Called when a FieldStart node is encountered in the document.
	/// </summary>
	public /*override*/ /*VisitorAction*/int visitFieldStart(FieldStart fieldStart) {
		// In Microsoft Word, a field code (such as "MERGEFIELD FieldName") follows
		// after a field start character. We want to skip field codes and output field.
		// Result only, therefore we use a flag to suspend the output while inside a field code.
		// Note this is a very simplistic implementation and will not work very well.
		// If you have nested fields in a document.
		mIsSkipText = true;
		return VisitorAction.CONTINUE;
	}
	/// <summary>
	/// Called when a FieldSeparator node is encountered in the document.
	/// </summary>
	public /*override*/ /*VisitorAction*/int visitFieldSeparator(FieldSeparator fieldSeparator) {
		// Once reached a field separator node, we enable the output because we are
		// now entering the field result nodes.
		mIsSkipText = false;
		return VisitorAction.CONTINUE;
	}
	/// <summary>
	/// Called when a FieldEnd node is encountered in the document.
	/// </summary>
	public /*override*/ /*VisitorAction*/int visitFieldEnd(FieldEnd fieldEnd) {
		// Make sure we enable the output when reached a field end because some fields
		// do not have field separator and do not have field result.
		mIsSkipText = false;
		return VisitorAction.CONTINUE;
	}
	/// <summary>
	/// Called when visiting of a Paragraph node is ended in the document.
	/// </summary>
	public /*override*/ /*VisitorAction*/int visitParagraphEnd(Paragraph paragraph) {
		// When outputting to plain text we output Cr+Lf characters.
		appendText(ControlChar.CR_LF);
		return VisitorAction.CONTINUE;
	}
	public /*override*/ /*VisitorAction*/int visitBodyStart(Body body) {
		// We can detect beginning and end of all composite nodes such as Section, Body, 
		// Table, Paragraph etc and provide custom handling for them.
		mBuilder.append("* Body Started *\r\n");
		return VisitorAction.CONTINUE;
	}
	public /*override*/ /*VisitorAction*/int visitBodyEnd(Body body) {
		mBuilder.append("* Body Ended *\r\n");
		return VisitorAction.CONTINUE;
	}
	/// <summary>
	/// Called when a HeaderFooter node is encountered in the document.
	/// </summary>
	public /*override*/ /*VisitorAction*/int visitHeaderFooterStart(HeaderFooter headerFooter) {
		// Returning this value from a visitor method causes visiting of this
		// Node to stop and move on to visiting the next sibling node
		// The net effect in this example is that the text of headers and footers
		// Is not included in the resulting output
		return VisitorAction.SKIP_THIS_NODE;
	}
	/// <summary>
	/// Adds text to the current output. Honors the enabled/disabled output flag.
	/// </summary>
	private void appendText(String text) {
		if (!mIsSkipText)
			mBuilder.append(text);
	}
	private /*final*/ StringBuilder mBuilder;
	private boolean mIsSkipText;
}
@Test
public void extractContentUsingField() throws Exception {
	Document doc = new Document("Your Directory Path" + "Extract content.docx");
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Pass the first boolean parameter to get the DocumentBuilder to move to the FieldStart of the field.
	// We could also get FieldStarts of a field using GetChildNode method as in the other examples.
	builder.moveToMergeField("Fullname", false, false);
	// The builder cursor should be positioned at the start of the field.
	FieldStart startField = (FieldStart) builder.getCurrentNode();
	Paragraph endPara = (Paragraph) doc.getFirstSection().getChild(NodeType.PARAGRAPH, 5, true);
	// Extract the content between these nodes in the document. Don't include these markers in the extraction.
	ArrayList<Node> extractedNodes = ExtractContentHelper.extractContent(startField, endPara, false);
	Document dstDoc = ExtractContentHelper.generateDocument(doc, extractedNodes);
	dstDoc.save("Your Directory Path" + "ExtractContent.ExtractContentUsingField.docx");
}
@Test
public void extractTableOfContents() throws Exception {
	Document doc = new Document("Your Directory Path" + "Table of contents.docx");
	for (Field field : doc.getRange().getFields()) {
		if (field.getType() == FieldType.FIELD_HYPERLINK) {
			FieldHyperlink hyperlink = (FieldHyperlink) field;
			if (hyperlink.getSubAddress() != null && hyperlink.getSubAddress().startsWith("_Toc")) {
				Paragraph tocItem = (Paragraph) field.getStart().getAncestor(NodeType.PARAGRAPH);
				System.out.println(tocItem.toString(SaveFormat.TEXT).trim());
				System.out.println("------------------");
				Bookmark bm = doc.getRange().getBookmarks().get(hyperlink.getSubAddress());
				Paragraph pointer = (Paragraph) bm.getBookmarkStart().getAncestor(NodeType.PARAGRAPH);
				System.out.println(pointer.toString(SaveFormat.TEXT));
			}
		}
	}
}
@Test
public void extractTextOnly() throws Exception {
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.insertField("MERGEFIELD Field");
	System.out.println("GetText() Result: " + doc.getText());
	// When converted to text it will not retrieve fields code or special characters,
	// but will still contain some natural formatting characters such as paragraph markers etc. 
	// This is the same as "viewing" the document as if it was opened in a text editor.
	System.out.println("ToString() Result: " + doc.toString(SaveFormat.TEXT));
}
@Test
public void extractContentBasedOnStyles() throws Exception {
	Document doc = new Document("Your Directory Path" + "Styles.docx");
	final String PARA_STYLE = "Heading 1";
	final String RUN_STYLE = "Intense Emphasis";
	ArrayList<Paragraph> paragraphs = paragraphsByStyleName(doc, PARA_STYLE);
	System.out.println("Paragraphs with \"{paraStyle}\" styles ({paragraphs.Count}):");
	for (Paragraph paragraph : paragraphs)
		System.out.println(paragraph.toString(SaveFormat.TEXT));
	ArrayList<Run> runs = runsByStyleName(doc, RUN_STYLE);
	System.out.println("\nRuns with \"{runStyle}\" styles ({runs.Count}):");
	for (Run run : runs)
		System.out.println(run.getRange().getText());
}
public ArrayList<Paragraph> paragraphsByStyleName(Document doc, String styleName) {
	ArrayList<Paragraph> paragraphsWithStyle = new ArrayList<Paragraph>();
	NodeCollection paragraphs = doc.getChildNodes(NodeType.PARAGRAPH, true);
	for (Paragraph paragraph : (Iterable<Paragraph>) paragraphs) {
		if (paragraph.getParagraphFormat().getStyle().getName().equals(styleName))
			paragraphsWithStyle.add(paragraph);
	}
	return paragraphsWithStyle;
}
public ArrayList<Run> runsByStyleName(Document doc, String styleName) {
	ArrayList<Run> runsWithStyle = new ArrayList<Run>();
	NodeCollection runs = doc.getChildNodes(NodeType.RUN, true);
	for (Run run : (Iterable<Run>) runs) {
		if (run.getFont().getStyle().getName().equals(styleName))
			runsWithStyle.add(run);
	}
	return runsWithStyle;
}
@Test
public void extractPrintText() throws Exception {
	Document doc = new Document("Your Directory Path" + "Tables.docx");
	Table table = (Table) doc.getChild(NodeType.TABLE, 0, true);
	// The range text will include control characters such as "\a" for a cell.
	// You can call ToString and pass SaveFormat.Text on the desired node to find the plain text content.
	System.out.println("Contents of the table: ");
	System.out.println(table.getRange().getText());
	System.out.println("\nContents of the row: ");
	System.out.println(table.getRows().get(1).getRange().getText());
	System.out.println("\nContents of the cell: ");
	System.out.println(table.getLastRow().getLastCell().getRange().getText());
}
@Test
public void extractImagesToFiles() throws Exception {
	Document doc = new Document("Your Directory Path" + "Images.docx");
	NodeCollection shapes = doc.getChildNodes(NodeType.SHAPE, true);
	int imageIndex = 0;
	for (Shape shape : (Iterable<Shape>) shapes) {
		if (shape.hasImage()) {
			String imageFileName =
					MessageFormat.format("Image.ExportImages.{0}_{1}", imageIndex, FileFormatUtil.imageTypeToExtension(shape.getImageData().getImageType()));
			shape.getImageData().save("Your Directory Path" + imageFileName);
			imageIndex++;
		}
	}
```

## Conclusion

Congratulations! You have learned how to extract content from documents using Aspose.Words for Java. This guide covered various extraction techniques, including content between block-level nodes, bookmarks, comment ranges, paragraphs, and more. You are now equipped to handle document content extraction efficiently in your Java applications.

## FAQ's

### How do I extract content from specific document sections?

To extract content from specific document sections, you can identify the starting and ending points of the sections and use the appropriate Aspose.Words for Java methods to extract content between them.

### Can I extract content from password-protected documents?

Yes, Aspose.Words for Java provides functionality to extract content from password-protected documents. You can provide the password when opening the document using the `Document` class constructor.

### How can I extract content and save it in different formats, such as plain text or HTML?

You can extract content from a document and save it in different formats using Aspose.Words for Java. After extracting the content, you can use the `Document` class methods to save it in formats like plain text, HTML, or others.

### Is there a way to extract content from specific document elements, such as tables or images?

Yes, you can extract content from specific document elements, such as tables or images, using Aspose.Words for Java. Identify the elements you want to extract, and then use the appropriate methods to extract their content.

### How can I automate the content extraction process in my Java application?

To automate the content extraction process in your Java application, you can create custom code based on the techniques described in this guide. You can also implement logic to iterate through multiple documents and extract content as needed.
