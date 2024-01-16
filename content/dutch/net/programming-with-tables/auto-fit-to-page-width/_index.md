---
title: Automatisch aanpassen aan paginabreedte
linktitle: Automatisch aanpassen aan paginabreedte
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een tabel automatisch aanpast aan de paginabreedte in een Word-document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-tables/auto-fit-to-page-width/
---

In deze zelfstudie leren we hoe u Aspose.Words voor .NET kunt gebruiken om een tabel automatisch aan te passen aan de paginabreedte in een Word-document. We zullen een stapsgewijze handleiding volgen om de code te begrijpen en deze functie te implementeren. Aan het einde van deze zelfstudie kunt u tabellen in Word-documenten programmatisch manipuleren.

## Stap 1: Projectconfiguratie
1. Start Visual Studio en maak een nieuw C#-project.
2. Voeg een verwijzing toe naar de Aspose.Words voor .NET-bibliotheek.

## Stap 2: Het document maken en configureren
Om Woordenverwerking met de tabel te starten, moeten we een document maken en de documentgenerator configureren. Volg deze stappen:

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Maak het document en de documentgenerator
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar uw documentenmap.

## Stap 3: De tabel invoegen en configureren
Vervolgens voegen we een tabel in het document in met een breedte die de helft van de breedte van de pagina beslaat. Gebruik de volgende code:

```csharp
// Plaats de tabel en configureer de breedte ervan
Table table = builder. StartTable();
builder. InsertCell();
table. PreferredWidth = PreferredWidth. FromPercent(50);
builder.Writeln("Cell #1");
builder. InsertCell();
builder.Writeln("Cell #2");
builder. InsertCell();
builder.Writeln("Cell #3");
```

Hier gebruiken we de documentbouwer om de tabel te maken, cellen in te voegen en de gewenste breedte van de tabel in te stellen op 50% van de paginabreedte. Vervolgens voegen we tekst toe in elke cel.

## Stap 4: Het gewijzigde document opslaan
Ten slotte moeten we het gewijzigde document opslaan met de tabel aangepast aan de breedte van de pagina. Gebruik de volgende code:

```csharp
// Sla het gewijzigde document op
doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

Zorg ervoor dat u het juiste pad en de juiste bestandsnaam voor het uitvoerdocument opgeeft.
  
### Voorbeeldbroncode voor automatisch aanpassen aan paginabreedte met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Voeg een tabel in met een breedte die de helft van de paginabreedte beslaat.
	Table table = builder.StartTable();
	builder.InsertCell();
	table.PreferredWidth = PreferredWidth.FromPercent(50);
	builder.Writeln("Cell #1");
	builder.InsertCell();
	builder.Writeln("Cell #2");
	builder.InsertCell();
	builder.Writeln("Cell #3");
	doc.Save(dataDir + "WorkingWithTables.AutoFitToPageWidth.docx");
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u een tabel automatisch kunt aanpassen aan de paginabreedte in een Word-document met behulp van Aspose.Words voor .NET. Door deze stapsgewijze handleiding te volgen en de meegeleverde C#-code te implementeren, kunt u tabellen in uw Word-documenten programmatisch manipuleren. Met deze functie kunt u de breedte van de tabel dynamisch aanpassen aan de pagina, waardoor u een professioneel en visueel aantrekkelijk document krijgt.