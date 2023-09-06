---
title: Show Hide Bookmarks In Word Document
linktitle: Show Hide Bookmarks In Word Document
second_title: Aspose.Words Document Processing API
description: Learn how to show or hide a specific bookmark in word document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-bookmarks/show-hide-bookmarks/
---

In this article, we will explore the C# source code above to understand how to use the Show Hide Bookmarks function in the Aspose.Words for .NET library. This feature allows you to show or hide a specific bookmark in word document.

## Prerequisites

- Basic knowledge of the C# language.
- .NET development environment with Aspose.Words library installed.

## Step 1: Loading the document

We use the `Document` class to load the existing document from a file:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Bookmarks.docx");
```

## Step 2: Show or hide a specific bookmark

We use the `ShowHideBookmarkedContent` function to show or hide a specific bookmark in the document. This function takes as parameters the document, the name of the bookmark and a boolean to indicate whether to show or hide the bookmark:

```csharp
ShowHideBookmarkedContent(doc, "MyBookmark1", false);
```

## Step 3: Saving the modified document

We use the `Save` method to save the modified document to a file:

```csharp
doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");
```

### Example source code for Show Hide Bookmarks using Aspose.Words for .NET

Here is the full example source code to demonstrate showing or hiding a specific bookmark using Aspose.Words for .NET:

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Bookmarks.docx");

	ShowHideBookmarkedContent(doc, "MyBookmark1", false);
	
	doc.Save(dataDir + "WorkingWithBookmarks.ShowHideBookmarks.docx");

```

#### ShowHideBookmarkedContent source code

```csharp

public void ShowHideBookmarkedContent(Document doc, string bookmarkName, bool showHide)
        {
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
        }
		
```
## Conclusion

In this article, we explored the C# source code to understand how to use the Show Hide Bookmarks feature of Aspose.Words for .NET. We followed a step-by-step guide to show or hide a specific bookmark in a document.

### FAQ's for show hide bookmarks in word document

#### Q: Can I show or hide multiple bookmarks in the same document?

A: Yes, you can show or hide multiple bookmarks in the same document by repeating steps 2 and 3 for each bookmark you want to process.

#### Q: Does the provided code work with other Word document formats, such as .doc or .docm?

A: Yes, the provided code works with various Word document formats supported by Aspose.Words, such as .doc and .docm. Just be sure to use the correct filename and path when loading and saving the document.

#### Q: How can I show a hidden bookmark again?

A: To show a hidden bookmark again, you need to use the same `ShowHideBookmarkedContent` function passing the value `true` for the boolean parameter that indicates whether to show or hide the bookmark.

#### Q: Can I use conditions to show or hide bookmarks based on merge field values in the document?

A: Yes, you can use conditions and merge field values to determine whether a bookmark should be shown or hidden. You can customize the code of the `ShowHideBookmarkedContent` function to take into account the appropriate conditions and values.

#### Q: How can I delete a bookmark in a Word document using Aspose.Words for .NET?

A: To remove a bookmark in a Word document using Aspose.Words for .NET, you can use the `RemoveBookmarks` method of the `Document` class. Here is a sample code:

```csharp
doc.RemoveBookmarks("BookmarkName");
```
