---
title: Krijg de afstand tussen de omringende tekst van de tabel
linktitle: Krijg de afstand tussen de omringende tekst van de tabel
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding om de afstand tussen tekst en een tabel in een Word-document te bepalen met behulp van Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-table-styles-and-formatting/get-distance-between-table-surrounding-text/
---

In deze zelfstudie leiden we u stapsgewijs door het proces om de afstand tussen omringende tekst in een tabel te bepalen met behulp van Aspose.Words voor .NET. We leggen de gebundelde C#-broncode uit en bieden u een uitgebreide handleiding om u te helpen deze functie te begrijpen en in uw eigen projecten te implementeren. Aan het einde van deze tutorial weet u hoe u toegang krijgt tot de verschillende afstanden tussen een tabel en de omringende tekst in uw Word-documenten met behulp van Aspose.Words voor .NET.

## Stap 1: Definieer de documentmap
Eerst moet u het pad naar uw documentenmap instellen. Dit is waar uw Word-document zich bevindt. Vervang "UW DOCUMENTENMAP" door het juiste pad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Bestaand document laden
 Vervolgens moet u het bestaande Word-document in een exemplaar van het`Document` klas.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Stap 3: Bereken de afstand tussen de tabel en de omringende tekst
 Om de afstand tussen de tabel en de omringende tekst te bepalen, moeten we de tabel in het document openen met behulp van de`GetChild()` methode en de`NodeType.Table` eigendom. We kunnen vervolgens de verschillende afstanden weergeven met behulp van de array-eigenschappen`DistanceTop`, `DistanceBottom`, `DistanceRight` En`DistanceLeft`.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Console.WriteLine("Distance between table and top text: " + table.DistanceTop);
Console.WriteLine("Distance between table and bottom text: " + table.DistanceBottom);
Console.WriteLine("Distance between the table and the text on the right: " + table.DistanceRight);
Console.WriteLine("Distance between the table and the text on the left: " + table.DistanceLeft);
```

### Voorbeeldbroncode voor het verkrijgen van afstand tussen omringende tekst met behulp van Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Console.WriteLine("\nGet distance between table left, right, bottom, top and the surrounding text.");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Console.WriteLine(table.DistanceTop);
	Console.WriteLine(table.DistanceBottom);
	Console.WriteLine(table.DistanceRight);
	Console.WriteLine(table.DistanceLeft);
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe we de afstand tussen omringende tekst in een tabel kunnen bepalen met behulp van Aspose.Words voor .NET. Door dit stappenplan te volgen, krijgt u eenvoudig toegang tot de verschillende afstanden tussen een tabel en de omringende tekst in uw Word-documenten. Aspose.Words biedt een krachtige en flexibele API voor het manipuleren en opmaken van tabellen in uw documenten. Met deze kennis kunt u de indeling van uw tabellen in relatie tot de tekst analyseren en aan specifieke behoeften voldoen.