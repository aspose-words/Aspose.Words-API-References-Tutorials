---
title: Receive Notifications Of Fonts
linktitle: Receive Notifications Of Fonts
second_title: Aspose.Words for .NET API Reference
description: Learn how to receive missing or substituted font notifications when using Aspose.Words for .NET.
type: docs
weight: 10
url: /net/working-with-fonts/receive-notifications-of-fonts/
---

In this tutorial, we will walk you through how to receive font notifications while using Aspose.Words for .NET. Font notifications let you detect and manage missing or substituted fonts in your documents. We'll take you step-by-step to help you understand and implement the code in your .NET project.

## Prerequisites
Before you begin, make sure you have the following items:
- A working knowledge of the C# programming language
- The Aspose.Words library for .NET installed in your project

## Step 1: Define the document directory
First, you need to set the directory path to the location of your Word document. Replace `"YOUR DOCUMENT DIRECTORY"` in the code with the appropriate path.

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Step 2: Load the document and configure the font settings
Next, we'll load the document using the `Document` class and configure the font settings using the `FontSettings` class. We will set the default font to use in case of missing fonts.

```csharp
// Load the document and configure the font settings
Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
```

## Step 3: Set notification handler
Next, we will define a notification handler by implementing the `IWarningCallback` interface. This will allow us to collect font warnings when saving the document.

```csharp
// Define the notification handler
HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc. WarningCallback = callback;
```

## Step 4: Apply font settings and save the document
Finally, we'll apply the font settings to the document and save it. Any font warnings will be captured by the notification handler we defined earlier.

```csharp
// Apply font settings and save the document
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.ReceiveNotificationsOfFonts.pdf");
```

### Sample source code for Receive Notifications Of Fonts using Aspose.Words for .NET 
```csharp

// Path to your document directory 
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Rendering.docx");
FontSettings fontSettings = new FontSettings();
// We can choose the default font to use in the case of any missing fonts.
fontSettings.SubstitutionSettings.DefaultFontSubstitution.DefaultFontName = "Arial";
// For testing we will set Aspose.Words to look for fonts only in a folder which doesn't exist. Since Aspose.Words won't
// find any fonts in the specified directory, then during rendering the fonts in the document will be subsuited with the default
// font specified under FontSettings.DefaultFontName. We can pick up on this subsuition using our callback.
fontSettings.SetFontsFolder(string.Empty, false);
// Create a new class implementing IWarningCallback which collect any warnings produced during document save.
HandleDocumentWarnings callback = new HandleDocumentWarnings();
doc.WarningCallback = callback;
doc.FontSettings = fontSettings;
doc.Save(dataDir + "WorkingWithFonts.ReceiveNotificationsOfFonts.pdf");

```

## Conclusion
In this tutorial, we saw how to receive font notifications while using Aspose.Words for .NET. Font notifications let you detect and manage missing or substituted fonts in your documents. Use this feature to ensure font consistency in your documents and take appropriate action in case of missing fonts.

