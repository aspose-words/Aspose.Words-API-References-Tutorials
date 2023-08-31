---
title: Configuring Link To Content
linktitle: Configuring Link To Content
second_title: Aspose.Words Document Processing API
description: Step-by-step guide to setting up linking to content in a document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-document-properties/configuring-link-to-content/
---

In this tutorial, we will walk you through the C# source code to set up linking to content with Aspose.Words for .NET. This feature allows you to link to specific content in a document.

## Step 1: Project Setup

To get started, create a new C# project in your favorite IDE. Make sure the Aspose.Words for .NET library is referenced in your project.

## Step 2: Creating the Document and Constructor

In this step we will create a new document and initialize the constructor. Use the following code:

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Step 3: Create a bookmark

Now we will create a bookmark in the document. Use the following code to create a bookmark with text inside:

```csharp
builder. StartBookmark("MyBookmark");
builder.Writeln("Text inside a bookmark.");
builder. EndBookmark("MyBookmark");
```

This code creates a bookmark called "MyBookmark" and adds some text inside.

## Step 4: Setting up the content link

Now we will configure the link to the content using the document properties. Use the following code to add and retrieve the link to the content:

```csharp
// Get the list of all custom properties in the document.
CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
// Add a content-bound property.
DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
customProperty = customProperties["Bookmark"];

bool isLinkedToContent = customProperty.IsLinkToContent;

string linkSource = customProperty.LinkSource;

string customPropertyValue = customProperty.Value.ToString();
```

This code adds a content-related property called "Bookmark" with the bookmark "MyBookmark". Then, it retrieves content-related property information such as link status, link source, and property value.

### Example source code for Configuring Link To Content using Aspose.Words for .NET

```csharp

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	
	builder.StartBookmark("MyBookmark");
	builder.Writeln("Text inside a bookmark.");
	builder.EndBookmark("MyBookmark");

	// Retrieve a list of all custom document properties from the file.
	CustomDocumentProperties customProperties = doc.CustomDocumentProperties;
	// Add linked to content property.
	DocumentProperty customProperty = customProperties.AddLinkToContent("Bookmark", "MyBookmark");
	customProperty = customProperties["Bookmark"];

	bool isLinkedToContent = customProperty.IsLinkToContent;
	
	string linkSource = customProperty.LinkSource;
	
	string customPropertyValue = customProperty.Value.ToString();

```

You have now learned how to configure the link to content in a document using Aspose.Words for .NET. By following the step-by-step guide provided in this tutorial, you can easily create and configure links to specific content in your own documents.
