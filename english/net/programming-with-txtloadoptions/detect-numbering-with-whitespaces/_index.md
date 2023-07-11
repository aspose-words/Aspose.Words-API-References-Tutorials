---
title: Detect Numbering With Whitespaces
linktitle: Detect Numbering With Whitespaces
second_title: Aspose.Words Document Processing API
description: Learn how to detect list numbers with white spaces in Aspose.Words for .NET. Improve the structure of your documents with ease.
type: docs
weight: 10
url: /net/programming-with-txtloadoptions/detect-numbering-with-whitespaces/
---
In this tutorial, we will explore the C# source code provided for the "Detection of numbering with white spaces" feature with Aspose.Words for .NET. This feature allows you to detect and create lists from a text document containing list numbers followed by white spaces.

## Step 1: Setting up the environment

Before you begin, make sure you've set up your development environment with Aspose.Words for .NET. Make sure you've added the necessary references and imported the appropriate namespaces.

## Step 2: Creating the text document

```csharp
// Path to your documents directory
string dataDir = "YOUR DOCUMENTS DIRECTORY";

string textDoc = "Full stop delimiters:\n" +
                  "1. First list item 1\n" +
                  "2. First list item 2\n" +
                  "3. First list item 3\n\n" +
                  "Right bracket delimiters:\n" +
                  "1) Second list item 1\n" +
                  "2) Second list item 2\n" +
                  "3) Second list item 3\n\n" +
                  "Bullet delimiters:\n" +
                  "• Third list item 1\n" +
                  "• Third list item 2\n" +
                  "• Third list item 3\n\n" +
                  "Whitespace delimiters:\n" +
                  "1 Fourth list item 1\n" +
                  "2 Fourth list item 2\n" +
                  "3 Fourth list item 3";
```

In this step, we create a text string that simulates a text document containing list numbers followed by white spaces. We use different list delimiters such as period, right bracket, bullet symbol and white spaces.

## Step 3: Configuring upload options

```csharp
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };
```

In this step, we configure the document loading options. We create a new `TxtLoadOptions` object and set the `DetectNumberingWithWhitespaces` property to `true`. This will allow Aspose.Words to detect list numbers even if they are followed by white spaces.

## Step 4: Loading the document and saving

```csharp
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
```

In this step, we load the document using the specified text string and load options. We use a `MemoryStream` to convert the text string to a memory stream. Then we save the resulting document in .docx format.

### Sample source code for White Space Numbering Detection feature with Aspose.Words for .NET.

```csharp

            
// Path to your document directory
string dataDir = "YOUR DOCUMENT DIRECTORY";
			
// Create a plaintext document in the form of a string with parts that may be interpreted as lists.
// Upon loading, the first three lists will always be detected by Aspose.Words,
// and List objects will be created for them after loading.
const string textDoc = "Full stop delimiters:\n" +
					   "1. First list item 1\n" +
					   "2. First list item 2\n" +
					   "3. First list item 3\n\n" +
					   "Right bracket delimiters:\n" +
					   "1) Second list item 1\n" +
					   "2) Second list item 2\n" +
					   "3) Second list item 3\n\n" +
					   "Bullet delimiters:\n" +
					   "• Third list item 1\n" +
					   "• Third list item 2\n" +
					   "• Third list item 3\n\n" +
					   "Whitespace delimiters:\n" +
					   "1 Fourth list item 1\n" +
					   "2 Fourth list item 2\n" +
					   "3 Fourth list item 3";

// The fourth list, with whitespace inbetween the list number and list item contents,
// will only be detected as a list if "DetectNumberingWithWhitespaces" in a LoadOptions object is set to true,
// to avoid paragraphs that start with numbers being mistakenly detected as lists.
TxtLoadOptions loadOptions = new TxtLoadOptions { DetectNumberingWithWhitespaces = true };

// Load the document while applying LoadOptions as a parameter and verify the result.
Document doc = new Document(new MemoryStream(Encoding.UTF8.GetBytes(textDoc)), loadOptions);

doc.Save(dataDir + "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx");
            
        
```

Now you can run the source code to load the text document containing list numbers with white spaces, then create a .docx document with the detected lists. The output file will be saved in the specified directory with the name "WorkingWithTxtLoadOptions.DetectNumberingWithWhitespaces.docx".

## Conclusion
In this tutorial, we explored the whitespace numbering detection feature in Aspose.Words for .NET. We learned how to create lists from a text document containing list numbers followed by white spaces.

This feature is extremely useful for processing documents containing list numbers formatted in different ways. By using the appropriate loading options, Aspose.Words is able to detect these list numbers, even if they are followed by white spaces, and convert them into structured lists in the final document.

Using this feature can save you time and improve your workflow efficiency. You can easily extract information from text documents and convert them into well-structured documents with proper lists.

Remember to consider loading options, such as configuring white space dialing detection, to achieve the desired results.

Aspose.Words for .NET offers many advanced features for document manipulation and generation. By further exploring the documentation and examples provided by Aspose.Words, you will be able to fully exploit the capabilities of this powerful library.

So, don't hesitate to integrate whitespace numbering detection into your Aspose.Words for .NET projects and take advantage of its benefits to create well-structured and readable documents.



