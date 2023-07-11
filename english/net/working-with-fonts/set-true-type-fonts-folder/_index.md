---
title: Set True Type Fonts Folder
linktitle: Set True Type Fonts Folder
second_title: Aspose.Words Document Processing API
description: Step-by-step guide to setting the true type fonts folder when rendering a document using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-fonts/set-true-type-fonts-folder/
---

In this tutorial, we'll walk you through the step-by-step process to set the true type fonts folder when rendering a document using Aspose.Words for .NET. We'll explain the bundled C# source code and provide you with a comprehensive guide to help you understand and implement this feature in your own projects. At the end of this tutorial, you will know how to specify a custom folder containing True Type fonts to use when rendering your documents using Aspose.Words for .NET.

## Step 1: Define the document directory
First, you need to set the path to your documents directory. This is the location where you want to save your edited rendered document. Replace "YOUR DOCUMENTS DIRECTORY" with the appropriate path.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Load the document to render
Next, you need to load the document to render using the `Document` class. Be sure to specify the correct document path.

```csharp
Document doc = new Document(dataDir + "Rendering.docx");
```

## Step 3: Set True Type Fonts Folder
Now you can specify the folder of true type fonts to use when rendering by creating an instance of the `FontSettings` class and using the `SetFontsFolder()` method to set the fonts folder. You can specify a custom folder containing your True Type fonts. The second parameter to `SetFontsFolder()` indicates whether you want to search subfolders of the specified folder as well.

```csharp
FontSettings fontSettings = new FontSettings();
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
doc.FontSettings = fontSettings;
```

## Step 4: Save the rendered document
Finally, you can save the rendered document to a file using the `Save()` method of the `Document` class. Be sure to specify the correct path and file name.

```csharp
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

### Sample source code for Set True Type Fonts Folder using Aspose.Words for .NET 

```csharp
// Path to your document directory 
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// Note that this setting will override any default font sources that are being searched by default. Now only these folders will be searched for
// Fonts when rendering or embedding fonts. To add an extra font source while keeping system font sources then use both FontSettings.GetFontSources and
// FontSettings.SetFontSources instead
fontSettings.SetFontsFolder(@"C:\MyFonts\", false);
// Set font settings
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.SetTrue TypeFontsFolder.pdf");
```

## Conclusion
In this tutorial, we learned how to set the true type fonts folder when rendering a document using Aspose.Words for .NET. By following this step-by-step guide, you can easily specify a custom folder containing True Type fonts to use when rendering your documents. Aspose.Words offers a powerful and flexible API for working with fonts in your documents. With this knowledge, you can control and customize the fonts used when rendering your documents to your specific needs.

### FAQ's

#### Q: How can I configure the TrueType fonts folder in Aspose.Words?

A: To configure the TrueType fonts folder in Aspose.Words, you can use the `SetTrueTypeFontsFolder` method of the `Fonts` class specifying the location of the folder containing the TrueType fonts.

#### Q: What types of fonts are considered TrueType fonts?

A: TrueType fonts are a popular font format. They are often used in Word documents and have a .ttf or .ttc file extension.

#### Q: Can I specify multiple TrueType font folders in Aspose.Words?

A: Yes, you can specify multiple TrueType font folders in Aspose.Words using the `SetTrueTypeFontsFolder` method of the `Fonts` class with a list of folder locations.

#### Q: How can I check the TrueType fonts folder configured in Aspose.Words?

A: To check the configured TrueType Fonts folder in Aspose.Words, you can use the `GetTrueTypeFontsFolder` method of the `Fonts` class to get the location of the configured TrueType Fonts folder.

#### Q: Why is it important to configure the TrueType fonts folder in Aspose.Words?

A: Setting up the TrueType fonts folder in Aspose.Words is important because it helps Aspose.Words locate the fonts needed when processing Word documents. This ensures consistency in document formatting and appearance, even across different systems.
