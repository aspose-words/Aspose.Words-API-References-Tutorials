---
title: Use Control Characters
linktitle: Use Control Characters
second_title: Aspose.Words Document Processing API
description: Step-by-step guide to using control characters with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/programming-with-document-properties/use-control-characters/
---

In this tutorial, we will walk you through the C# source code for using control characters with Aspose.Words for .NET. This feature allows you to manipulate control characters in text.

## Step 1: Project Setup

To get started, create a new C# project in your favorite IDE. Make sure the Aspose.Words for .NET library is referenced in your project.

## Step 2: Using control characters

In this step, we are going to use control characters in a text. Use the following code:

```csharp
const string text = "test\r";
// Replace control character "\r" with "\r\n".
string replace = text.Replace(ControlChar.Cr, ControlChar.CrLf);
```

This code defines a `text` string containing the control character "\r" (newline) and uses the `Replace` method to replace it with the control character "\r\n" (newline). line followed by a line break).

### Example source code for Use Control Characters using Aspose.Words for .NET

```csharp

	const string text = "test\r";
	// Replace "\r" control character with "\r\n".
	string replace = text.Replace(ControlChar.Cr, ControlChar.CrLf);

```
You can use the above code in your own project by replacing the `text` string with your own text containing control characters.

You have now learned how to use control characters with Aspose.Words for .NET. By following the step-by-step guide provided in this tutorial, you can easily manipulate control characters in your own applications.
