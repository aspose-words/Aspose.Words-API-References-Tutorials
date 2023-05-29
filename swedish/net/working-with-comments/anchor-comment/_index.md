---
title: Ankarekommentar
linktitle: Ankarekommentar
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du förankrar kommentarsvar till specifik text i Word-dokument med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/working-with-comments/anchor-comment/
---

den här omfattande handledningen kommer du att lära dig hur du förankrar kommentarsvar till specifik text i ett Word-dokument med Aspose.Words för .NET. Vi guidar dig genom processen och förser dig med nödvändiga C#-kodavsnitt. I slutet av den här guiden kommer du att kunna associera kommentarer med specifik text i dina dokument.

## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
- Aspose.Words för .NET-biblioteket installerat på ditt system.

## Steg 1: Skapa ett nytt dokument och lägg till text
För att börja, skapa ett nytt dokument med klassen Document och lägg till önskad text:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);
```

## Steg 2: Skapa en kommentar och lägg till kommentarintervall
Skapa sedan en kommentar och associera den med specifik text med CommentRangeStart och CommentRangeEnd-objekt:

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);
```

## Steg 3: Spara dokumentet
Efter att ha förankrat kommentaren till specifik text, spara dokumentet till en fil med hjälp av Spara-metoden för klassen Document:

```csharp
doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");
```

### Exempel på källkod för Anchor Comment Svara med Aspose.Words för .NET
Här är den fullständiga källkoden för att förankra ett kommentarsvar med Aspose.Words för .NET:

```csharp
// Create an instance of the Document.
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document();

// Create three Run objects.
// The first two run some text, while the third runs a Comment

Paragraph para1 = new Paragraph(doc);
Run run1 = new Run(doc, "Some ");
Run run2 = new Run(doc, "text ");
para1.AppendChild(run1);
para1.AppendChild(run2);
doc.FirstSection.Body.AppendChild(para1);

Paragraph para2 = new Paragraph(doc);
Run run3 = new Run(doc, "is ");
Run run4 = new Run(doc, "added ");
para2.AppendChild(run3);
para2.AppendChild(run4);
doc.FirstSection.Body.AppendChild(para2);

Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

// Each of the Run objects has an associated CommentRangeStart and CommentRangeEnd object.

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);

doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");	
```
