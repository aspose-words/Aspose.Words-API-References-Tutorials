---
title: Cloning and Combining Documents in Aspose.Words for Java
linktitle: Cloning and Combining Documents in Aspose.Words for Java
second_title: Aspose.Words Java Document Processing API
description: Learn how to clone and combine documents in Aspose.Words for Java. Step-by-step guide with source code examples.
type: docs
weight: 27
url: /java/document-manipulation/cloning-and-combining-documents/
---

## Introduction to Cloning and Combining Documents in Aspose.Words for Java

In this tutorial, we will explore how to clone and combine documents using Aspose.Words for Java. We'll cover various scenarios, including cloning a document, inserting documents at replace points, bookmarks, and during mail merge operations.

## Step 1: Cloning a Document

To clone a document in Aspose.Words for Java, you can use the `deepClone()` method. Here's a simple example:

```java
Document doc = new Document(getMyDir() + "Document.docx");
Document clone = doc.deepClone();
clone.save(getArtifactsDir() + "CloneAndCombineDocuments.CloningDocument.docx");
```

This code will create a deep clone of the original document and save it as a new file.

## Step 2: Inserting Documents at Replace Points

You can insert documents at specific replace points in another document. Here's how you can do it:

```java
Document mainDoc = new Document(getMyDir() + "Document insertion 1.docx");
FindReplaceOptions options = new FindReplaceOptions();
options.setDirection(FindReplaceDirection.BACKWARD);
options.setReplacingCallback(new InsertDocumentAtReplaceHandler());
mainDoc.getRange().replace(Pattern.compile("\\[MY_DOCUMENT\\]"), "", options);
mainDoc.save(getArtifactsDir() + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
```

In this example, we use a `FindReplaceOptions` object to specify a callback handler for the replacement. The `InsertDocumentAtReplaceHandler` class handles the insertion logic.

## Step 3: Inserting Documents at Bookmarks

To insert a document at a specific bookmark in another document, you can use the following code:

```java
Document mainDoc = new Document(getMyDir() + "Document insertion 1.docx");
Document subDoc = new Document(getMyDir() + "Document insertion 2.docx");
Bookmark bookmark = mainDoc.getRange().getBookmarks().get("insertionPlace");
insertDocument(bookmark.getBookmarkStart().getParentNode(), subDoc);
mainDoc.save(getArtifactsDir() + "CloneAndCombineDocuments.InsertDocumentAtBookmark.docx");
```

Here, we find the bookmark by name and use the `insertDocument` method to insert the content of the `subDoc` document at the bookmark location.

## Step 4: Inserting Documents During Mail Merge

You can insert documents during a mail merge operation in Aspose.Words for Java. Here's how:

```java
Document mainDoc = new Document(getMyDir() + "Document insertion 1.docx");
mainDoc.getMailMerge().setFieldMergingCallback(new InsertDocumentAtMailMergeHandler());
mainDoc.getMailMerge().execute(new String[] { "Document_1" }, new Object[] { getMyDir() + "Document insertion 2.docx" });
mainDoc.save(getArtifactsDir() + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
```

In this example, we set a field merging callback using the `InsertDocumentAtMailMergeHandler` class to handle the insertion of the document specified by the "Document_1" field.

## Complete Source Code For Cloning and Combining Documents in Aspose.Words for Java

