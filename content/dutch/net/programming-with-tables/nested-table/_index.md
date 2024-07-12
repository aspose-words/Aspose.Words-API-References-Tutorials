---
title: Geneste tabel
linktitle: Geneste tabel
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een geneste tabel in een Word-document maakt met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-tables/nested-table/
---

In deze zelfstudie leren we hoe u een geneste tabel in een Word-document kunt maken met Aspose.Words voor .NET. We zullen een stapsgewijze handleiding volgen om de code te begrijpen en deze functie te implementeren. Aan het einde van deze zelfstudie kunt u programmatisch geneste tabellen in uw Word-documenten maken.

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

## Stap 3: De geneste tabel bouwen
Vervolgens bouwen we de geneste tabel door cellen in de buitenste tabel in te voegen en een nieuwe tabel in de eerste cel te maken. Gebruik de volgende code:

```csharp
// Voeg de eerste cel van de buitenste tabel in
Cell cell = builder. InsertCell();
builder.Writeln("Cell 1 of the outer table");

// Voeg de tweede cel van de buitenste tabel in
builder. InsertCell();
builder.Writeln("Cell 2 of the outer table");

// Beëindiging van de buitenste tafel
builder. EndTable();

// Ga naar de eerste cel van de buitenste tabel
builder.MoveTo(cell.FirstParagraph);

// Bouw de binnentafel
builder. InsertCell();
builder.Writeln("Cell 1 of inner table");
builder. InsertCell();
builder.Writeln("Cell 2 of the inner table");

// Einde van de binnentafel
builder. EndTable();
```

Hier gebruiken we de documentbouwer om cellen en inhoud in de buitenste tabel in te voegen. Vervolgens verplaatsen we de documentbuilder-cursor naar de eerste cel van de buitenste tabel en bouwen we daarbinnen een nieuwe tabel door cellen en inhoud in te voegen.

## Stap 4: Het gewijzigde document opslaan
Ten slotte moeten we het gewijzigde document opslaan met de geneste tabel. Gebruik de volgende code:

```csharp
doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

Zorg ervoor dat u het juiste pad en naambestand voor het uitvoerdocument opgeeft.

### Voorbeeldbroncode voor geneste tabel met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Cell cell = builder.InsertCell();
	builder.Writeln("Outer Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Outer Table Cell 2");
	// Deze aanroep is belangrijk om een geneste tabel binnen de eerste tabel te maken.
	//Zonder deze aanroep worden de hieronder ingevoegde cellen aan de buitenste tabel toegevoegd.
	builder.EndTable();
	// Ga naar de eerste cel van de buitenste tabel.
	builder.MoveTo(cell.FirstParagraph);
	// Bouw de binnentafel.
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 1");
	builder.InsertCell();
	builder.Writeln("Inner Table Cell 2");
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.NestedTable.docx");
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u een geneste tabel in een Word-document kunt maken met Aspose.Words voor .NET. Door deze stapsgewijze handleiding te volgen en de meegeleverde C#-code te implementeren, kunt u programmatisch geneste tabellen maken in uw Word-documenten op basis van uw specifieke behoeften.
