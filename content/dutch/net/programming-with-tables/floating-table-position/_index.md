---
title: Zwevende tafelpositie
linktitle: Zwevende tafelpositie
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een tabel in een zwevende positie in een Word-document plaatst met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-tables/floating-table-position/
---

In deze zelfstudie gaan we leren hoe u Aspose.Words voor .NET kunt gebruiken om een tabel in een zwevende positie in een Word-document te plaatsen. We zullen een stapsgewijze handleiding volgen om de code te begrijpen en deze functie te implementeren. Aan het einde van deze zelfstudie kunt u de positie en uitlijning van zwevende tabellen in uw Word-documenten programmatisch beheren.

## Stap 1: Projectconfiguratie
1. Start Visual Studio en maak een nieuw C#-project.
2. Voeg een verwijzing toe naar de Aspose.Words voor .NET-bibliotheek.

## Stap 2: Het document laden en toegang krijgen tot de tabel
Om Woordenverwerking met de tabel te starten, moeten we het document laden dat de tabel bevat en er toegang toe hebben. Volg deze stappen:

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laad het document
Document doc = new Document(dataDir + "Table wrapped by text.docx");

// Toegang tot de array
Table table = doc.FirstSection.Body.Tables[0];
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar uw documentenmap. Zorg er ook voor dat het document een tabel bevat die in een zwevende positie wordt geplaatst.

## Stap 3: Het zwevende bord positioneren
Vervolgens plaatsen we de tabel in een zwevende positie met behulp van de eigenschappen van Aspose.Words voor .NET. Gebruik de volgende code:

```csharp
// Positionering van de zwevende tafel
table. AbsoluteHorizontalDistance = 10;
table. RelativeVerticalAlignment = VerticalAlignment. Center;
```

 Hier gebruiken wij de`AbsoluteHorizontalDistance` eigenschap om de absolute horizontale afstand van de tabel vanaf de linkerrand van de pagina in te stellen. Wij gebruiken ook de`RelativeVerticalAlignment` eigenschap om de relatieve verticale uitlijning van de tabel ten opzichte van de omringende inhoud in te stellen.

## Stap 4: Het gewijzigde document opslaan
Ten slotte moeten we het gewijzigde document opslaan met de tabel in een zwevende positie. Gebruik de volgende code:

```csharp
// Sla het gewijzigde document op
doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

Zorg ervoor dat u het juiste pad en de juiste bestandsnaam voor het uitvoerdocument opgeeft.

### Voorbeeldbroncode voor zwevende tabelpositie met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	Table table = doc.FirstSection.Body.Tables[0];
	table.AbsoluteHorizontalDistance = 10;
	table.RelativeVerticalAlignment = VerticalAlignment.Center;
	doc.Save(dataDir + "WorkingWithTables.FloatingTablePosition.docx");
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u een tabel in een zwevende positie in een Word-document kunt plaatsen met behulp van Aspose.Words voor .NET. Door deze stapsgewijze handleiding te volgen en de meegeleverde C#-code te implementeren, kunt u de positie en uitlijning van zwevende tabellen in uw Word-documenten programmatisch beheren.