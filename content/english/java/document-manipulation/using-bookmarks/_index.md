---
title: Using Bookmarks in Aspose.Words for Java
linktitle: Using Bookmarks in Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: Optimize your document processing with Aspose.Words for Java. Learn to use bookmarks for efficient content navigation and manipulation in this step-by-step guide.
type: docs
weight: 17
url: /java/document-manipulation/using-bookmarks/
---

## Introduction to Using Bookmarks in Aspose.Words for Java

Bookmarks are a powerful feature in Aspose.Words for Java that allows you to mark and manipulate specific parts of a document. In this step-by-step guide, we will explore how to use bookmarks in Aspose.Words for Java to enhance your document processing. 

## Step 1: Creating a Bookmark

To create a bookmark, follow these steps:

```java
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Start the bookmark
builder.startBookmark("My Bookmark");
builder.writeln("Text inside a bookmark.");

// End the bookmark
builder.endBookmark("My Bookmark");
```

## Step 2: Accessing Bookmarks

You can access bookmarks in a document using their index or name. Here's how:

```java
Document doc = new Document("Your Directory Path" + "Bookmarks.docx");

// By index:
Bookmark bookmark1 = doc.getRange().getBookmarks().get(0);

// By name:
Bookmark bookmark2 = doc.getRange().getBookmarks().get("MyBookmark3");
```

## Step 3: Updating Bookmark Data

To update bookmark data, use the following code:

```java
Document doc = new Document("Your Directory Path" + "Bookmarks.docx");
Bookmark bookmark = doc.getRange().getBookmarks().get("MyBookmark1");
String name = bookmark.getName();
String text = bookmark.getText();
bookmark.setName("RenamedBookmark");
bookmark.setText("This is new bookmarked text.");
```

## Step 4: Working with Bookmarked Text

You can copy bookmarked text and add it to another document. Here's how:

```java
Document srcDoc = new Document("Your Directory Path" + "Bookmarks.docx");
Bookmark srcBookmark = srcDoc.getRange().getBookmarks().get("MyBookmark1");
Document dstDoc = new Document();
NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
appendBookmarkedText(importer, srcBookmark, dstDoc.getLastSection().getBody());
dstDoc.save("Your Directory Path" + "WorkingWithBookmarks.CopyBookmarkedText.docx");
```

## Step 5: Show and Hide Bookmarks

You can show or hide bookmarks in a document. Here's an example:

