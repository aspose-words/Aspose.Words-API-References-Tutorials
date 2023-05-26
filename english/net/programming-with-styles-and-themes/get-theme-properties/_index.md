---
title: Get Theme Properties
linktitle: Get Theme Properties
second_title: Aspose.Words for .NET API Reference
description: Explore a document's theme properties with Aspose.Words for .NET. Customize styles and colors for a unique look.
type: docs
weight: 10
url: /net/programming-with-styles-and-themes/get-theme-properties/
---

In this tutorial, we will explore the provided C# source code to get the theme properties of a document using Aspose.Words for .NET. Theme properties include primary and secondary fonts used, as well as accent colors.

## Step 1: Setting up the environment

Make sure you have set up your development environment with Aspose.Words for .NET. Make sure you've added the necessary references and imported the appropriate namespaces.

## Step 2: Creating a Document Object

```csharp
Document doc = new Document();
```

In this step, we create a new `Document` object.

## Step 3: Get theme properties

```csharp
Aspose.Words.Themes.Theme theme = doc.Theme;

Console.WriteLine(theme.MajorFonts.Latin);
Console.WriteLine(theme.MinorFonts.EastAsian);
Console.WriteLine(theme.Colors.Accent1);
```

In this step, we use the `Theme` property of the `Document` object to get the `Theme` object. Then we can access the different properties of the theme such as the main fonts (`MajorFonts`), the secondary fonts (`MinorFonts`) and the accent colors (`Colors`).

## Step 4: Display theme properties

In this final step, we display the theme property values using `Console.WriteLine`. You can adapt the display according to your needs.

You can run the source code to get the theme properties of a document. This feature allows you to retrieve information about fonts and colors used in a document's theme, which can be useful for style customization or analysis.

### Sample source code for Get Theme Properties using Aspose.Words for .NET 
```csharp
 
Document doc = new Document();

Aspose.Words.Themes.Theme theme = doc.Theme;

Console.WriteLine(theme.MajorFonts.Latin);
Console.WriteLine(theme.MinorFonts.EastAsian);
Console.WriteLine(theme.Colors.Accent1);

        
```

## Conclusion

In this tutorial, we explored the functionality of getting a document's theme properties with Aspose.Words for .NET. Using the `Theme` object and its associated properties, we were able to access information about the primary and secondary fonts as well as the accent colors used in the document theme.

The ability to get theme properties allows you to analyze and customize the styles and layouts of your documents. You can use this information to apply targeted changes, create reports, or perform analysis on font and color usage in your documents.

Aspose.Words for .NET offers a powerful API for manipulating your document themes, allowing you to easily adjust and customize the look of your documents.

Feel free to explore more features of Aspose.Words for .NET to enhance your workflow and meet your specific style and theme management needs.
