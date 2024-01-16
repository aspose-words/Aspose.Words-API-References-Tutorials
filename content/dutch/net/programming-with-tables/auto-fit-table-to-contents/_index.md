---
title: Tabel automatisch aanpassen aan inhoud
linktitle: Tabel automatisch aanpassen aan inhoud
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een tabel automatisch aan de inhoud ervan in een Word-document kunt aanpassen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-tables/auto-fit-table-to-contents/
---

In deze zelfstudie leren we hoe u Aspose.Words voor .NET kunt gebruiken om een tabel automatisch aan te passen aan de inhoud in een Word-document met behulp van C#. We zullen het stapsgewijze proces van het schrijven van code doorlopen om deze functionaliteit te bereiken. Aan het einde van deze zelfstudie heeft u een duidelijk inzicht in hoe u tabellen in Word-documenten programmatisch kunt manipuleren.

## Stap 1: Zet het project op
1. Start Visual Studio en maak een nieuw C#-project.
2. Voeg een verwijzing toe naar de Aspose.Words voor .NET-bibliotheek.

## Stap 2: Laad het Word-document
Om de woordenverwerking met de tabel te starten, moeten we het Word-document laden dat de tabel bevat. Volg deze stappen:

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Laad het Word-document
Document doc = new Document(dataDir + "Tables.docx");
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar uw document.

## Stap 3: Open de tabel en pas deze automatisch aan de inhoud aan
Vervolgens moeten we toegang krijgen tot de tabel in het document en het gedrag voor automatisch aanpassen toepassen. Gebruik de volgende code:

```csharp
// Toegang tot de tabel
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);

// Pas de tabel automatisch aan de inhoud aan
table. AutoFit(AutoFitBehavior.AutoFitToContents);
```

 Hier casten we het eerste onderliggende knooppunt van het type`Table` uit het document en gebruik vervolgens de`AutoFit` methode met de`AutoFitToContents` gedrag om de tabelbreedte aan te passen aan de inhoud ervan.

## Stap 4: Sla het gewijzigde document op
Ten slotte moeten we het gewijzigde document opslaan met de automatisch aangepaste tabel. Gebruik de volgende code:

```csharp
// Sla het gewijzigde document op
doc.Save(dataDir + "WorkingWithTables.AutoFitTableToContents.docx");
```

Zorg ervoor dat u het juiste pad en de juiste bestandsnaam voor het uitvoerdocument opgeeft.

### Voorbeeldbroncode voor het automatisch aanpassen van tabel aan inhoud met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	table.AutoFit(AutoFitBehavior.AutoFitToContents);
	doc.Save(dataDir + "WorkingWithTables.AutoFitTableToContents.docx");
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u een tabel automatisch aan de inhoud ervan in een Word-document kunt aanpassen met behulp van Aspose.Words voor .NET. Door de stapsgewijze handleiding te volgen en de meegeleverde C#-code te implementeren, kunt u tabellen in uw Word-documenten programmatisch manipuleren. Hierdoor kunt u de tabelbreedte dynamisch aanpassen op basis van de inhoud, waardoor een professioneler en visueel aantrekkelijker document ontstaat.