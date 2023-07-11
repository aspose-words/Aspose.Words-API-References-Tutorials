---
title: Insert Style Separator
linktitle: Insert Style Separator
second_title: Aspose.Words Document Processing API
description: Learn to create documents with custom styles and insert style separators for precise, professional formatting.
type: docs
weight: 10
url: /net/programming-with-styles-and-themes/insert-style-separator/
---
In this tutorial, we will explore the C# source code provided to insert a style separator in a document using Aspose.Words for .NET. We will create a new document, define custom styles and insert a style separator.

## Step 1: Setting up the environment

Make sure you have set up your development environment with Aspose.Words for .NET. Make sure you've added the necessary references and imported the appropriate namespaces.

## Step 2: Creating a new Document object

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

In this step, we create a new `Document` object and an associated `DocumentBuilder` object.

## Step 3: Creating and configuring the custom style

```csharp
Style paraStyle = builder.Document.Styles.Add(StyleType.Paragraph, "MyParaStyle");
paraStyle.Font.Bold = false;
paraStyle.Font.Size = 8;
paraStyle.Font.Name = "Arial";
```

In this step, we create a custom paragraph style named "MyParaStyle" and set its font properties.

## Step 4: Inserting the style separator

```csharp
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Write("Heading 1");
builder. InsertStyleSeparator();
builder.ParagraphFormat.StyleName = paraStyle.Name;
builder.Write("This is text with some other formatting");
```

In this step, we set the paragraph style to "Heading 1", write some text with this style, and then insert a style separator. Then we set the paragraph style to our custom style "MyParaStyle" and write some text with this style.

## Step 5: Save the document

In this last step, you can save the created document according to your needs.

You can run source code to insert a style separator into a document. This lets you create sections of text with different styles and customize the look of your document.

### Sample source code for Insert Style Separator using Aspose.Words for .NET 

```csharp

// Path to your document directory 
string dataDir = "YOUR DOCUMENT DIRECTORY"; 
 
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

Style paraStyle = builder.Document.Styles.Add(StyleType.Paragraph, "MyParaStyle");
paraStyle.Font.Bold = false;
paraStyle.Font.Size = 8;
paraStyle.Font.Name = "Arial";

// Append text with "Heading 1" style.
builder.ParagraphFormat.StyleIdentifier = StyleIdentifier.Heading1;
builder.Write("Heading 1");
builder.InsertStyleSeparator();

// Append text with another style.
builder.ParagraphFormat.StyleName = paraStyle.Name;
builder.Write("This is text with some other formatting ");

doc.Save(dataDir + "WorkingWithStylesAndThemes.InsertStyleSeparator.docx");
            
        
```

## Conclusion

In this tutorial, we learned how to insert a style separator in a document using Aspose.Words for .NET. We created a new document, defined a custom style, and used the style separator to differentiate sections of text with different styles.

Using style separators provides additional flexibility when formatting your documents. This helps maintain visual consistency while allowing for stylistic variation.

Aspose.Words for .NET provides a powerful API for managing styles in your documents. You can explore this library further to customize the look of your documents and create professional results.

Remember to save your document after inserting the style separator.
