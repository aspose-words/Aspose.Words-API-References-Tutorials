---
title: Set Theme Properties
linktitle: Set Theme Properties
second_title: Aspose.Words for .NET API Reference
description: Learn to customize the look of your documents by changing theme properties with Aspose.Words for .NET. Get professional and attractive results.
type: docs
weight: 10
url: /net/programming-with-styles-and-themes/set-theme-properties/
---
In this tutorial, we will explore the provided C# source code to set the theme properties of a document using Aspose.Words for .NET. We are going to change the secondary fonts and theme colors.

## Step 1: Setting up the environment

Make sure you have set up your development environment with Aspose.Words for .NET. Make sure you've added the necessary references and imported the appropriate namespaces.

## Step 2: Creating a Document Object

```csharp
Document doc = new Document();
```

In this step, we create a new `Document` object.

## Step 3: Edit theme properties

```csharp
Aspose.Words.Themes.Theme theme = doc.Theme;
theme.MinorFonts.Latin = "Times New Roman";
theme.Colors.Hyperlink = Color.Gold;
```

In this step, we access the `Theme` object of the `Document` object to get the document theme. Next, we can modify theme properties such as secondary fonts (`MinorFonts.Latin`) and colors (`Colors.Hyperlink`).

## Step 4: Save the document

In this last step, you can save the modified document as needed.

You can run source code to set theme properties for a document. This lets you customize the fonts and colors used in the theme to achieve a consistent look across your documents.

### Sample source code for Set Theme Properties using Aspose.Words for .NET 
```csharp
            
Document doc = new Document();

Aspose.Words.Themes.Theme theme = doc.Theme;
theme.MinorFonts.Latin = "Times New Roman";
theme.Colors.Hyperlink = Color.Gold;
            
        
```

## Conclusion

In this tutorial, we explored the functionality to set a document's theme properties with Aspose.Words for .NET. By changing secondary fonts and theme colors, you can customize the look of your documents and maintain visual consistency.

Aspose.Words for .NET offers a powerful API for manipulating your document styles and themes. By modifying the properties of the theme, you can adapt the appearance of your documents to the specific needs of your project or your brand.

Don't forget to save your edited document once the theme properties are set.

Explore more features offered by Aspose.Words for .NET to optimize your workflow and achieve professional and attractive documents.