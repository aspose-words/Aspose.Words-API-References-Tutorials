---
title: Insert TCField
linktitle: Insert TCField
second_title: Aspose.Words for .NET API Reference
description: Learn how to insert and manipulate TCFields in Word documents using C# and Aspose.Words for .NET in this step-by-step guide.
type: docs
weight: 10
url: /net/add-content-using-documentbuilder/insert-tcfield/
---

In this example, we will guide you through the process of using the Insert TCField feature of Aspose.Words for .NET. The TCField represents a table of contents entry in a Word document. We will provide a step-by-step explanation of the C# source code, along with the expected output in markdown format. Let's get started!

## Step 1: Initializing the document and document builder

To begin, we need to initialize the document and the document builder. The document builder is a powerful tool provided by Aspose.Words for .NET that allows us to construct and manipulate Word documents programmatically. Here's how you can do it:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 2: Inserting the TCField

Next, we will insert the TCField into the document using the `InsertField` method. The TCField represents a table of contents entry with the specified entry text. Here's an example:

```csharp
builder.InsertField("TC \"Entry Text\" \\f t");
```

The above code will insert a TCField with the entry text "Entry Text" into the document.

## Step 3: Saving the document

After inserting the TCField, we can save the document to a specific location using the `Save` method. Make sure to provide the desired path and filename for the output document. Here's an example:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTCField.docx");
```

The above code will save the document with the TCField to the specified directory.

## Output Markdown Formats

When the code is executed successfully, the output document will contain a table of contents entry with the specified entry text. The TCField is represented as a field in the Word document, and the resulting markdown format will depend on how the document is processed.

Please note that the output document is not directly in markdown format but rather in Word format. However, when you convert the Word document to markdown using appropriate tools or libraries, the TCField will be processed accordingly.

### Example Source Code for Insert TCField using Aspose.Words for .NET

Here's the complete example source code for inserting a TCField using Aspose.Words for .NET:

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	
	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);

	builder.InsertField("TC \"Entry Text\" \\f t");

	doc.Save(dataDir + "AddContentUsingDocumentBuilder.InsertTCField.docx");
			
```

Feel free to modify the code according to your requirements and explore other features provided by Aspose.Words for .NET.

That's it! You have successfully learned how to insert a TCField using Aspose.Words for .NET.