```java
Document doc = new Document("Your Directory Path" + "Bookmarks.docx");
showHideBookmarkedContent(doc, "MyBookmark1", false);
doc.save("Your Directory Path" + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

## Step 6: Untangling Row Bookmarks

Untangling row bookmarks allows you to work with them more effectively:

```java
Document doc = new Document("Your Directory Path" + "Table column bookmarks.docx");
untangle(doc);
deleteRowByBookmark(doc, "ROW2");
doc.save("Your Directory Path" + "WorkingWithBookmarks.UntangleRowBookmarks.docx");
```

## Complete Source Code For Using Bookmarks in Aspose.Words for Java

```java
	Document doc = new Document("Your Directory Path" + "Bookmarks.docx");
	// By index:
	Bookmark bookmark1 = doc.getRange().getBookmarks().get(0);
	// By name:
	Bookmark bookmark2 = doc.getRange().getBookmarks().get("MyBookmark3");
}
@Test
public void updateBookmarkData() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Bookmarks.docx");
	Bookmark bookmark = doc.getRange().getBookmarks().get("MyBookmark1");
	String name = bookmark.getName();
	String text = bookmark.getText();
	bookmark.setName("RenamedBookmark");
	bookmark.setText("This is a new bookmarked text.");
}
@Test
public void bookmarkTableColumns() throws Exception {
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.startTable();
	builder.insertCell();
	builder.startBookmark("MyBookmark");
	builder.write("This is row 1 cell 1");
	builder.insertCell();
	builder.write("This is row 1 cell 2");
	builder.endRow();
	builder.insertCell();
	builder.writeln("This is row 2 cell 1");
	builder.insertCell();
	builder.writeln("This is row 2 cell 2");
	builder.endRow();
	builder.endTable();
	builder.endBookmark("MyBookmark");
	for (Bookmark bookmark : doc.getRange().getBookmarks()) {
		System.out.println(MessageFormat.format("Bookmark: {0}{1}", bookmark.getName(), bookmark.isColumn() ? " (Column)" : ""));
		if (bookmark.isColumn()) {
			if (Row.class.isInstance(bookmark.getBookmarkStart().getAncestor(NodeType.ROW))) {
				Row row = (Row) bookmark.getBookmarkStart().getAncestor(NodeType.ROW);
				if (bookmark.getFirstColumn() < row.getCells().toArray().length) {
					System.out.println(row.getCells().get(bookmark.getFirstColumn()).getText().trim());
				}
			}
		}
	}
}
@Test
public void copyBookmarkedText() throws Exception
{
	Document srcDoc = new Document("Your Directory Path" + "Bookmarks.docx");
	// This is the bookmark whose content we want to copy.
	Bookmark srcBookmark = srcDoc.getRange().getBookmarks().get("MyBookmark1");
	// We will be adding to this document.
	Document dstDoc = new Document();
	// Let's say we will be appended to the end of the body of the last section.
	CompositeNode dstNode = dstDoc.getLastSection().getBody();
	// If you import multiple times without a single context, it will result in many styles created.
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.KEEP_SOURCE_FORMATTING);
	appendBookmarkedText(importer, srcBookmark, dstNode);
	dstDoc.save("Your Directory Path" + "WorkingWithBookmarks.CopyBookmarkedText.docx");
}
/// <summary>
/// Copies content of the bookmark and adds it to the end of the specified node.
/// The destination node can be in a different document.
/// </summary>
/// <param name="importer">Maintains the import context.</param>
/// <param name="srcBookmark">The input bookmark.</param>
/// <param name="dstNode">Must be a node that can contain paragraphs (such as a Story).</param>
private void appendBookmarkedText(NodeImporter importer, Bookmark srcBookmark, CompositeNode dstNode) throws Exception
{
	// This is the paragraph that contains the beginning of the bookmark.
	Paragraph startPara = (Paragraph) srcBookmark.getBookmarkStart().getParentNode();
	// This is the paragraph that contains the end of the bookmark.
	Paragraph endPara = (Paragraph) srcBookmark.getBookmarkEnd().getParentNode();
	if (startPara == null || endPara == null)
		throw new IllegalStateException(
			"Parent of the bookmark start or end is not a paragraph, cannot handle this scenario yet.");
	// Limit ourselves to a reasonably simple scenario.
	if (startPara.getParentNode() != endPara.getParentNode())
		throw new IllegalStateException(
			"Start and end paragraphs have different parents, cannot handle this scenario yet.");
	// We want to copy all paragraphs from the start paragraph up to (and including) the end paragraph,
	// therefore the node at which we stop is one after the end paragraph.
	Node endNode = endPara.getNextSibling();
	for (Node curNode = startPara; curNode != endNode; curNode = curNode.getNextSibling())
	{
		// This creates a copy of the current node and imports it (makes it valid) in the context
		// of the destination document. Importing means adjusting styles and list identifiers correctly.
		Node newNode = importer.importNode(curNode, true);
		dstNode.appendChild(newNode);
	}
}
@Test
public void createBookmark() throws Exception
{
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.startBookmark("My Bookmark");
	builder.writeln("Text inside a bookmark.");
	builder.startBookmark("Nested Bookmark");
	builder.writeln("Text inside a NestedBookmark.");
	builder.endBookmark("Nested Bookmark");
	builder.writeln("Text after Nested Bookmark.");
	builder.endBookmark("My Bookmark");
	PdfSaveOptions options = new PdfSaveOptions();
	options.getOutlineOptions().getBookmarksOutlineLevels().add("My Bookmark", 1);
	options.getOutlineOptions().getBookmarksOutlineLevels().add("Nested Bookmark", 2);
	doc.save("Your Directory Path" + "WorkingWithBookmarks.CreateBookmark.pdf", options);
}
@Test
public void showHideBookmarks() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Bookmarks.docx");
	showHideBookmarkedContent(doc, "MyBookmark1", false);
	doc.save("Your Directory Path" + "WorkingWithBookmarks.ShowHideBookmarks.docx");
}
private void showHideBookmarkedContent(Document doc, String bookmarkName, boolean showHide) throws Exception
{
	Bookmark bm = doc.getRange().getBookmarks().get(bookmarkName);
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.moveToDocumentEnd();
	// {IF "{MERGEFIELD bookmark}" = "true" "" ""}
	Field field = builder.insertField("IF \"", null);
	builder.moveTo(field.getStart().getNextSibling());
	builder.insertField("MERGEFIELD " + bookmarkName + "", null);
	builder.write("\" = \"true\" ");
	builder.write("\"");
	builder.write("\"");
	builder.write(" \"\"");
	Node currentNode = field.getStart();
	boolean flag = true;
	while (currentNode != null && flag)
	{
		if (currentNode.getNodeType() == NodeType.RUN)
			if ("\"".equals(currentNode.toString(SaveFormat.TEXT).trim()))
				flag = false;
		Node nextNode = currentNode.getNextSibling();
		bm.getBookmarkStart().getParentNode().insertBefore(currentNode, bm.getBookmarkStart());
		currentNode = nextNode;
	}
	Node endNode = bm.getBookmarkEnd();
	flag = true;
	while (currentNode != null && flag)
	{
		if (currentNode.getNodeType() == NodeType.FIELD_END)
			flag = false;
		Node nextNode = currentNode.getNextSibling();
		bm.getBookmarkEnd().getParentNode().insertAfter(currentNode, endNode);
		endNode = currentNode;
		currentNode = nextNode;
	}
	doc.getMailMerge().execute(new String[] { bookmarkName }, new Object[] { showHide });
}
@Test
public void untangleRowBookmarks() throws Exception
{
	Document doc = new Document("Your Directory Path" + "Table column bookmarks.docx");
	// This performs the custom task of putting the row bookmark ends into the same row with the bookmark starts.
	untangle(doc);
	// Now we can easily delete rows by a bookmark without damaging any other row's bookmarks.
	deleteRowByBookmark(doc, "ROW2");
	// This is just to check that the other bookmark was not damaged.
	if (doc.getRange().getBookmarks().get("ROW1").getBookmarkEnd() == null)
		throw new Exception("Wrong, the end of the bookmark was deleted.");
	doc.save("Your Directory Path" + "WorkingWithBookmarks.UntangleRowBookmarks.docx");
}
private void untangle(Document doc) throws Exception
{
	for (Bookmark bookmark : doc.getRange().getBookmarks())
	{
		// Get the parent row of both the bookmark and bookmark end node.
		Row row1 = (Row) bookmark.getBookmarkStart().getAncestor(Row.class);
		Row row2 = (Row) bookmark.getBookmarkEnd().getAncestor(Row.class);
		// If both rows are found okay, and the bookmark start and end are contained in adjacent rows,
		// move the bookmark end node to the end of the last paragraph in the top row's last cell.
		if (row1 != null && row2 != null && row1.getNextSibling() == row2)
			row1.getLastCell().getLastParagraph().appendChild(bookmark.getBookmarkEnd());
	}
}
private void deleteRowByBookmark(Document doc, String bookmarkName)
{
	Bookmark bookmark = doc.getRange().getBookmarks().get(bookmarkName);
	Row row = (Row) bookmark.getBookmarkStart().getAncestor(Row.class);
	row.remove();
```

## Conclusion

Using bookmarks in Aspose.Words for Java can greatly simplify document processing tasks. Whether you need to navigate, extract, or manipulate content, bookmarks provide a powerful mechanism to do so efficiently.

## FAQ's

### How do I create a bookmark in a table cell?

To create a bookmark in a table cell, use the `DocumentBuilder` class and start and end the bookmark within the cell.

### Can I copy a bookmark to another document?

Yes, you can copy a bookmark to another document using the `NodeImporter` class to ensure the formatting is preserved.

### How can I delete a row by its bookmark?

You can delete a row by its bookmark by first finding the bookmarked row and then removing it from the document.

### What are some common use cases for bookmarks?

Bookmarks are commonly used for generating table of contents, extracting specific content, and automating document generation processes.

### Where can I find more information about Aspose.Words for Java?

For detailed documentation and downloads, visit [Aspose.Words for Java Documentation](https://reference.aspose.com/words/java/).
