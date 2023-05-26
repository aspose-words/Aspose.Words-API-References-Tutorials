---
title: Comparison Target
linktitle: Comparison Target
second_title: Aspose.Words for .NET API Reference
description: Learn compare target feature of Aspose.Words for .NET that allows you to compare documents and generate a new document containing the changes made.
type: docs
weight: 10
url: /net/compare-documents/comparison-target/
---

Here is a step-by-step guide to explain the C# source code below, which uses the comparison target functionality of Aspose.Words for .NET.

## Step 1: Introduction

The compare target feature of Aspose.Words for .NET allows you to compare two documents and generate a new document containing the changes made to the target document. This can be useful for tracking changes made between different versions of a document.

## Step 2: Setting up the environment

Before you start, you need to set up your development environment to work with Aspose.Words for .NET. Make sure you have the Aspose.Words library installed and have a suitable C# project to embed the code in.

## Step 3: Add Required Assemblies

To use the comparison target feature of Aspose.Words for .NET, you must add the necessary assemblies to your project. Make sure you have the proper references to Aspose.Words in your project.

```csharp
using Aspose.Words;
```

## Step 4: Document Initialization

In this step, we will initialize two documents for comparison. You must specify the directory path where your documents are located, as well as the name of the source document.

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Initialization of document A to compare.
Document docA = new Document(dataDir + "DocumentA.docx");

// Clone document A to create an identical copy of document B.
Document docB = docA.Clone();
```

## Step 5: Configuring Compare Options

In this step, we will configure the comparison options to specify the behavior of the comparison. Options include the ability to ignore formatting, as well as the comparison target, which is the "Show changes in" option in Microsoft Word's "Compare Documents" dialog box.

```csharp
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };
```

## Step 6: Document Comparison

Now we will compare the documents and generate the result in a new document.

```csharp
docA.Compare(docB, "user", DateTime.Now, options);
```

The `Compare` method compares document A with document B and saves the changes to document A. You can specify the user name and date of comparison for reference.

### Sample source code for Comparison Target using Aspose.Words for .NET


```csharp
            
Document docA = new Document(MyDir + "Document.docx");
Document docB = docA.Clone();

// Relates to Microsoft Word "Show changes in" option in "Compare Documents" dialog box.
CompareOptions options = new CompareOptions { IgnoreFormatting = true, Target = ComparisonTargetType.New };

docA.Compare(docB, "user", DateTime.Now, options);
            
        
```

## Conclusion

In this article, we explored the diff target feature of Aspose.Words for .NET. This feature allows you to compare two documents and generate a new document containing the changes made. You can use this knowledge to track changes between different versions of your documents.


