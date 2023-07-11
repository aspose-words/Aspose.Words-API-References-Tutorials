---
title: Get Variables
linktitle: Get Variables
second_title: Aspose.Words Document Processing API
description: Step-by-step guide to retrieve document variables with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-document-properties/get-variables/
---

In this tutorial, we will walk you through the C# source code to retrieve variables from a document with Aspose.Words for .NET. This feature allows you to access variables defined in a document.

## Step 1: Project Setup

To get started, create a new C# project in your favorite IDE. Make sure the Aspose.Words for .NET library is referenced in your project.

## Step 2: Loading the document

In this step, we will load the Word document from which we want to retrieve the variables. Use the following code to load the document:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

Replace `"YOUR DOCUMENTS DIRECTORY"` with the actual path of the directory where your document is located.

## Step 3: Retrieving variables

Now we will retrieve the variables defined in the document. Use the following code:

```csharp
string variables = "";
foreach(KeyValuePair<string, string> entry in doc.Variables)
{
     string name = entry.Key;
     string value = entry.Value;
     if (variables == "")
     {
         variables = "Name: " + name + ", " + "Value: " + value;
     }
     else
     {
         variables = variables + "\nName: " + name + ", " + "Value: " + value;
     }
}

Console.WriteLine("\nThe document contains the following variables:\n" + variables);
```

This code iterates over each key-value pair in the document variables and retrieves the name and value of each variable. The variables are then concatenated to display the information for each variable.

### Example source code for Get Variables using Aspose.Words for .NET

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(dataDir + "Document.docx");
	
	string variables = "";
	foreach (KeyValuePair<string, string> entry in doc.Variables)
	{
		string name = entry.Key;
		string value = entry.Value;
		if (variables == "")
		{
			variables = "Name: " + name + "," + "Value: {1}" + value;
		}
		else
		{
			variables = variables + "Name: " + name + "," + "Value: {1}" + value;
		}
	}
	

	Console.WriteLine("\nDocument have following variables " + variables);

```

Be sure to specify the correct document path in the `dataDir` variable.

You have now learned how to retrieve variables from a document using Aspose.Words for .NET. By following the step-by-step guide provided in this tutorial, you can easily access and view variables from your own documents.
