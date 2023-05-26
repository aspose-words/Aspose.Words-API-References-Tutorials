---
title: Hyphenation Callback
linktitle: Hyphenation Callback
second_title: Aspose.Words for .NET API Reference
description: Learn how to use hyphenation callback in Aspose.Words for .NET to handle word hyphenation.
type: docs
weight: 10
url: /net/working-with-hyphenation/hyphenation-callback/
---

In this step-by-step tutorial, we will show you how to use the hyphenation callback feature in Aspose.Words for .NET. We'll explain the provided C# source code and show you how to implement it in your own projects.

To get started, make sure you have Aspose.Words for .NET installed and configured in your development environment. If you haven't already, download and install the library from the official site.

## Step 1: Save Hyphenation Reminder

First, we'll register the hyphenation callback using a custom `CustomHyphenationCallback` class. This will allow us to handle word hyphenation according to our own rules:

```csharp
Hyphenation.Callback = new CustomHyphenationCallback();
```

Make sure you have implemented the `CustomHyphenationCallback` class according to your specific needs.

## Step 2: Loading the document and applying hyphenation

Next, load your document from the specified directory and hyphenate the words using Aspose.Words:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "German text.docx");
document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
```

## Step 3: Handling Missing Dictionary Errors

In case a hyphenation dictionary is missing, we will catch the corresponding exception and display an error message:

```csharp
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
     Console.WriteLine(e.Message);
}
```

## Step 4: Cleanup and Disable Hyphenation Reminder

Finally, for cleanliness and to turn off the hyphenation reminder, perform the following steps:

```csharp
finally
{
     Hyphenation. Callback = null;
}
```

This cleans up and disables the hyphenation reminder after finishing processing.

So ! You have successfully used hyphenation callback in Aspose.Words for .NET.

### Sample Source Code for Hyphenation Callback with Aspose.Words for .NET

```csharp
try
{
	 // Register hyphenation callback.
	 Hyphenation.Callback = new CustomHyphenationCallback();
	 string dataDir = "YOUR DOCUMENT DIRECTORY";
	 Document document = new Document(dataDir + "German text.docx");
	 document.Save(dataDir + "TreatmentByCesureWithRecall.pdf");
}
catch (Exception e) when (e.Message.StartsWith("Missing hyphenation dictionary"))
{
	 Console.WriteLine(e.Message);
}
finally
{
	 Hyphenation. Callback = null;
}

```

Feel free to use this code in your own projects and modify it to suit your specific needs.