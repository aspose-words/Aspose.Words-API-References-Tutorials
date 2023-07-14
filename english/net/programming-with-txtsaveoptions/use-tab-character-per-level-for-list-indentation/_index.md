---
title: Use Tab Character Per Level For List Indentation
linktitle: Use Tab Character Per Level For List Indentation
second_title: Aspose.Words Document Processing API
description: Learn how to use the indent lists with tab characters feature in Aspose.Words for .NET. Save time and improve your workflow with this powerful feature.
type: docs
weight: 10
url: /net/programming-with-txtsaveoptions/use-tab-character-per-level-for-list-indentation/
---

In this tutorial, we will explore the C# source code provided for the "Use one tab character per level for list indentation" feature with Aspose.Words for .NET. This feature allows you to apply tab characters for indenting lists at each level, providing greater flexibility and control over the appearance of your documents.

## Step 1: Setting up the environment

Before you begin, make sure you've set up your development environment with Aspose.Words for .NET. Make sure you've added the necessary references and imported the appropriate namespaces.

## Step 2: Creating the document and the generator

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

In this step, we create a new `Document` object and an associated `DocumentBuilder` object. These objects will allow us to manipulate and generate our document.

## Step 3: Creating a list with three levels of indentation

```csharp
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder.ListFormat.ListIndent();
builder. Writen("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");
```

In this step, we apply the default format of list numbers using the `ApplyNumberDefault()` method of the list formatter. Next, we add three items to our list using the document builder's `Writeln()` and `Write()` methods. We use the `ListIndent()` method to increment the indentation at each level.

## Step 4: Configure recording options

```csharp
TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 1;
saveOptions.ListIndentation.Character = '\t';
```

In this step, we configure the options for saving the document. We create a new `TxtSaveOptions` object and set the `ListIndentation.Count` property to 1 to specify the number of tab characters per indentation level. We also set the `ListIndentation.Character` property to '\t' to specify that we want to use tab characters.

## Step 5: Save the document

```csharp
doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt", saveOptions);
```

In this last step, we save the document with the specified save options. We use the `Save()` method of the document passing the full path of the output file and the saving options.


Now you can run the source code to generate a document with list indentation using tab characters. The output file will be saved in the specified directory with name "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt".

### Example code source for the Use one tab character per level for list indentation feature with Aspose.Words for .NET:

```csharp

// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Create a list with three levels of indentation
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder.ListFormat.ListIndent();
builder. Writen("Element 2");
builder.ListFormat.ListIndent();
builder.Write("Element 3");

TxtSaveOptions saveOptions = new TxtSaveOptions();
saveOptions.ListIndentation.Count = 1;
saveOptions.ListIndentation.Character = '\t';

doc.Save(dataDir + "WorkingWithTxtSaveOptions.UseTabCharacterPerLevelForListIndentation.txt", saveOptions);

```

Now that you have finished generating your document with list indentation using tab characters, you can use Markdown to format your article content. Be sure to use appropriate formatting tags to highlight titles, subtitles, and included source code.

### Frequently Asked Questions

#### Q: What is the "Use one tab character per level for list indentation" feature with Aspose.Words for .NET?
The "Use one tab character per level for list indentation" feature with Aspose.Words for .NET allows applying tab characters for list indentation at each level. This provides greater flexibility and control over the appearance of your documents.

#### Q: How can I use this feature with Aspose.Words for .NET?
To use this feature with Aspose.Words for .NET, you can follow these steps:

Set up your development environment by adding the necessary references and importing the appropriate namespaces.

Create a new `Document` object and an associated `DocumentBuilder` object.

Use the `DocumentBuilder` to create a list with multiple levels of indentation using the methods `ApplyNumberDefault()` to apply the default list number format, `Writeln()` and `Write()` to add items to the list, and `ListIndent()` to increment the indentation at each level.

Configure save options by creating a `TxtSaveOptions` object and setting the properties `ListIndentation.Count` to the number of tab characters per level and `ListIndentation.Character` to `'\t'` to use the tab characters.

Save the document using the `Save()` method of the document specifying the full path of the output file and the saving options.

#### Q: Is it possible to customize the number of tab characters per level for list indentation?
Yes, you can customize the number of tab characters per level for list indentation by changing the value of the `ListIndentation.Count` property in the `TxtSaveOptions` class. You can specify the number of tab characters you want for each level of indentation.

#### Q: What other characters can I use for list indentation with Aspose.Words for .NET?
Besides tab characters, you can also use other characters for list indentation with Aspose.Words for .NET. You can set the `ListIndentation.Character` property to any desired character, such as space (`' '`), for indenting lists.

#### Q: Does Aspose.Words for .NET offer any other features for managing lists?
Yes, Aspose.Words for .NET offers many features for managing lists in Word documents. You can create numbered or bulleted lists, set indentation levels, customize the style of lists, add list items, and more.