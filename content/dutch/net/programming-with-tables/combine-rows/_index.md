---
title: Combineer rijen
linktitle: Combineer rijen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u tabelrijen in een Word-document combineert met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-tables/combine-rows/
---

In deze zelfstudie leren we hoe u Aspose.Words voor .NET kunt gebruiken om rijen met tabellen in een Word-document te combineren. We zullen een stapsgewijze handleiding volgen om de code te begrijpen en deze functie te implementeren. Aan het einde van deze zelfstudie kunt u tabelrijen in uw Word-documenten programmatisch manipuleren en samenvoegen.

## Stap 1: Projectconfiguratie
1. Start Visual Studio en maak een nieuw C#-project.
2. Voeg een verwijzing toe naar de Aspose.Words voor .NET-bibliotheek.

## Stap 2: Het document laden en toegang krijgen tot de tabellen
Om Woordenverwerking met tabellen te starten, moeten we het document laden dat deze bevat en deze openen. Volg deze stappen:

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laad het document
Document doc = new Document(dataDir + "Tables.docx");

// Toegang tot tafels
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);
Table secondTable = (Table)doc.GetChild(NodeType.Table, 1, true);
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar uw documentenmap.

## Stap 3: Tabelrijen combineren
Vervolgens combineren we de rijen van de tweede tabel tot het einde van de eerste tabel. Gebruik de volgende code:

```csharp
// Combinatie van tabelrijen
while (secondTable.HasChildNodes)
     firstTable.Rows.Add(secondTable.FirstRow);
secondTable.Remove();
```

 Hier gebruiken we een`while` lus om alle rijen van de tweede array te herhalen en ze toe te voegen aan het einde van de eerste array met behulp van de`Add` methode. Vervolgens verwijderen we de tweede tabel uit het document met behulp van de`Remove` methode.

## Stap 4: Het gewijzigde document opslaan
Ten slotte moeten we het gewijzigde document opslaan met de gecombineerde tabelrijen. Gebruik de volgende code:

```csharp
// Sla het gewijzigde document op
doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

Zorg ervoor dat u het juiste pad en de juiste bestandsnaam voor het uitvoerdocument opgeeft.

### Voorbeeldbroncode voor Combine Rows met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// De rijen uit de tweede tabel worden aan het einde van de eerste tabel toegevoegd.
	Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
	Table secondTable = (Table) doc.GetChild(NodeType.Table, 1, true);
	// Voeg alle rijen uit de huidige tabel toe aan de volgende tabellen
	// met verschillende celaantallen en breedtes kunnen worden samengevoegd tot één tabel.
	while (secondTable.HasChildNodes)
		firstTable.Rows.Add(secondTable.FirstRow);
	secondTable.Remove();
	doc.Save(dataDir + "WorkingWithTables.CombineRows.docx");
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u rijen met tabellen in een Word-document kunt combineren met Aspose.Words voor .NET. Door deze stapsgewijze handleiding te volgen en de meegeleverde C#-code te implementeren, kunt u tabelrijen in uw Word-documenten programmatisch manipuleren. Met deze functie kunt u uw gegevens efficiënt samenvoegen en in een tabel ordenen.