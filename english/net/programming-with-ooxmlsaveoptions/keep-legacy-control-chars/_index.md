---
title: Keep Legacy Control Chars
linktitle: Keep Legacy Control Chars
second_title: Aspose.Words for .NET API Reference
description: Learn how to preserve legacy control characters when saving a document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-ooxmlsaveoptions/keep-legacy-control-chars/
---

In this tutorial, we will explore the provided C# source code to preserve legacy control characters when saving a document using Aspose.Words for .NET. This feature allows you to preserve special control characters when converting or saving a document.

## Step 1: Setting up the environment

Before you begin, make sure you've set up your development environment with Aspose.Words for .NET. Make sure you've added the necessary references and imported the appropriate namespaces.

## Step 2: Loading the document

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Legacy control character.doc");
```

In this step, we load the document using the `Document` method and passing the path to the file containing the inherited control characters.

## Step 3: Configuring OOXML backup options

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };
```

In this step, we configure OOXML save options by creating a new `OoxmlSaveOptions` object. We specify the desired save format (here, `FlatOpc`) and enable the `KeepLegacyControlChars` option to keep legacy control characters.

## Step 4: Saving the document with legacy control characters

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
```

In this last step, we save the document using the `Save` method and passing the path to the output file with the `.docx` extension, along with the specified save options.

Now you can run source code to preserve legacy control characters when saving a document. The resulting file will be saved in the specified directory with the name "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx".

### Sample source code for Keep Legacy Control Chars using Aspose.Words for .NET 
```csharp

// Path to your document directory 
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Legacy control character.doc");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions(SaveFormat.FlatOpc) { KeepLegacyControlChars = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.KeepLegacyControlChars.docx", saveOptions);
            
        
```

## Conclusion

In this tutorial, we explored the functionality of preserving legacy control characters when saving a document using Aspose.Words for .NET. We have learned how to preserve those special characters that may be important for proper document formatting or display.

Preserving legacy control characters is especially useful when working with documents that use older or specific features, such as special control characters. By enabling the `KeepLegacyControlChars` option when saving the document, you ensure that these characters are preserved.

Aspose.Words for .NET offers a range of flexible and powerful backup options to meet your document manipulation needs. By using the appropriate options, you can customize the backup process to preserve the specific characteristics of your documents.

Feel free to incorporate this functionality into your Aspose.Words for .NET projects to ensure the integrity and preservation of legacy control characters in your documents.
