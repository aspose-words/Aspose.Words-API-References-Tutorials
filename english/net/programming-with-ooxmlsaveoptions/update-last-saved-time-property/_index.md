---
title: Update Last Saved Time Property
linktitle: Update Last Saved Time Property
second_title: Aspose.Words Document Processing API
description: Learn how to automatically update the Last Saved Time property when saving a document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-ooxmlsaveoptions/update-last-saved-time-property/
---
In this tutorial, we will explore the provided C# source code to update the last save time property when saving a document using Aspose.Words for .NET. This feature allows you to automatically update the last save time property of the generated document.

## Step 1: Setting up the environment

Before you begin, make sure you've set up your development environment with Aspose.Words for .NET. Make sure you've added the necessary references and imported the appropriate namespaces.

## Step 2: Loading the document

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

Document doc = new Document(dataDir + "Document.docx");
```

In this step, we load the document using the `Document` method and passing the path to the DOCX file to load.

## Step 3: Configuring OOXML backup options

```csharp
OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };
```

In this step, we configure OOXML save options using the `OoxmlSaveOptions` class. We enable automatic updating of the last save time property by setting `UpdateLastSavedTimeProperty` to `true`.

## Step 4: Save document with updated property

```csharp
doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
```

In this last step, we save the document using the `Save` method and passing the path to the output file with the `.docx` extension, along with the specified save options.

Now you can run the source code to automatically update the last save time property when saving a document. The resulting file will be saved in the specified directory with the name "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx".

### Sample source code for Update Last Saved Time Property using Aspose.Words for .NET 

```csharp

// Path to your document directory 
string dataDir = "YOUR DOCUMENT DIRECTORY"; 

Document doc = new Document(dataDir + "Document.docx");

OoxmlSaveOptions saveOptions = new OoxmlSaveOptions { UpdateLastSavedTimeProperty = true };

doc.Save(dataDir + "WorkingWithOoxmlSaveOptions.UpdateLastSavedTimeProperty.docx", saveOptions);
            
        
```

## Conclusion

In this tutorial, we explored the feature of automatically updating the last save time property when saving a document using Aspose.Words for .NET. By enabling this feature with OOXML save options, you can ensure that the last save time property is updated automatically in the generated document.

Updating the last save time property can be useful for tracking changes and versions of a document. It also keeps track of when the document was last saved, which can be useful in various scenarios.

Aspose.Words for .NET makes it easy to automatically update the Last Backup Time property by providing flexible and powerful backup options. You can integrate this feature into your projects to ensure that generated documents have accurate backup information.