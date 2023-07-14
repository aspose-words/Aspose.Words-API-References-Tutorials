---
title: Ignore Text Inside Insert Revisions
linktitle: Ignore Text Inside Insert Revisions
second_title: Aspose.Words Document Processing API
description: Learn how to use the "Ignore Text Inside Insert Revisions" feature of Aspose.Words for .NET to manipulate insert revisions in Word documents.
type: docs
weight: 10
url: /net/find-and-replace-text/ignore-text-inside-insert-revisions/
---

In this article, we will explore the C# source code above to understand how to use the Ignore Text Inside Insert Revisions function in the Aspose.Words for .NET library. This feature is useful when we want to ignore text inside insert revisions while manipulating documents.

## Prerequisites

- Basic knowledge of the C# language.
- .NET development environment with Aspose.Words library installed.

## Step 1: Creating a New Document

Before we start manipulating text inside insert revisions, we need to create a new document using Aspose.Words for .NET. This can be done by instantiating a `Document` object:

```csharp
Document doc = new Document();
```

## Step 2: Insert text with revision tracking

Once we have a document, we can insert text with revision tracking using a `DocumentBuilder` object. For example, to insert the "Inserted" text with revision tracking, we can use the `StartTrackRevisions`, `Writeln` and `StopTrackRevisions` methods:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

## Step 3: Insert unreviewed text

In addition to text with revision tracking, we can also insert unrevised text using the `DocumentBuilder` object. For example, to insert the text "Text" without revision, we can use the `Write` method:

```csharp
builder.Write("Text");
```

## Step 4: Using the Ignore Text Inside Insert Revisions function

To ignore text inside insert revisions on subsequent operations, we can use a `FindReplaceOptions` object and set the `IgnoreInserted` property to `true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
```

## Step 5: Using regular expressions for search and replace

To perform search operations and replacement on the document text, we will use regular expressions. In our example, we will search for all occurrences of the letter "e" and replace them with an asterisk "*". We'll use .NET's `Regex` class for this:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## Step 6: Viewing the Modified Document Output

After applying the search and replace, we can display the changed content of the document using the `GetText` method:

```csharp
Console.WriteLine(doc.GetText());
```

## Step 7: Changing Options to Include Insert Revisions

If we want to include the text inside the insert revisions in the output result, we can change the options to not ignore the insert revisions. For this we will set the `IgnoreInserted` property to `false`:

```csharp
options.IgnoreInserted = false;
```

## Step 8: Viewing the Modified Document with Insert Revisions

After changing the options, we can perform the search and replace again to get the result with the text inside the insert revisions included:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```


### Example source code for Ignore Text Inside Insert Revisions using Aspose.Words for .NET

Here is the full sample source code to demonstrate the use of the Ignore Text Inside Insert Revisions function with Aspose.Words for .NET:


```csharp
       
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Insert text with tracking revisions.
	doc.StartTrackRevisions("author", DateTime.Now);
	builder.Writeln("Inserted");
	doc.StopTrackRevisions();

	// Insert non-revised text.
	builder.Write("Text");

	FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };

	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());

	options.IgnoreInserted = false;
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());
   
```

## Conclusion

In this article, we explored the C# source code to understand how to use the Ignore Text Inside Insert Revisions function in Aspose.Words for .NET. We followed a step-by-step guide to creating a document, inserting text with tracking revisions and unrevised text, using the Ignore Text Inside Insert Revisions function, performing search and replace operations with regular expressions, and display the modified document.

### FAQ's

#### Q: What is the "Ignore Text Inside Insert Revisions" feature in Aspose.Words for .NET?

A: The "Ignore Text Inside Insert Revisions" feature in Aspose.Words for .NET allows you to specify whether the text inside insert revisions should be ignored during certain operations, such as finding and replacing text. When this feature is enabled, the text inside the insert revisions is not considered during operations.

#### Q: How can I create a new document using Aspose.Words for .NET?

A: To create a new document using Aspose.Words for .NET, you can instantiate a `Document` object. Here's an example of C# code to create a new document:

```csharp
Document doc = new Document();
```

#### Q: How can I insert text with revision tracking in Aspose.Words for .NET?

A: Once you have a document, you can insert text with revision tracking using a `DocumentBuilder` object. For example, to insert the "Inserted" text with revision tracking, you can use the `StartTrackRevisions`, `Writeln`, and `StopTrackRevisions` methods:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
doc.StartTrackRevisions("author", DateTime.Now);
builder.Writeln("Inserted");
doc.StopTrackRevisions();
```

#### Q: How can I insert unrevised text in Aspose.Words for .NET?

A: In addition to text with revision tracking, you can also insert unrevised text using the `DocumentBuilder` object. For example, to insert the text "Text" without revision, you can use the `Write` method:

```csharp
builder.Write("Text");
```

#### Q: How can I ignore text inside insert revisions in Aspose.Words for .NET?

A: To ignore text inside insert revisions during subsequent operations, you can use a `FindReplaceOptions` object and set the `IgnoreInserted` property to `true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreInserted = true };
```

#### Q: How can I perform search and replace using regular expressions in Aspose.Words for .NET?

A: To perform search and replace operations on the text of the document using regular expressions, you can use the .NET `Regex` class. For example, to search for all occurrences of the letter "e" and replace them with an asterisk "*", you can create a `Regex` object and use it with the `Replace` method:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

#### Q: How can I view the modified output of the document in Aspose.Words for .NET?

A: After applying search and replace operations, you can view the changed content of the document using the `GetText` method:

```csharp
Console.WriteLine(doc.GetText());
```

#### Q: How can I include the insert revisions in the output result in Aspose.Words for .NET?

A: To include the text inside the insert revisions in the output result, you can change the options to not ignore the insert revisions. For this, you can set the `IgnoreInserted` property of the `FindReplaceOptions` object to `false`:

```csharp
options.IgnoreInserted = false;
```

#### Q: How can I display the modified document with the insert revisions in Aspose.Words for .NET?

A: After changing the options to include insert revisions, you can perform the search and replace again to get the result with the text inside the insert revisions included:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```
