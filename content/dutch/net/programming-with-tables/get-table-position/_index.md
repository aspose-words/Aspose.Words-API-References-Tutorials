---
title: Verkrijg tafelpositie
linktitle: Verkrijg tafelpositie
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de positie van een tabel in een Word-document kunt achterhalen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-tables/get-table-position/
---

In deze tutorial gaan we leren hoe we de positie van een tabel in een Word-document kunnen achterhalen met behulp van Aspose.Words voor .NET. We zullen een stapsgewijze handleiding volgen om de code te begrijpen en deze functie te implementeren. Aan het einde van deze zelfstudie kunt u programmatisch tabelpositioneringseigenschappen in uw Word-documenten verkrijgen.

## Stap 1: Projectconfiguratie
1. Start Visual Studio en maak een nieuw C#-project.
2. Voeg een verwijzing toe naar de Aspose.Words voor .NET-bibliotheek.

## Stap 2: Het document laden en toegang krijgen tot de tabel
Om Woordenverwerking met de tabel te starten, moeten we het document laden dat de tabel bevat en er toegang toe hebben. Volg deze stappen:

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laad het document
Document doc = new Document(dataDir + "Tables.docx");

// Toegang tot de array
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar uw documentenmap. Zorg er ook voor dat het document de tabel bevat waarvan u de positie wilt verkrijgen.

## Stap 3: Eigenschappen voor arraypositionering ophalen
Vervolgens controleren we het positioneringstype van de array en verkrijgen we de juiste positioneringseigenschappen. Gebruik de volgende code:

```csharp
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.RelativeHorizontalAlignment);
Console.WriteLine(table.RelativeVerticalAlignment);
}
else
{
Console.WriteLine(table.Alignment);
}
```

 Hier gebruiken we een voorwaarde om te controleren of de array van het float-type is. Als dat zo is, printen wij de`RelativeHorizontalAlignment`En`RelativeVerticalAlignment` eigenschappen om de relatieve horizontale en verticale uitlijning van de tabel te verkrijgen. Anders printen wij de`Alignment` eigenschap om de array-uitlijning te verkrijgen.

### Voorbeeldbroncode voor Get Table Position met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	if (table.TextWrapping == TextWrapping.Around)
	{
		Console.WriteLine(table.RelativeHorizontalAlignment);
		Console.WriteLine(table.RelativeVerticalAlignment);
	}
	else
	{
		Console.WriteLine(table.Alignment);
	}
```

## Conclusie
In deze tutorial hebben we geleerd hoe we de positie van een tabel in een Word-document kunnen achterhalen met Aspose.Words voor .NET. Door deze stapsgewijze handleiding te volgen en de meegeleverde C#-code te implementeren, kunt u programmatisch tabelpositioneringseigenschappen in uw Word-documenten verkrijgen. Met deze functie kunt u arrays analyseren en manipuleren op basis van hun specifieke posities.