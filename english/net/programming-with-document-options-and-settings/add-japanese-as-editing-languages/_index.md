---
title: Add Japanese As Editing Languages
linktitle: Add Japanese As Editing Languages
second_title: Aspose.Words for .NET API Reference
description: Step-by-step guide to add Japanese as an editing language with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-document-options-and-settings/add-japanese-as-editing-languages/
---

In this tutorial, we will take you step by step to understand and implement the functionality of adding Japanese as an editing language with Aspose.Words for .NET. This feature allows you to set language preferences when loading a document and add Japanese as an editing language.

## Step 1: Project Setup

To get started, create a new C# project in your favorite IDE. Make sure the Aspose.Words for .NET library is referenced in your project.

## Step 2: Loading the document

In this step, we will load the Word document that does not contain a default editing language and to which we want to add Japanese. Use the following code to load the document:

```csharp
LoadOptions loadOptions = new LoadOptions();

// Set the language preferences that will be used when loading the document.
loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);

string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);
```

## Step 3: Checking the default language

After loading the document, we will check if the default editing language has been correctly set to Japanese. Use the following code to get the Far Eastern language ID:

```csharp
int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
Console.WriteLine(
	localeIdFarEast == (int) EditingLanguage.Japanese
		? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
		: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");
```

The code checks if the Far Eastern language ID matches that of Japanese. According to the result, it displays a corresponding message.

### Example source code for Add Japanese As Editing Languages using Aspose.Words for .NET

```csharp

	LoadOptions loadOptions = new LoadOptions();
	
	// Set language preferences that will be used when document is loading.
	loadOptions.LanguagePreferences.AddEditingLanguage(EditingLanguage.Japanese);
	
	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "No default editing language.docx", loadOptions);

	int localeIdFarEast = doc.Styles.DefaultFont.LocaleIdFarEast;
	Console.WriteLine(
		localeIdFarEast == (int) EditingLanguage.Japanese
			? "The document either has no any FarEast language set in defaults or it was set to Japanese originally."
			: "The document default FarEast language was set to another than Japanese language originally, so it is not overridden.");

```


