---
title: Access Styles
linktitle: Access Styles
second_title: Aspose.Words for .NET API Reference
description: Learn how to access document styles with Aspose.Words for .NET. Complete tutorial to manipulate the styles of your documents.
type: docs
weight: 10
url: /net/programming-with-styles-and-themes/access-styles/
---

In this tutorial, we will explore the provided C# source code for accessing document styles using Aspose.Words for .NET. This feature allows you to get the full collection of styles present in the document.

## Step 1: Setting up the environment

Before you begin, make sure you've set up your development environment with Aspose.Words for .NET. Make sure you've added the necessary references and imported the appropriate namespaces.

## Step 2: Creating the document

```csharp
Document doc = new Document();
```

In this step we create a new empty `Document` object.

## Step 3: Accessing the style collection

```csharp
string styleName = "";

StyleCollection styles = doc.Styles;
```

In this step, we access the document's style collection using the `Styles` property. This collection contains all the styles present in the document.

## Step 4: Browse Styles

```csharp
foreach(Style style in styles)
{
     if (styleName == "")
     {
         styleName = style.Name;
         Console.WriteLine(styleName);
     }
     else
     {
         styleName = styleName + "," + style.Name;
         Console.WriteLine(styleName);
     }
}
```

In this final step, we loop through each style in the collection using a `foreach` loop. We display the name of each style to the console, concatenating them with commas for better readability.

Now you can run the source code to access styles in a document and display their names to the console. This feature can be useful for analyzing styles in a document, performing specific operations on particular styles, or simply getting information about available styles.

### Sample source code for Access Styles using Aspose.Words for .NET 
```csharp

Document doc = new Document();

string styleName = "";

// Get styles collection from the document.
StyleCollection styles = doc.Styles;
foreach (Style style in styles)
{
	if (styleName == "")
	{
		styleName = style.Name;
		Console.WriteLine(styleName);
	}
	else
	{
		styleName = styleName + ", " + style.Name;
		Console.WriteLine(styleName);
	}
}
            
        
```

## Conclusion

In this tutorial, we explored the functionality of accessing document styles using Aspose.Words for .NET. By accessing the styles collection, we were able to get the full list of styles present in the document.

Accessing document styles can be useful in many scenarios, such as specific manipulation of certain styles, analysis of styles for statistics or further processing, or simply to obtain information about the styles used.

Aspose.Words for .NET provides a powerful API for accessing different elements of a document, including styles. You can integrate this functionality into your projects to efficiently manage the styles of your documents.