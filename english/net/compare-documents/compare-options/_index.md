---
title: Compare Options In Word Document
linktitle: Compare Options In Word Document
second_title: Aspose.Words Document Processing API
description: Step-by-step guide to explain C# source code of Compare Options in word document feature with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/compare-documents/compare-options/
---
In this tutorial, we will explain how to use the Compare Options in word document feature with Aspose.Words for .NET. Follow the steps below to understand the source code and apply the changes.

## Step 1: Compare documents with custom options

To begin, load two documents to compare. In this example, we will use the `Clone()` method to create a copy of the original document. Here's how:

```csharp
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();
```

## Step 2: Configuring comparison options

We will now configure the compare options by creating a `CompareOptions` object and setting the various properties as needed. Here's how:

```csharp
CompareOptions options = new CompareOptions
{
IgnoreFormatting = true,
IgnoreHeadersAndFooters = true,
IgnoreCaseChanges = true,
IgnoreTables = true,
IgnoreFields = true,
IgnoreComments = true,
IgnoreTextboxes=true,
IgnoreFootnotes=true
};
```

## Step 3: Compare documents with custom options

We will now use the `Compare()` method passing the custom options to compare the two documents. This method will mark the changes in the original document. Here's how:

```csharp
// Compare documents with custom options
docA.Compare(docB, "user", DateTime.Now, options);

// Check if the documents are equal
Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal": "Documents are not equal");
```

### Example source code for Compare Options using Aspose.Words for .NET

Here is the complete source code for the Compare Options feature with Aspose.Words for .NET:

```csharp

	Document docA = new Document(MyDir + "Document.docx");
	Document docB = docA.Clone();

	CompareOptions options = new CompareOptions
	{
		IgnoreFormatting = true,
		IgnoreHeadersAndFooters = true,
		IgnoreCaseChanges = true,
		IgnoreTables = true,
		IgnoreFields = true,
		IgnoreComments = true,
		IgnoreTextboxes = true,
		IgnoreFootnotes = true
	};

	docA.Compare(docB, "user", DateTime.Now, options);

	Console.WriteLine(docA.Revisions.Count == 0 ? "Documents are equal" : "Documents are not equal");

```

With this code you can compare two documents using custom options to ignore specific elements when comparing with Aspose.Words for .NET.

## Conclusion

In this tutorial, we learned how to use Compare Options in Aspose.Words for .NET to customize the comparison process when comparing two documents. By specifying different options, you can ignore specific elements and make the comparison process more flexible. This feature allows you to have greater control over the comparison process, tailoring it to your specific requirements. Aspose.Words for .NET provides powerful document comparison capabilities, making it easy to identify differences between documents while ignoring certain elements as needed.

### FAQ's

#### Q: What is the purpose of using Compare Options in Aspose.Words for .NET?

A: Compare Options in Aspose.Words for .NET allow you to customize the comparison process when comparing two documents. With these options, you can specify which elements to ignore during the comparison, such as formatting changes, headers and footers, tables, fields, comments, textboxes, and footnotes.

#### Q: How do I use Compare Options in Aspose.Words for .NET?

A: To use Compare Options in Aspose.Words for .NET, follow these steps:
1. Load the two documents that you want to compare into separate Document objects.
2. Use the `Clone()` method to create a copy of the original document.
3. Create a `CompareOptions` object and set its properties to customize the comparison process. You can specify which elements to ignore during the comparison.
4. Use the `Compare()` method on one of the documents and pass the other document and the `CompareOptions` object as parameters. This method will compare the documents based on the specified options and mark the changes in the original document.
5. Check the `Revisions` property of the original document. If the count is zero, it means the documents are identical, considering the specified options.

#### Q: What are the common options available in CompareOptions?

A: The common options available in CompareOptions include:
- `IgnoreFormatting`: Ignores changes in formatting.
- `IgnoreHeadersAndFooters`: Ignores changes in headers and footers.
- `IgnoreCaseChanges`: Ignores case changes (uppercase/lowercase).
- `IgnoreTables`: Ignores changes in tables.
- `IgnoreFields`: Ignores changes in fields.
- `IgnoreComments`: Ignores changes in comments.
- `IgnoreTextboxes`: Ignores changes in textboxes.
- `IgnoreFootnotes`: Ignores changes in footnotes.

#### Q: Can I use custom options for specific elements during document comparison?

A: Yes, you can use custom options for specific elements during document comparison. By setting the properties of the `CompareOptions` object accordingly, you can choose which elements to ignore and which to consider during the comparison.
