---
title: Eindnootopties instellen
linktitle: Eindnootopties instellen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u eindnootopties in Word-documenten instelt met Aspose.Words voor .NET. Stap-voor-stap handleiding met voorbeeldbroncode.
type: docs
weight: 10
url: /nl/net/working-with-footnote-and-endnote/set-endnote-options/
---

In deze stapsgewijze zelfstudie laten we u zien hoe u Aspose.Words voor .NET kunt gebruiken om eindnootopties in een Word-document in te stellen. We leggen de meegeleverde C#-broncode uit en laten u zien hoe u deze in uw eigen projecten kunt implementeren.

 Om aan de slag te gaan, moet u ervoor zorgen dat Aspose.Words voor .NET is geïnstalleerd en ingesteld in uw ontwikkelomgeving. Als u dit nog niet hebt gedaan, downloadt en installeert u de bibliotheek van[Aspose.Releases]https://releases.aspose.com/words/net/.

## Stap 1: Initialiseren van het documentobject

 Initialiseer eerst de`Document` object door het pad naar uw brondocument op te geven:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "Document.docx");
```

## Stap 2: Initialiseren van het DocumentBuilder-object

 Initialiseer vervolgens de`DocumentBuilder` object om bewerkingen op het document uit te voeren:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 3: Tekst en eindnoot toevoegen

 Gebruik de`Write` werkwijze van de`DocumentBuilder` object om tekst aan het document toe te voegen, en de`InsertFootnote` methode om een eindnoot in te voegen:

```csharp
builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");
```

## Stap 4: Eindnootopties instellen

 Toegang krijgen tot`EndnoteOptions`eigenschap van het document om de eindnootopties te wijzigen. In dit voorbeeld stellen we de herstartregel in op herstarten op elke pagina en de positie aan het einde van de sectie:

```csharp
EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;
```

## Stap 5: Het document opslaan

Sla ten slotte het gewijzigde document op:

```csharp
doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

Dat is het! U hebt met succes eindnootopties ingesteld in een Word-document met Aspose.Words voor .NET.

### Voorbeeldbroncode voor Set Endnote Options met Aspose.Words voor .NET

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";	
Document doc = new Document(dataDir + "Document.docx");
DocumentBuilder builder = new DocumentBuilder(doc);

builder.Write("Some text");
builder.InsertFootnote(FootnoteType.Endnote, "Footnote text.");

EndnoteOptions option = doc.EndnoteOptions;
option.RestartRule = FootnoteNumberingRule.RestartPage;
option.Position = EndnotePosition.EndOfSection;

doc.Save(dataDir + "WorkingWithFootnotes.SetEndnoteOptions.docx");
```

U kunt deze code gerust in uw eigen projecten gebruiken en aanpassen aan uw specifieke vereisten.

### Veelgestelde vragen

#### Vraag: Hoe kan ik eindnoten opmaken in Aspose.Words?

 A: Om eindnoten op te maken in Aspose.Words, kunt u de`EndnoteOptions` klasse en de`SeparatorNoteTextStyle` eigendom. Met deze eigenschap kunt u de letterstijl, grootte, kleur, enz. voor eindnoten opgeven.

#### Vraag: Is het mogelijk om de nummering van eindnoten in een document aan te passen?

 A: Ja, het is mogelijk om de nummering van eindnoten in een document aan te passen. U kunt gebruik maken van de`RestartRule` En`NumberStyle` eigenschappen van de`EndnoteOptions` class om specifieke herstartregels en nummeringsstijlen te definiëren.

#### Vraag: Hoe kan ik eindnoten in een document plaatsen?

A: Om eindnoten in een document te plaatsen, kunt u de`Position` eigendom van de`EndnoteOptions` klas. U kunt opgeven of eindnoten onderaan elke pagina, aan het einde van elke sectie of aan het einde van het document moeten worden geplaatst.

#### Vraag: Kan ik het nummeringsformaat van de eindnoten aanpassen?

 A: Ja, u kunt het formaat van de eindnootnummering aanpassen in Aspose.Words. Gebruik de`NumberFormat` eigendom van de`EndnoteOptions` class om het gewenste formaat in te stellen, zoals Arabische cijfers, Romeinse cijfers, letters, enz.

#### Vraag: Is het mogelijk om de eindnootnummering tussen secties van een document voort te zetten?

 A: Ja, het is mogelijk om de eindnootnummering tussen secties van een document voort te zetten. Gebruik de`RestartRule` eigendom van de`EndnoteOptions` klasse en stel deze in`RestartContinuous` om de nummering tussen secties door te laten gaan.