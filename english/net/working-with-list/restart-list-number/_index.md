---
title: Restart List Number
linktitle: Restart List Number
second_title: Aspose.Words for .NET API Reference
description: Learn how to reset the number of a list in a Word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-list/restart-list-number/
---
In this step-by-step tutorial, we will show you how to reset the number of a list in a Word document using Aspose.Words for .NET. We'll explain the provided C# source code and show you how to implement it in your own projects.

To get started, make sure you have Aspose.Words for .NET installed and configured in your development environment. If you haven't already, download and install the library from the official site.

## Step 1: Creating the Document and Document Generator

First, create a new document and an associated document generator:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2: Creating and Customizing the First List

Next, create a list based on an existing template, then customize its levels:

```csharp
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;
```

## Step 3: Adding items to the first list

Use the document builder to add items to the first list and remove list numbers:

```csharp
builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## Step 4: Creating and Customizing the Second List

To reuse the first list by resetting the number, create a copy of the original list layout:

```csharp
List list2 = doc.Lists.AddCopy(list1);
list2.ListLevels[0].StartAt = 10;
```

You can also make additional changes to the second list if needed.

## Step 5: Adding items to the second list

Use the document builder again to add items to the second list and remove the list numbers:

```csharp
builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## Step 6: Save the modified document

Finally, save the modified document:

```csharp
builder.Document.Save(dataDir + "ResetListNumber.docx");
```

So ! You have successfully reset the number of a list in a Word document using Aspose.Words for .NET.

### Sample Source Code for List Number Reset

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Create a list based on a template.
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;

builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

// To reuse the first list, we need to restart numbering by creating a copy of the original list formatting.
List list2 = doc.Lists.AddCopy(list1);

// We can modify the new list in any way, including setting a new start number.
list2.ListLevels[0].StartAt = 10;

builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

builder.Document.Save(dataDir + "WorkingWithList.RestartListNumber.docx");
            
```





