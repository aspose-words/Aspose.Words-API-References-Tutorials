---
title: Bouw een tafel met randen
linktitle: Bouw een tafel met randen
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het bouwen van een tabel met randen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-table-styles-and-formatting/build-table-with-borders/
---

In deze zelfstudie leiden we u stapsgewijs door het proces om een tabel met randen te bouwen met behulp van Aspose.Words voor .NET. We leggen de gebundelde C#-broncode uit en bieden u een uitgebreide handleiding om u te helpen deze functie te begrijpen en in uw eigen projecten te implementeren. Aan het einde van deze zelfstudie weet u hoe u een tabel met aangepaste randen in uw Word-documenten kunt maken met behulp van Aspose.Words voor .NET.

## Stap 1: Definieer de documentmap
Eerst moet u het pad naar uw documentenmap instellen. Dit is waar uw Word-document wordt opgeslagen. Vervang "UW DOCUMENTENDIRECTORY" door het juiste pad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Bestaand document laden
 Vervolgens moet u het bestaande Word-document in een exemplaar van het`Document` klas.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Stap 3: Ga naar de tabel en verwijder bestaande randen
 Om te beginnen met het bouwen van de tabel met randen, moeten we naar de tabel in het document navigeren en de bestaande randen verwijderen. De`ClearBorders()` methode verwijdert alle randen uit de tabel.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
table. ClearBorders();
```

## Stap 4: stel de tabelranden in
 Nu kunnen we de tabelranden instellen met behulp van de`SetBorders()` methode. In dit voorbeeld gebruiken we een groen gekleurde rand met een dikte van 1,5 punt.

```csharp
table.SetBorders(LineStyle.Single, 1.5, Color.Green);
```

## Stap 5: Sla het gewijzigde document op
Ten slotte slaan we het gewijzigde document op in een bestand. U kunt een geschikte naam en locatie voor het uitvoerdocument kiezen.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithBorders.docx");
```

Gefeliciteerd! U hebt nu een tabel met aangepaste randen gebouwd met Aspose.Words voor .NET.

### Voorbeeldbroncode voor Build Table With Borders met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	//Verwijder eventuele bestaande randen uit de tabel.
	table.ClearBorders();
	// Plaats een groene rand rond en binnen de tafel.
	table.SetBorders(LineStyle.Single, 1.5, Color.Green);
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithBorders.docx");
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u een tabel met randen kunt bouwen met Aspose.Words voor .NET. Door deze stapsgewijze handleiding te volgen, kunt u eenvoudig uw tabelranden in uw Word-documenten aanpassen. Aspose.Words biedt een krachtige en flexibele API voor het manipuleren en opmaken van tabellen in uw documenten. Met deze kennis kunt u de visuele presentatie van uw Word-documenten verbeteren en aan specifieke behoeften voldoen.