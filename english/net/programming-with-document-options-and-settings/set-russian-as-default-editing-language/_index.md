---
title: Set Russian As Default Editing Language
linktitle: Set Russian As Default Editing Language
second_title: Aspose.Words for .NET API Reference
description: Step-by-step guide to set Russian as the default editing language of a document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-document-options-and-settings/set-russian-as-default-editing-language/
---

In this tutorial, we will walk you through the C# source code to set Russian as the default editing language with Aspose.Words for .NET. This feature allows you to set the default language when loading a document.

## Step 1: Project Setup

To get started, create a new C# project in your favorite IDE. Make sure the Aspose.Words for .NET library is referenced in your project.

## Step 2: Loading the document

In this step, we will load the Word document for which we want to set Russian as the default editing language. Use the following code to load the document:

```csharp
LoadOptions loadOptions = new LoadOptions();
loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;

// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

Replace `"YOUR DOCUMENTS DIRECTORY"` with the actual path of the directory where your document is located.

## Step 3: Checking the default language

After uploading the document, we will check if the default language has been correctly set to Russian. Use the following code to get the default language ID:

```csharp
int localeId = doc.Styles.DefaultFont.LocaleId;
Console.WriteLine(
	localeId == (int) EditingLanguage.Russian
		? "The document either has no any language set in defaults or it was set to Russian originally."
		: "The document default language was set to another than Russian language originally, so it is not overridden.");
```

The code checks if the language ID matches that of Russian. According to the result, it displays a corresponding message.

### Example source code for Set Russian As Default Editing Language using Aspose.Words for .NET

```csharp

	LoadOptions loadOptions = new LoadOptions();
	loadOptions.LanguagePreferences.DefaultEditingLanguage = EditingLanguage.Russian;
	
	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeId = doc.Styles.DefaultFont.LocaleId;
	Console.WriteLine(
		localeId == (int) EditingLanguage.Russian
			? "The document either has no any language set in defaults or it was set to Russian originally."
			: "The document default language was set to another than Russian language originally, so it is not overridden.");

```

Be sure to specify the correct document path in the `dataDir` variable.

You have now learned how to set Russian as the default editing language for a document using Aspose.Words for .NET. By following the step guide
