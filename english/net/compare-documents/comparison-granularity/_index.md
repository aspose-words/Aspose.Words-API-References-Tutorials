---
title: Comparison Granularity
linktitle: Comparison Granularity
second_title: Aspose.Words Document Processing API
description: Learn Compare Granularity feature of Aspose.Words for .NET that allows documents to be compared character by character, reporting changes made.
type: docs
weight: 10
url: /net/compare-documents/comparison-granularity/
---
Here is a step-by-step guide to explain the C# source code below, which uses the Compare Granularity feature of Aspose.Words for .NET.

## Step 1: Introduction

The Compare Granularity feature of Aspose.Words for .NET allows you to compare documents at the character level. This means that each character will be compared and changes will be reported accordingly.

## Step 2: Setting up the environment

Before you start, you need to set up your development environment to work with Aspose.Words for .NET. Make sure you have the Aspose.Words library installed and have a suitable C# project to embed the code in.

## Step 3: Add Required Assemblies

To use the Compare Granularity feature of Aspose.Words for .NET, you need to add the necessary assemblies to your project. Make sure you have the proper references to Aspose.Words in your project.

```csharp
using Aspose.Words;
using Aspose.Words.DocumentBuilder;
```

## Step 4: Creating Documents

In this step, we will create two documents using the DocumentBuilder class. These documents will be used for the comparison.

```csharp
// Create document A.
DocumentBuilder builderA = new DocumentBuilder(new Document());
builderA.Writeln("This is a simple A word.");

// Create document B.
DocumentBuilder builderB = new DocumentBuilder(new Document());
builderB.Writeln("This is simple B words.");
```

## Step 5: Configuring Compare Options

In this step, we will configure the comparison options to specify the comparison granularity. Here we will use character-level granularity.

```csharp
CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };
```

## Step 6: Document Comparison

Now let's compare the documents using the Compare method of the Document class. Changes will be saved in document A.

```csharp
builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);
```

The `Compare` method compares document A with document B and saves the changes to document A. You can specify the author's name and the date of comparison for reference.

## Conclusion

In this article, we explored the Compare Granularity feature of Aspose.Words for .NET. This feature allows you to compare documents at the character level and report changes. You can use this knowledge to perform detailed document comparisons in your projects.

### Sample source code for Comparison Granularity using Aspose.Words for .NET

```csharp
            
DocumentBuilder builderA = new DocumentBuilder(new Document());
DocumentBuilder builderB = new DocumentBuilder(new Document());

builderA.Writeln("This is A simple word");
builderB.Writeln("This is B simple words");

CompareOptions compareOptions = new CompareOptions { Granularity = Granularity.CharLevel };

builderA.Document.Compare(builderB.Document, "author", DateTime.Now, compareOptions);            
        
```

