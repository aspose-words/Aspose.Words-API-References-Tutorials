---
title: Herhaal rijen op volgende pagina's
linktitle: Herhaal rijen op volgende pagina's
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u tabelrijen op volgende pagina's in een Word-document kunt herhalen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-tables/repeat-rows-on-subsequent-pages/
---

In deze zelfstudie leren we hoe u de rijen van een tabel op volgende pagina's van een Word-document kunt herhalen met behulp van Aspose.Words voor .NET. We zullen een stapsgewijze handleiding volgen om de code te begrijpen en deze functie te implementeren. Aan het einde van deze zelfstudie kunt u rijen opgeven die u op volgende pagina's van uw tabel in uw Word-documenten wilt herhalen.

## Stap 1: Projectconfiguratie
1. Start Visual Studio en maak een nieuw C#-project.
2. Voeg een verwijzing toe naar de Aspose.Words voor .NET-bibliotheek.

## Stap 2: Het document aanmaken en de documentgenerator initialiseren
Volg deze stappen om Woordenverwerking te starten met de document- en documentgenerator:

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Documentcreatie
Document doc = new Document();

// Initialiseer de documentgenerator
DocumentBuilder builder = new DocumentBuilder(doc);
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar uw documentenmap.

## Stap 3: De tabel opbouwen met herhaalde rijen
Vervolgens bouwen we een tabel met herhaalde rijen op volgende pagina's. Gebruik de volgende code:

```csharp
// Begin van de tafel
builder. StartTable();

// Configuratie van de eerste regelparameters (kopregels)
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;

// Voeg de eerste cel van de eerste rij in
builder. InsertCell();
builder.Writeln("Header line 1");
builder. EndRow();

// Voeg de tweede cel van de eerste rij in
builder. InsertCell();
builder.Writeln("Header line 2");
builder. EndRow();

// Configureer de parameters van de volgende regels
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();

// Lus om de cellen in de volgende rijen in te voegen
for (int i = 0; i < 50; i++)
{
builder. InsertCell();
builder.RowFormat.HeadingFormat = false;
builder.Write("Text column 1");
builder. InsertCell();
builder.Write("Text column 2");
builder. EndRow();
}

// Einde van tafel
builder. EndTable();
```

 Hier gebruiken we de documentbouwer om een tabel te bouwen met twee koprijen en meerdere gegevensrijen. De`RowFormat.HeadingFormat` parameters worden gebruikt om koprijen te markeren die op volgende pagina's moeten worden herhaald.

## Stap 4: Het gewijzigde document opslaan
Eindelijk VS

  moet het gewijzigde document opslaan met de koprijen herhaald op volgende pagina's van de tabel. Gebruik de volgende code:

```csharp
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

Zorg ervoor dat u het juiste pad en de juiste bestandsnaam voor het uitvoerdocument opgeeft.

### Voorbeeldbroncode voor herhaalde rijen op volgende pagina's met Aspose.Words voor .NET 

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.StartTable();
builder.RowFormat.HeadingFormat = true;
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.CellFormat.Width = 100;
builder.InsertCell();
builder.Writeln("Heading row 1");
builder.EndRow();
builder.InsertCell();
builder.Writeln("Heading row 2");
builder.EndRow();
builder.CellFormat.Width = 50;
builder.ParagraphFormat.ClearFormatting();
for (int i = 0; i < 50; i++)
{
	builder.InsertCell();
	builder.RowFormat.HeadingFormat = false;
	builder.Write("Column 1 Text");
	builder.InsertCell();
	builder.Write("Column 2 Text");
	builder.EndRow();
}
doc.Save(dataDir + "WorkingWithTables.RepeatRowsOnSubsequentPages.docx");
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe we de rijen van een tabel kunnen herhalen op volgende pagina's van een Word-document met Aspose.Words voor .NET. Door deze stapsgewijze handleiding te volgen en de meegeleverde C#-code te implementeren, kunt u opgeven welke regels u volgens uw specifieke behoeften in uw Word-documenten moet herhalen.