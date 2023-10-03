---
title: Removing Content from Documents in Aspose.Words for Java
linktitle: Removing Content from Documents in Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: Learn how to remove content from Word documents in Java using Aspose.Words for Java. Remove page breaks, section breaks, and more. Optimize your document processing.
type: docs
weight: 16
url: /java/document-manipulation/removing-content-from-documents/
---

## Introduction to Aspose.Words for Java

Before we dive into the removal techniques, let's briefly introduce Aspose.Words for Java. It is a Java API that provides extensive features for working with Word documents. You can create, edit, convert, and manipulate Word documents seamlessly using this library.

## Removing Page Breaks

Page breaks are often used to control the layout of a document. However, there might be cases where you need to remove them. Here's how you can remove page breaks using Aspose.Words for Java:

```java
Document doc = new Document(getMyDir() + "Document.docx");
NodeCollection paragraphs = doc.getChildNodes(NodeType.PARAGRAPH, true);
for (Paragraph para : (Iterable<Paragraph>) paragraphs) {
    if (para.getParagraphFormat().getPageBreakBefore()) {
        para.getParagraphFormat().setPageBreakBefore(false);
    }
    for (Run run : para.getRuns()) {
        if (run.getText().contains(ControlChar.PAGE_BREAK)) {
            run.setText(run.getText().replace(ControlChar.PAGE_BREAK, ""));
        }
    }
}
doc.save(getArtifactsDir() + "RemoveContent.RemovePageBreaks.docx");
```

This code snippet will iterate through paragraphs in the document, checking for page breaks and removing them.

## Removing Section Breaks

Section breaks divide a document into separate sections with different formatting. To remove section breaks, follow these steps:

```java
for (int i = doc.getSections().getCount() - 2; i >= 0; i--) {
    doc.getLastSection().prependContent(doc.getSections().get(i));
    doc.getSections().get(i).remove();
}
```

This code iterates through sections in reverse order, combining the content of the current section with the last one and then removing the copied section.

## Removing Footers

Footers in Word documents often contain page numbers, dates, or other information. If you need to remove them, you can use the following code:

```java
Document doc = new Document(getMyDir() + "Header and footer types.docx");
for (Section section : doc.getSections()) {
    HeaderFooter footer = section.getHeadersFooters().getByHeaderFooterType(HeaderFooterType.FOOTER_FIRST);
    footer.remove();
    footer = section.getHeadersFooters().getByHeaderFooterType(HeaderFooterType.FOOTER_PRIMARY);
    footer.remove();
    footer = section.getHeadersFooters().getByHeaderFooterType(HeaderFooterType.FOOTER_EVEN);
    footer.remove();
}
doc.save(getArtifactsDir() + "RemoveContent.RemoveFooters.docx");
```

This code removes all types of footers (first, primary, and even) from each section in the document.

## Removing Table of Contents

Table of contents (TOC) fields generate a dynamic table that lists headings and their page numbers. To remove a TOC, you can use the following code:

```java
Document doc = new Document(getMyDir() + "Table of contents.docx");
removeTableOfContents(doc, 0);
doc.save(getArtifactsDir() + "RemoveContent.RemoveToc.doc");
```

This code defines a method `removeTableOfContents` that removes the specified TOC from the document.

## Complete Source Code For Removing Content from Documents in Aspose.Words for Java