```java
	Document doc = new Document(getMyDir() + "Document.docx");
	Document clone = doc.deepClone();
	clone.save(getArtifactsDir() + "CloneAndCombineDocuments.CloningDocument.docx");
}
@Test
public void insertDocumentAtReplace() throws Exception
{
	Document mainDoc = new Document(getMyDir() + "Document insertion 1.docx");
	// Set find and replace options.
	FindReplaceOptions options = new FindReplaceOptions();
	{
		options.setDirection(FindReplaceDirection.BACKWARD); 
		options.setReplacingCallback(new InsertDocumentAtReplaceHandler());
	}
	// Call the replace method.
	mainDoc.getRange().replace(Pattern.compile("\\[MY_DOCUMENT\\]"), "", options);
	mainDoc.save(getArtifactsDir() + "CloneAndCombineDocuments.InsertDocumentAtReplace.docx");
}
@Test
public void insertDocumentAtBookmark() throws Exception
{
	Document mainDoc = new Document(getMyDir() + "Document insertion 1.docx");
	Document subDoc = new Document(getMyDir() + "Document insertion 2.docx");
	Bookmark bookmark = mainDoc.getRange().getBookmarks().get("insertionPlace");
	insertDocument(bookmark.getBookmarkStart().getParentNode(), subDoc);
	mainDoc.save(getArtifactsDir() + "CloneAndCombineDocuments.InsertDocumentAtBookmark.docx");
}
@Test
public void insertDocumentAtMailMerge() throws Exception
{
	Document mainDoc = new Document(getMyDir() + "Document insertion 1.docx");
	mainDoc.getMailMerge().setFieldMergingCallback(new InsertDocumentAtMailMergeHandler());
	// The main document has a merge field in it called "Document_1".
	// The corresponding data for this field contains a fully qualified path to the document.
	// That should be inserted to this field.
	mainDoc.getMailMerge().execute(new String[] { "Document_1" }, new Object[] { getMyDir() + "Document insertion 2.docx" });
	mainDoc.save(getArtifactsDir() + "CloneAndCombineDocuments.InsertDocumentAtMailMerge.doc");
}
/// <summary>
/// Inserts content of the external document after the specified node.
/// Section breaks and section formatting of the inserted document are ignored.
/// </summary>
/// <param name="insertionDestination">Node in the destination document after which the content
/// Should be inserted. This node should be a block level node (paragraph or table).</param>
/// <param name="docToInsert">The document to insert.</param>
private static void insertDocument(Node insertionDestination, Document docToInsert)
{
	if (insertionDestination.getNodeType() == NodeType.PARAGRAPH || insertionDestination.getNodeType() == NodeType.TABLE)
	{
		CompositeNode destinationParent = insertionDestination.getParentNode();
		NodeImporter importer =
			new NodeImporter(docToInsert, insertionDestination.getDocument(), ImportFormatMode.KEEP_SOURCE_FORMATTING);
		// Loop through all block-level nodes in the section's body,
		// then clone and insert every node that is not the last empty paragraph of a section.
		for (Section srcSection : docToInsert.getSections())
		for (Node srcNode : srcSection.getBody())
		{
			if (srcNode.getNodeType() == NodeType.PARAGRAPH)
			{
				Paragraph para = (Paragraph)srcNode;
				if (para.isEndOfSection() && !para.hasChildNodes())
					continue;
			}
			Node newNode = importer.importNode(srcNode, true);
			destinationParent.insertAfter(newNode, insertionDestination);
			insertionDestination = newNode;
		}
	}
	else
	{
		throw new IllegalArgumentException("The destination node should be either a paragraph or table.");
	}
}
/// <summary>
/// Inserts content of the external document after the specified node.
/// </summary>
/// <param name="insertAfterNode">Node in the destination document after which the content
/// Should be inserted. This node should be a block level node (paragraph or table).</param>
/// <param name="srcDoc">The document to insert.</param>
private void insertDocumentWithSectionFormatting(Node insertAfterNode, Document srcDoc)
{
	if (insertAfterNode.getNodeType() != NodeType.PARAGRAPH &&
		insertAfterNode.getNodeType() != NodeType.TABLE)
		throw new IllegalArgumentException("The destination node should be either a paragraph or table.");
	Document dstDoc = (Document) insertAfterNode.getDocument();
	// To retain section formatting, split the current section into two at the marker node and then import the content
	// from srcDoc as whole sections. The section of the node to which the insert marker node belongs.
	Section currentSection = (Section) insertAfterNode.getAncestor(NodeType.SECTION);
	// Don't clone the content inside the section, we just want the properties of the section retained.
	Section cloneSection = (Section) currentSection.deepClone(false);
	// However, make sure the clone section has a body but no empty first paragraph.
	cloneSection.ensureMinimum();
	cloneSection.getBody().getFirstParagraph().remove();
	insertAfterNode.getDocument().insertAfter(cloneSection, currentSection);
	// Append all nodes after the marker node to the new section. This will split the content at the section level at.
	// The marker so the sections from the other document can be inserted directly.
	Node currentNode = insertAfterNode.getNextSibling();
	while (currentNode != null)
	{
		Node nextNode = currentNode.getNextSibling();
		cloneSection.getBody().appendChild(currentNode);
		currentNode = nextNode;
	}
	// This object will be translating styles and lists during the import.
	NodeImporter importer = new NodeImporter(srcDoc, dstDoc, ImportFormatMode.USE_DESTINATION_STYLES);
	for (Section srcSection : (Iterable<Section>) srcDoc.getSections())
	{
		Node newNode = importer.importNode(srcSection, true);
		dstDoc.insertAfter(newNode, currentSection);
		currentSection = (Section) newNode;
	}
}
private static class InsertDocumentAtMailMergeHandler implements IFieldMergingCallback
{
	// This handler makes special processing for the "Document_1" field.
	// The field value contains the path to load the document. 
	// We load the document and insert it into the current merge field.
	public void /*IFieldMergingCallback.*/fieldMerging(FieldMergingArgs args) throws Exception
	{
		if ("Document_1".equals(args.getDocumentFieldName()))
		{
			// Use document builder to navigate to the merge field with the specified name.
			DocumentBuilder builder = new DocumentBuilder(args.getDocument());
			builder.moveToMergeField(args.getDocumentFieldName());
			// The name of the document to load and insert is stored in the field value.
			Document subDoc = new Document((String)args.getFieldValue());
			insertDocument(builder.getCurrentParagraph(), subDoc);
			// The paragraph that contained the merge field might be empty now, and you probably want to delete it.
			if (!builder.getCurrentParagraph().hasChildNodes())
				builder.getCurrentParagraph().remove();
			// Indicate to the mail merge engine that we have inserted what we wanted.
			args.setText(null);
		}
	}
	public void /*IFieldMergingCallback.*/imageFieldMerging(ImageFieldMergingArgs args)
	{
		// Do nothing.
	}
}
private static class InsertDocumentAtMailMergeBlobHandler implements IFieldMergingCallback
{
	/// <summary>
	/// This handler makes special processing for the "Document_1" field.
	/// The field value contains the path to load the document.
	/// We load the document and insert it into the current merge field.
	/// </summary>
	public void /*IFieldMergingCallback.*/fieldMerging(FieldMergingArgs e) throws Exception
	{
		if ("Document_1".equals(e.getDocumentFieldName()))
		{
			DocumentBuilder builder = new DocumentBuilder(e.getDocument());
			builder.moveToMergeField(e.getDocumentFieldName());
			ByteArrayInputStream stream = new ByteArrayInputStream((byte[]) e.getFieldValue());
			Document subDoc = new Document(stream);
			insertDocument(builder.getCurrentParagraph(), subDoc);
			// The paragraph that contained the merge field might be empty now, and you probably want to delete it.
			if (!builder.getCurrentParagraph().hasChildNodes())
				builder.getCurrentParagraph().remove();
			e.setText(null);
		}
	}
	public void /*IFieldMergingCallback.*/imageFieldMerging(ImageFieldMergingArgs args)
	{
		// Do nothing.
	}
}
private static class InsertDocumentAtReplaceHandler implements IReplacingCallback
{
	public /*ReplaceAction*/int /*IReplacingCallback.*/replacing(ReplacingArgs args) throws Exception
	{
		Document subDoc = new Document(getMyDir() + "Document insertion 2.docx");
		// Insert a document after the paragraph, containing the match text.
		Paragraph para = (Paragraph)args.getMatchNode().getParentNode();
		insertDocument(para, subDoc);
		// Remove the paragraph with the match text.
		para.remove();
		return ReplaceAction.SKIP;
	}
```

