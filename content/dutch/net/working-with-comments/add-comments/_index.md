---
title: Commentaar toevoegen
linktitle: Commentaar toevoegen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u opmerkingen aan Word-documenten kunt toevoegen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-comments/add-comments/
---

In deze uitgebreide zelfstudie leert u hoe u opmerkingen aan een Word-document kunt toevoegen met Aspose.Words voor .NET. Wij begeleiden u door het proces en voorzien u van de benodigde C#-codefragmenten. Aan het einde van deze handleiding kunt u opmerkingen invoegen en de inhoud ervan in uw documenten aanpassen.

## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
- Aspose.Words voor .NET-bibliotheek geïnstalleerd op uw systeem.

## Stap 1: Maak een nieuw document en DocumentBuilder
Maak om te beginnen een nieuw document met behulp van de klasse Document en initialiseer een DocumentBuilder-object:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 2: Voeg inhoud toe aan het document
Voeg vervolgens de gewenste inhoud aan het document toe met behulp van het DocumentBuilder-object. In dit voorbeeld voegen we wat tekst toe:

```csharp
builder.Write("Some text is added.");
```

## Stap 3: Maak een opmerking en voeg inhoud toe
Om een opmerking toe te voegen, maakt u een exemplaar van de klasse Commentaar, waarbij u het Document-object, de naam van de auteur, de initialen van de auteur en de huidige datum doorgeeft:

```csharp
Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
```

Voeg vervolgens de opmerking toe aan de huidige paragraaf:

```csharp
builder.CurrentParagraph.AppendChild(comment);
```

Voeg inhoud toe aan de opmerking, zoals een alinea en tekst:

```csharp
comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));
```

## Stap 4: Sla het document op
Nadat u de opmerking en de inhoud ervan hebt toegevoegd, slaat u het document op in een bestand met behulp van de Save-methode van de Document-klasse:

```csharp
doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## Voorbeeldbroncode voor het toevoegen van opmerkingen met Aspose.Words voor .NET
Hier is de volledige broncode voor het toevoegen van opmerkingen met Aspose.Words voor .NET:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text is added.");

Comment comment = new Comment(doc, "Awais Hafeez", "AH", DateTime.Today);
builder.CurrentParagraph.AppendChild(comment);

comment.Paragraphs.Add(new Paragraph(doc));
comment.FirstParagraph.Runs.Add(new Run(doc, "Comment text."));

doc.Save(dataDir + "WorkingWithComments.AddComments.docx");
```

## Conclusie
Gefeliciteerd! U hebt met succes geleerd hoe u opmerkingen aan een Word-document kunt toevoegen met Aspose.Words voor .NET. Door de stapsgewijze handleiding te volgen en de meegeleverde broncode te gebruiken, kunt u nu opmerkingen invoegen en de inhoud ervan in uw documenten aanpassen.

Opmerkingen zijn handig voor samenwerking, het verstrekken van aanvullende informatie of het maken van aantekeningen in een document. Experimenteer met verschillende auteursnamen, initialen en commentaarinhoud om aan uw specifieke vereisten te voldoen.

### Veelgestelde vragen

#### Vraag: Hoe kan ik een opmerking toevoegen aan een Aspose.Words voor .NET-document?

A: Om commentaar toe te voegen aan een Aspose.Words voor .NET-document, moet u de stappen volgen die in de tutorial worden vermeld.

#### Vraag: Kan ik commentaartekst opmaken in Aspose.Words voor .NET?

A: Ja, u kunt commentaartekst in Aspose.Words voor .NET opmaken met behulp van de beschikbare opmaakeigenschappen.

#### Vraag: Hoe kan ik alle opmerkingen in een document ophalen?

A: U kunt alle opmerkingen in een document ophalen met behulp van de`Document.Comments` eigendom.

#### Vraag: Kan ik een specifieke opmerking in Aspose.Words voor .NET verwijderen?

 A: Ja, u kunt een specifieke opmerking in Aspose.Words voor .NET verwijderen met behulp van de`Comment.Remove` methode.

#### Vraag: Hoe kan ik de tekst van een bestaand commentaar in Aspose.Words voor .NET wijzigen?

 A: Om de tekst van een bestaand commentaar in Aspose.Words voor .NET te wijzigen, kunt u toegang krijgen tot het`Comment.Text` eigendom van de corresponderende`Comment` object en wijzig de tekst indien nodig.