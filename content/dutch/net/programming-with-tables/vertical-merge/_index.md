---
title: Verticaal samenvoegen
linktitle: Verticaal samenvoegen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u cellen in een tabel in een Word-document verticaal kunt samenvoegen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-tables/vertical-merge/
---

In deze zelfstudie leren we hoe u cellen in een tabel in een Word-document verticaal kunt samenvoegen met Aspose.Words voor .NET. We zullen een stapsgewijze handleiding volgen om de code te begrijpen en deze functie te implementeren. Aan het einde van deze zelfstudie kunt u cellen in uw tabellen in Word-documenten verticaal samenvoegen.

## Stap 1: Projectconfiguratie
1. Start Visual Studio en maak een nieuw C#-project.
2. Voeg een verwijzing toe naar de Aspose.Words voor .NET-bibliotheek.

## Stap 2: Het document laden
Volg deze stappen om de tekstverwerking met het document te starten:

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Maak een nieuw document
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar uw documentenmap.

## Stap 3: Cellen verticaal samenvoegen
Vervolgens voegen we de cellen verticaal in de tabel samen. Gebruik de volgende code:

```csharp
// Voeg een cel in
builder. InsertCell();

// Pas de verticale samenvoeging toe op de eerste cel
builder.CellFormat.VerticalMerge = CellMerge.First;
builder.Write("Text in merged cells.");

// Voeg nog een cel in
builder. InsertCell();

// Pas geen verticale samenvoeging toe op de cel
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in a cell");
builder. EndRow();

// Voeg een cel in
builder. InsertCell();

// Pas de verticale samenvoeging met de vorige cel toe
builder.CellFormat.VerticalMerge = CellMerge.Previous;

// Voeg nog een cel in
builder. InsertCell();

// Pas geen verticale samenvoeging toe op de cel
builder.CellFormat.VerticalMerge = CellMerge.None;
builder.Write("Text in another cell");
builder. EndRow();

//Beëindig het maken van de tabel
builder. EndTable();
```

In deze code gebruiken we de DocumentBuilder-constructor om cellen in een tabel in te voegen. We passen verticaal samenvoegen toe op cellen met behulp van de eigenschap CellFormat.VerticalMerge. We gebruiken CellMerge.First voor de eerste celsamenvoeging, CellMerge.Previous om samen te voegen met de vorige cel, en CellMerge.None voor geen verticale samenvoeging.

## Stap 4: Het gewijzigde document opslaan
Ten slotte moeten we het gewijzigde document opslaan met de samengevoegde cellen. Gebruik de volgende code:

```csharp
doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

Zorg ervoor dat u het juiste pad en de juiste bestandsnaam voor het uitvoerdocument opgeeft.

### Voorbeeldbroncode voor Vertical Merge met Aspose.Words voor .NET 
```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.First;
	builder.Write("Text in merged cells.");
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in one cell");
	builder.EndRow();
	builder.InsertCell();
	// Deze cel is verticaal samengevoegd met de cel erboven en moet leeg zijn.
	builder.CellFormat.VerticalMerge = CellMerge.Previous;
	builder.InsertCell();
	builder.CellFormat.VerticalMerge = CellMerge.None;
	builder.Write("Text in another cell");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.VerticalMerge.docx");
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u cellen in een tabel in een Word-document verticaal kunt samenvoegen met Aspose.Words voor .NET. Door deze stapsgewijze handleiding te volgen en de meegeleverde C#-code te implementeren, kunt u eenvoudig cellen verticaal in uw tabellen samenvoegen.