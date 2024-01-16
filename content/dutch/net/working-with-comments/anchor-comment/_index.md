---
title: Ankercommentaar
linktitle: Ankercommentaar
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u reacties op opmerkingen kunt verankeren aan specifieke tekst in Word-documenten met behulp van Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-comments/anchor-comment/
---

In deze uitgebreide zelfstudie leert u hoe u reacties op opmerkingen kunt verankeren aan specifieke tekst in een Word-document met behulp van Aspose.Words voor .NET. Wij begeleiden u door het proces en voorzien u van de benodigde C#-codefragmenten. Aan het einde van deze handleiding kunt u opmerkingen koppelen aan specifieke tekst in uw documenten.

## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
- Aspose.Words voor .NET-bibliotheek geïnstalleerd op uw systeem.

## Stap 1: Maak een nieuw document en voeg tekst toe
Maak om te beginnen een nieuw document met behulp van de klasse Document en voeg de gewenste tekst toe:

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

## Stap 2: Maak een opmerking en voeg commentaarbereik toe
Maak vervolgens een opmerking en koppel deze aan specifieke tekst met behulp van de objecten CommentRangeStart en CommentRangeEnd:

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

## Stap 3: Sla het document op
Nadat u de opmerking aan specifieke tekst hebt verankerd, slaat u het document op in een bestand met behulp van de Save-methode van de Document-klasse:

```csharp
doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");
```

### Voorbeeldbroncode voor ankercommentaarantwoord met Aspose.Words voor .NET
Hier is de volledige broncode voor het verankeren van een commentaarantwoord met Aspose.Words voor .NET:

```csharp
// Maak een exemplaar van het document.
string dataDir = "YOUR DOCUMENT DIRECTORY";        
Document doc = new Document();

// Maak drie Run-objecten.
// De eerste twee voeren wat tekst uit, terwijl de derde een commentaar uitvoert

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

// Elk van de Run-objecten heeft een bijbehorend CommentRangeStart- en CommentRangeEnd-object.

CommentRangeStart commentRangeStart = new CommentRangeStart(doc, comment.Id);
CommentRangeEnd commentRangeEnd = new CommentRangeEnd(doc, comment.Id);

run1.ParentNode.InsertAfter(commentRangeStart, run1);
run3.ParentNode.InsertAfter(commentRangeEnd, run3);
commentRangeEnd.ParentNode.InsertAfter(comment, commentRangeEnd);

doc.Save(dataDir + "WorkingWithComments.AnchorComment.doc");	
```

### Veelgestelde vragen

#### Vraag: Wat is een commentaaranker in Aspose.Words voor .NET?

A: In Aspose.Words voor .NET is een commentaaranker een markering die een opmerking verbindt met een specifieke locatie in een document.

#### Vraag: Hoe kan ik een commentaaranker toevoegen aan een Aspose.Words voor .NET-document?

A: Als u een commentaaranker wilt toevoegen aan een Aspose.Words voor .NET-document, volgt u de stappen die in de zelfstudie worden vermeld.

#### Vraag: Hoe krijg ik toegang tot een bestaand commentaaranker in Aspose.Words voor .NET?

 A: U kunt toegang krijgen tot een bestaand commentaaranker in Aspose.Words voor .NET met behulp van de`Comment.Anchor` eigendom.

#### Vraag: Kan ik een commentaaranker in Aspose.Words voor .NET ondersteunen?

 A: Ja, u kunt een commentaaranker in Aspose.Words voor .NET verwijderen met behulp van de`Comment.Remove` methode.

#### Vraag: Hoe kan ik de tekst bewerken van een opmerking die is gekoppeld aan een commentaaranker in Aspose.Words voor .NET?

 A: Om de tekst van een opmerking die is gekoppeld aan een commentaaranker in Aspose.Words voor .NET te wijzigen, kunt u toegang krijgen tot de`Comment.Text` eigendom van de corresponderende`Comment` object en wijzig de tekst indien nodig.

