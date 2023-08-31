---
title: Show Hide Bookmarked Content In Word Document
linktitle: Show Hide Bookmarked Content In Word Document
second_title: Aspose.Words Document Processing API
description: Learn how to show or hide bookmark content in word document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-bookmarks/show-hide-bookmarked-content/
---

In this article, we will explore the above C# source code to understand how to use Show Hide Bookmarked Content function in Aspose.Words for .NET library. This feature allows you to show or hide the contents of a bookmark in word document based on a specific condition when merging data.

## Prerequisites

- Basic knowledge of the C# language.
- .NET development environment with Aspose.Words library installed.

## Step 1: Getting the bookmark

We use the `Bookmarks` property of the document range to get the specific bookmark on which we want to show or hide the content:

```csharp
Bookmark bm = doc.Range.Bookmarks[bookmarkName];
```

## Step 2: Inserting the merge fields

We use a document builder `DocumentBuilder` to insert the necessary merge fields. These merge fields will set a condition to show or hide the bookmark content depending on the value of the `showHide` variable:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder. MoveToDocumentEnd();

Field field = builder. InsertField("IF \"", null);
builder. MoveTo(field. Start. NextSibling);
builder. InsertField("MERGEFIELD " + bookmarkName + "", null);
builder. Write("\" = \"true\" ");
builder. Write("\"");
builder. Write("\"");
builder. Write(" \"\"");
```

## Step 3: Moving bookmark content

We loop through the contents of the bookmark and move it so that it appears

isse before the bookmark. This will control showing or hiding content based on the specified condition:

```csharp
Node currentNode = field. Start;
bool flag = true;
while (currentNode != null && flag)
{
     if (currentNode.NodeType == NodeType.Run)
         if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
             flag = false;

     Node nextNode = currentNode.NextSibling;

     bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
     currentNode = nextNode;
}
```

## Step 4: Moving the rest of the bookmark content

We move the rest of the bookmark content after the bookmark, using the end node of the bookmark as the insertion point:

```csharp
Node endNode = bm.BookmarkEnd;
flag = true;
while (currentNode != null && flag)
{
     if (currentNode.NodeType == NodeType.FieldEnd)
         flag = false;

     Node nextNode = currentNode.NextSibling;

     bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
     endNode = currentNode;
     currentNode = nextNode;
}
```

## Step 5: Performing the merge

We use the `Execute` method of the document`s `MailMerge` object to execute the merge using the bookmark name and the value of the `showHide` variable:

```csharp
doc. MailMerge. Execute(new[] { bookmarkName }, new object[] { showHide });
```

### Example source code for Show Hide Bookmarked Content using Aspose.Words for .NET

Here is the full example of Source code to demonstrate showing or hiding bookmark content using Aspose.Words for .NET:

```csharp

	Bookmark bm = doc.Range.Bookmarks[bookmarkName];

	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.MoveToDocumentEnd();

	// {IF "{MERGEFIELD bookmark}" = "true" "" ""}
	Field field = builder.InsertField("IF \"", null);
	builder.MoveTo(field.Start.NextSibling);
	builder.InsertField("MERGEFIELD " + bookmarkName + "", null);
	builder.Write("\" = \"true\" ");
	builder.Write("\"");
	builder.Write("\"");
	builder.Write(" \"\"");

	Node currentNode = field.Start;
	bool flag = true;
	while (currentNode != null && flag)
	{
		if (currentNode.NodeType == NodeType.Run)
			if (currentNode.ToString(SaveFormat.Text).Trim() == "\"")
				flag = false;

		Node nextNode = currentNode.NextSibling;

		bm.BookmarkStart.ParentNode.InsertBefore(currentNode, bm.BookmarkStart);
		currentNode = nextNode;
	}

	Node endNode = bm.BookmarkEnd;
	flag = true;
	while (currentNode != null && flag)
	{
		if (currentNode.NodeType == NodeType.FieldEnd)
			flag = false;

		Node nextNode = currentNode.NextSibling;

		bm.BookmarkEnd.ParentNode.InsertAfter(currentNode, endNode);
		endNode = currentNode;
		currentNode = nextNode;
	}

	doc.MailMerge.Execute(new[] { bookmarkName }, new object[] { showHide });

```

## Conclusion

In this article, we explored the C# source code to understand how to use the Show Hide Bookmarked Content feature of Aspose.Words for .NET. We've followed a step-by-step guide to show or hide the contents of a bookmark based on a specific condition when merging data.

### FAQ's for show hide bookmarked content in word document

#### Q: Can I use the same condition for multiple bookmarks in the same document?

A: Yes, you can use the same condition for multiple bookmarks in the same document. Just repeat steps 2-5 for each bookmark, adjusting the bookmark name and optionally the value of the `showhide` variable as needed.

#### Q: How can I add more conditions to show or hide bookmark content?

A: To add more conditions, you can use logical operators such as `AND` and `OR` in the code for inserting the merge fields in step 2. Edit the condition in the following code to add additional conditions :

```csharp
builder. Write("\" = \"true\" ");
```

#### Q: How can I delete a bookmark in a Word document using Aspose.Words for .NET?

A: To remove a bookmark in a Word document using Aspose.Words for .NET, you can use the `Remove` method from the `Bookmarks` collection of the document range. Here is sample code for deleting a specific bookmark:

```csharp
doc.Range.Bookmarks.Remove(bookmarkName);
```

#### Q: Is the Aspose.Words library free?

A: The Aspose.Words library is a commercial library and requires a valid license to use in your projects. You can check [Aspose.Words for .NET API references](https://reference.aspose.com/words/net/) to learn more about licensing options and pricing.

#### Q: Are there other libraries available for Words Processing with Word documents in .NET?

A: Yes, there are other libraries available for Words Processing with Word documents in .NET, such as Open XML SDK and GemBox.Document. You can explore these libraries as alternatives to Aspose.Words based on your specific needs and preferences.