```java
	Document doc = new Document(getMyDir() + "Document.docx");
	// In Aspose.Words section breaks are represented as separate Section nodes in the document.
	// To remove these separate sections, the sections are combined.
	removePageBreaks(doc);
	removeSectionBreaks(doc);
	doc.save(getArtifactsDir() + "RemoveContent.RemovePageBreaks.docx");
}
private void removePageBreaks(Document doc)
{
	NodeCollection paragraphs = doc.getChildNodes(NodeType.PARAGRAPH, true);
	for (Paragraph para : (Iterable<Paragraph>) paragraphs)
	{
		// If the paragraph has a page break before the set, then clear it.
		if (para.getParagraphFormat().getPageBreakBefore())
			para.getParagraphFormat().setPageBreakBefore(false);
		// Check all runs in the paragraph for page breaks and remove them.
		for (Run run : para.getRuns())
		{
			if (run.getText().contains(ControlChar.PAGE_BREAK))
				run.setText(run.getText().replace(ControlChar.PAGE_BREAK, ""));
		}
	}
}
private void removeSectionBreaks(Document doc)
{
	// Loop through all sections starting from the section that precedes the last one and moving to the first section.
	for (int i = doc.getSections().getCount() - 2; i >= 0; i--)
	{
		// Copy the content of the current section to the beginning of the last section.
		doc.getLastSection().prependContent(doc.getSections().get(i));
		// Remove the copied section.
		doc.getSections().get(i).remove();
	}
}
@Test
public void removeFooters() throws Exception
{
	Document doc = new Document(getMyDir() + "Header and footer types.docx");
	for (Section section : doc.getSections())
	{
		// Up to three different footers are possible in a section (for first, even and odd pages)
		// we check and delete all of them.
		HeaderFooter footer = section.getHeadersFooters().getByHeaderFooterType(HeaderFooterType.FOOTER_FIRST);
		footer.remove();
		// Primary footer is the footer used for odd pages.
		footer = section.getHeadersFooters().getByHeaderFooterType(HeaderFooterType.FOOTER_PRIMARY);
		footer.remove();
		footer = section.getHeadersFooters().getByHeaderFooterType(HeaderFooterType.FOOTER_EVEN);
		footer.remove();
	}
	doc.save(getArtifactsDir() + "RemoveContent.RemoveFooters.docx");
}
@Test
public void removeToc() throws Exception
{
	Document doc = new Document(getMyDir() + "Table of contents.docx");
	// Remove the first table of contents from the document.
	removeTableOfContents(doc, 0);
	doc.save(getArtifactsDir() + "RemoveContent.RemoveToc.doc");
}
/// <summary>
/// Removes the specified table of contents field from the document.
/// </summary>
/// <param name="doc">The document to remove the field from.</param>
/// <param name="index">The zero-based index of the TOC to remove.</param>
private void removeTableOfContents(Document doc, int index)
{
	// Store the FieldStart nodes of TOC fields in the document for quick access.
	ArrayList<FieldStart> fieldStarts = new ArrayList<>();
	// This is a list to store the nodes found inside the specified TOC. They will be removed at the end of this method.
	ArrayList<Node> nodeList = new ArrayList<>();
	for (FieldStart start : (Iterable<FieldStart>) doc.getChildNodes(NodeType.FIELD_START, true))
	{
		if (start.getFieldType() == FieldType.FIELD_TOC)
		{
			fieldStarts.add(start);
		}
	}
	// Ensure the TOC specified by the passed index exists.
	if (index > fieldStarts.size() - 1)
		throw new IllegalArgumentException("Specified argument was out of the range of valid values.\r\nParameter name: " + "TOC index is out of range");
	boolean isRemoving = true;
	Node currentNode = fieldStarts.get(index);
	while (isRemoving)
	{
		// It is safer to store these nodes and delete them all at once later.
		nodeList.add(currentNode);
		currentNode = currentNode.nextPreOrder(doc);
		// Once we encounter a FieldEnd node of type FieldTOC,
		// we know we are at the end of the current TOC and stop here.
		if (currentNode.getNodeType() == NodeType.FIELD_END)
		{
			FieldEnd fieldEnd = (FieldEnd) currentNode;
			if (fieldEnd.getFieldType() == FieldType.FIELD_TOC)
				isRemoving = false;
		}
	}
	for (Node node : nodeList)
	{
		node.remove();
	}
```

## Conclusion

In this article, we've explored how to remove various types of content from Word documents using Aspose.Words for Java. Whether it's page breaks, section breaks, footers, or table of contents, Aspose.Words provides the tools to manipulate your documents effectively.

## FAQ's

### How can I remove specific page breaks?

To remove specific page breaks, iterate through the paragraphs in your document and clear the page break attribute for the desired paragraphs.

### Can I remove headers along with footers?

Yes, you can remove both headers and footers from your document by following a similar approach as shown in the article for footers.

### Is Aspose.Words for Java compatible with the latest Word document formats?

Yes, Aspose.Words for Java supports the latest Word document formats, ensuring compatibility with modern documents.

### What other document manipulation features does Aspose.Words for Java offer?

Aspose.Words for Java offers a wide range of features, including document creation, editing, conversion, and more. You can explore its documentation for detailed information.
