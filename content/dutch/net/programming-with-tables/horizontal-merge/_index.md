---
title: Horizontaal samenvoegen
linktitle: Horizontaal samenvoegen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u cellen in een Word-tabel horizontaal samenvoegt met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-tables/horizontal-merge/
---

In deze zelfstudie leren we hoe u cellen in een tabel in een Word-document horizontaal kunt samenvoegen met Aspose.Words voor .NET. We zullen een stapsgewijze handleiding volgen om de code te begrijpen en deze functie te implementeren. Aan het einde van deze zelfstudie kunt u cellen programmatisch horizontaal in uw Word-tabellen samenvoegen.

## Stap 1: Projectconfiguratie
1. Start Visual Studio en maak een nieuw C#-project.
2. Voeg een verwijzing toe naar de Aspose.Words voor .NET-bibliotheek.

## Stap 2: Het document aanmaken en de documentgenerator initialiseren
Om Woordenverwerking met de tabel en cellen te starten, moeten we een nieuw document maken en de documentgenerator initialiseren. Volg deze stappen:

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Maak het document en initialiseer de documentgenerator
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar uw documentenmap.

## Stap 3: De tabel bouwen met horizontaal samenvoegen van cellen
Vervolgens bouwen we de tabel en passen we horizontale celsamenvoeging toe met behulp van de eigenschappen van Aspose.Words voor .NET. Gebruik de volgende code:

```csharp
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.First;
builder.Write("Text in merged cells.");
builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.Previous;
// Deze cel is samengevoegd met de vorige en moet leeg zijn.
builder. EndRow();

builder. InsertCell();
builder.CellFormat.HorizontalMerge = CellMerge.None;
builder.Write("Text in a cell.");
builder. InsertCell();
builder.Write("Text in another cell.");
builder. EndRow();
builder. EndTable();
```

 Hier gebruiken we de documentbouwer om de tabel samen te stellen en de horizontale samenvoegeigenschappen van de cel in te stellen. Wij gebruiken de`HorizontalMerge` eigendom van de`CellFormat` object om het type horizontale samenvoeging op te geven dat op elke cel moet worden toegepast. Gebruik makend van`CellMerge.First` we voegen de eerste cel samen met de volgende, terwijl we gebruiken`CellMerge.Previous` we voegen de huidige cel samen met de vorige cel.`CellMerge.None` geeft aan dat de cel niet mag worden samengevoegd.

## Stap 4: Het gewijzigde document opslaan
Ten slotte moeten we het gewijzigde document opslaan met de cellen horizontaal samengevoegd. Gebruik de volgende code:

```csharp
doc.Save(data

Dir + "WorkingWithTables.HorizontalMerge.docx");
```

Zorg ervoor dat u het juiste pad en de juiste bestandsnaam voor het uitvoerdocument opgeeft.

### Voorbeeldbroncode voor Horizontal Merge met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	// Deze cel wordt samengevoegd met de vorige en moet leeg zijn.
	builder.CellFormat.HorizontalMerge = CellMerge.Previous;
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.HorizontalMerge = CellMerge.None;
	builder.Write("Text in one cell.");
	builder.InsertCell();
	builder.Write("Text in another cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.HorizontalMerge.docx");
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u cellen in een tabel in een Word-document horizontaal kunt samenvoegen met Aspose.Words voor .NET. Door deze stapsgewijze handleiding te volgen en de meegeleverde C#-code te implementeren, kunt u programmatisch horizontale celsamenvoeging in uw Word-tabellen toepassen. Met deze functie kunt u complexere tabelindelingen maken en uw gegevens beter organiseren.