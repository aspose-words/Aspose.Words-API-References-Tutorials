---
title: Ignore Text Inside Fields
linktitle: Ignore Text Inside Fields
second_title: Aspose.Words Document Processing API
description: Learn how to use the "Ignore Text Inside Fields" feature of Aspose.Words for .NET.
type: docs
weight: 10
url: /net/find-and-replace-text/ignore-text-inside-fields/
---
In this article, we will explore the C# source code above to understand how to use the Ignore Text Inside Fields function in the Aspose.Words for .NET library. This feature is useful when we want to ignore the text inside the fields when manipulating documents.

## Prerequisites

- Basic knowledge of the C# language.
- .NET development environment with Aspose.Words library installed.

## Step 1: Creating a New Document

Before we start manipulating text inside fields, we need to create a new document using Aspose.Words for .NET. This can be done by instantiating a `Document` object:

```csharp
Document doc = new Document();
```

## Step 2: Inserting a field with text inside

Once we have a document, we can insert a field containing text inside it using a `DocumentBuilder` object. For example, to insert an "INCLUDETEXT" field with the text "Text in field", we can use the `InsertField` method:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertField("INCLUDETEXT", "Text in field");
```

## Step 3: Using the Ignore Text Inside Fields function

To ignore text inside fields on subsequent operations, we can use a `FindReplaceOptions` object and set the `IgnoreFields` property to `true`:

```csharp
FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
```

## Step 4: Using regular expressions for search and replace

To perform search and replace operations on the text of the document, we will use regular expressions. In our example, we will search for all occurrences of the letter "e" and replace them with an asterisk "*". We'll use .NET's `Regex` class for this:

```csharp
Regex regex = new Regex("e");
doc.Range.Replace(regex, "*", options);
```

## Step 5: Viewing the Modified Document Output

After applying the search and replace, we can display the changed content of the document using the `GetText` method:

```csharp
Console.WriteLine(doc.GetText());
```

## Step 6: Changing options to include fields

we include the text inside the fields in the output result, we can change the options to not ignore the fields. For this we will set the `IgnoreFields` property to `false`:

```csharp
options.IgnoreFields = false;
```

## Step 7: Displaying the modified document with the fields

After changing the options, we can perform the search and replace again to get the result with the text inside the included fields:

```csharp
doc.Range.Replace(regex, "*", options);
Console.WriteLine(doc.GetText());
```

### Example source code for Ignore Text Inside Fields using Aspose.Words for .NET

Here is the full sample source code to demonstrate the use of the Ignore Text Inside Fields function with Aspose.Words for .NET:

```csharp
    
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	// Insert field with text inside.
	builder.InsertField("INCLUDETEXT", "Text in field");
	
	FindReplaceOptions options = new FindReplaceOptions { IgnoreFields = true };
	
	Regex regex = new Regex("e");
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());

	options.IgnoreFields = false;
	doc.Range.Replace(regex, "*", options);
	
	Console.WriteLine(doc.GetText());
  
```

## Conclusion

In this article, we explored the C# source code to understand how to use the Ignore Text Inside Fields function in Aspose.Words for .NET. We followed a step-by-step guide to create a document, insert a field with text inside, use the Ignore Text Inside Fields function, perform search and replace operations with regular expressions, and display the modified document .