## Conclusion

Cloning and combining documents in Aspose.Words for Java can be accomplished using various techniques. Whether you need to clone a document, insert content at replace points, bookmarks, or during mail merge, Aspose.Words provides powerful features to manipulate documents seamlessly.

## FAQ's

### How do I clone a document in Aspose.Words for Java?

You can clone a document in Aspose.Words for Java using the `deepClone()` method. Here's an example:

```java
Document doc = new Document(getMyDir() + "Document.docx");
Document clone = doc.deepClone();
clone.save(getArtifactsDir() + "ClonedDocument.docx");
```

### How can I insert a document at a bookmark?

To insert a document at a bookmark in Aspose.Words for Java, you can find the bookmark by name and then use the `insertDocument` method to insert the content. Here's an example:

```java
Document mainDoc = new Document(getMyDir() + "MainDocument.docx");
Document subDoc = new Document(getMyDir() + "SubDocument.docx");
Bookmark bookmark = mainDoc.getRange().getBookmarks().get("MyBookmark");
insertDocument(bookmark.getBookmarkStart().getParentNode(), subDoc);
mainDoc.save(getArtifactsDir() + "CombinedDocument.docx");
```

### How do I insert documents during mail merge in Aspose.Words for Java?

You can insert documents during mail merge in Aspose.Words for Java by setting a field merging callback and specifying the document to be inserted. Here's an example:

```java
Document mainDoc = new Document(getMyDir() + "MainDocument.docx");
mainDoc.getMailMerge().setFieldMergingCallback(new InsertDocumentAtMailMergeHandler());
mainDoc.getMailMerge().execute(new String[] { "DocumentField" }, new Object[] { getMyDir() + "DocumentToInsert.docx" });
mainDoc.save(getArtifactsDir() + "MergedDocument.docx");
```

In this example, the `InsertDocumentAtMailMergeHandler` class handles the insertion logic for the "DocumentField" during mail merge.
