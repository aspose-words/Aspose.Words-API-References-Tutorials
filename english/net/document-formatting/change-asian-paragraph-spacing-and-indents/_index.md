---
title: Change Asian Paragraph Spacing And Indents In Word Document
linktitle: Change Asian Paragraph Spacing And Indents In Word Document
second_title: Aspose.Words Document Processing API
description: Learn how to change Asian paragraph spacing and indents in word document with Aspose.Words for .NET.
type: docs
weight: 10
url: /net/document-formatting/change-asian-paragraph-spacing-and-indents/
---
In this tutorial, we will walk you through how to change the spacing and indents of an Asian paragraph using Aspose.Words for .NET. Follow the steps below to understand the source code and apply the changes.

## Step 1: Loading the document

To get started, specify the directory for your documents and load the document containing the Asian typography into a Document object. Here's how:

```csharp
// Path to the documents directory.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(MyDir + "Asian typography.docx");
```

## Step 2: Changing paragraph spacing and indents

We will now modify the spacing and indents of the first paragraph of the Asian document. Here's how:

```csharp
ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
format.CharacterUnitLeftIndent = 10; // Update ParagraphFormat.LeftIndent
format.CharacterUnitRightIndent = 10; // Update ParagraphFormat.RightIndent
format.CharacterUnitFirstLineIndent = 20; // Update ParagraphFormat.FirstLineIndent
format.LineUnitBefore = 5; // Update ParagraphFormat.SpaceBefore
format.LineUnitAfter = 10; // Update ParagraphFormat.SpaceAfter
```

## Step 3: Saving the document

After inserting the text input form field, save the document to the desired location using the `Save` method. Make sure to provide the appropriate file path:

```csharp
doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");
```

### Example source code for Change Asian Paragraph Spacing And Indents using Aspose.Words for .NET

Here is the complete source code for the Edit Asian Paragraph Spacing and Indents feature with Aspose.Words for .NET:

```csharp

	// The path to the documents directory.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	Document doc = new Document(MyDir + "Asian typography.docx");

	ParagraphFormat format = doc.FirstSection.Body.FirstParagraph.ParagraphFormat;
	format.CharacterUnitLeftIndent = 10;       // ParagraphFormat.LeftIndent will be updated
	format.CharacterUnitRightIndent = 10;      // ParagraphFormat.RightIndent will be updated
	format.CharacterUnitFirstLineIndent = 20;  // ParagraphFormat.FirstLineIndent will be updated
	format.LineUnitBefore = 5;                 // ParagraphFormat.SpaceBefore will be updated
	format.LineUnitAfter = 10;                 // ParagraphFormat.SpaceAfter will be updated

	doc.Save(dataDir + "DocumentFormatting.ChangeAsianParagraphSpacingAndIndents.doc");

```

With this code you will be able to change the spacing and indents of an Asian paragraph using Aspose.Words for .NET.

## Conclusion

In this tutorial, we learned how to change the spacing and indents of an Asian paragraph using Aspose.Words for .NET. By modifying the relevant properties of the `ParagraphFormat`, we can control the layout and appearance of Asian paragraphs in a Word document. This feature is useful for customizing the formatting of text with Asian characters and achieving the desired visual presentation in documents with mixed language content.

### FAQ's

#### Q: What does the "Change Asian Paragraph Spacing and Indents" feature in Aspose.Words for .NET do?

A: The "Change Asian Paragraph Spacing and Indents" feature in Aspose.Words for .NET allows you to modify the spacing and indentation properties of an Asian paragraph in a Word document. You can adjust the left and right indents, first-line indent, space before, and space after values to control the layout and appearance of the paragraph.

#### Q: How do I change the spacing and indents of an Asian paragraph using Aspose.Words for .NET?

A: To change the spacing and indents of an Asian paragraph, you need to access the `ParagraphFormat` of the target paragraph and modify its relevant properties. In the example code provided, we access the first paragraph of the document and set the `CharacterUnitLeftIndent`, `CharacterUnitRightIndent`, `CharacterUnitFirstLineIndent`, `LineUnitBefore`, and `LineUnitAfter` properties to adjust the spacing and indents.

#### Q: Can I apply these changes to other paragraphs in the document?

A: Yes, you can apply these changes to other paragraphs in the document by accessing their respective `ParagraphFormat` objects. The example code targets the first paragraph of the document, but you can modify other paragraphs by adjusting the index in the `Paragraphs` collection or using other criteria to select the desired paragraphs.
