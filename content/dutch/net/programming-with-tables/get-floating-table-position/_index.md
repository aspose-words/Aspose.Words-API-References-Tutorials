---
title: Verkrijg zwevende tafelpositie
linktitle: Verkrijg zwevende tafelpositie
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de positie van zwevende tabellen in een Word-document kunt achterhalen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-tables/get-floating-table-position/
---

In deze zelfstudie leren we hoe u de positie van een zwevende tabel in een Word-document kunt achterhalen met behulp van Aspose.Words voor .NET. We zullen een stapsgewijze handleiding volgen om de code te begrijpen en deze functie te implementeren. Aan het einde van deze zelfstudie kunt u programmatisch de positioneringseigenschappen van een zwevende tabel in uw Word-documenten verkrijgen.

## Stap 1: Projectconfiguratie
1. Start Visual Studio en maak een nieuw C#-project.
2. Voeg een verwijzing toe naar de Aspose.Words voor .NET-bibliotheek.

## Stap 2: Het document laden en toegang krijgen tot de tabellen
Om Woordenverwerking met tabellen te starten, moeten we het document laden dat deze bevat en deze openen. Volg deze stappen:

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laad het document
Document doc = new Document(dataDir + "Table wrapped by text.docx");
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar uw documentenmap. Zorg er ook voor dat het document zwevende tabellen bevat.

## Stap 3: Eigenschappen voor plaatsing van zwevende tabellen verkrijgen
Vervolgens doorlopen we alle tabellen in het document en verkrijgen we de positioneringseigenschappen van de zwevende tabel. Gebruik de volgende code:

```csharp
foreach(Table table in doc.FirstSection.Body.Tables)
{
// Als de array een zwevend type is, drukt u de positioneringseigenschappen ervan af.
if (table.TextWrapping == TextWrapping.Around)
{
Console.WriteLine(table.HorizontalAnchor);
Console.WriteLine(table.VerticalAnchor);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.AbsoluteVerticalDistance);
Console.WriteLine(table.AllowOverlap);
Console.WriteLine(table.AbsoluteHorizontalDistance);
Console.WriteLine(table.RelativeVerticalAlignment);
Console.WriteLine("...............................");
}
}
```

 Hier gebruiken we een`foreach` lus om alle arrays in het document te doorlopen. We controleren of de array van het float-type is door de`TextWrapping` eigendom. Als dat zo is, drukken we de positioneringseigenschappen van de tabel af, zoals horizontaal anker, verticaal anker, absolute horizontale en verticale afstanden, overlappende toestemming, absolute horizontale afstand en relatieve verticale uitlijning.
 
### Voorbeeldbroncode voor Get Floating Table Position met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table wrapped by text.docx");
	foreach (Table table in doc.FirstSection.Body.Tables)
	{
		// Als de tabel een zwevend type is, drukt u de positioneringseigenschappen ervan af.
		if (table.TextWrapping == TextWrapping.Around)
		{
			Console.WriteLine(table.HorizontalAnchor);
			Console.WriteLine(table.VerticalAnchor);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.AbsoluteVerticalDistance);
			Console.WriteLine(table.AllowOverlap);
			Console.WriteLine(table.AbsoluteHorizontalDistance);
			Console.WriteLine(table.RelativeVerticalAlignment);
			Console.WriteLine("..............................");
		}
	}
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe we de positie van een zwevende tabel in een Word-document kunnen achterhalen met behulp van Aspose.Words voor .NET. Door deze stapsgewijze handleiding te volgen en de meegeleverde C#-code te implementeren, kunt u de positioneringseigenschappen van zwevende tabellen in uw Word-documenten programmatisch verkrijgen. Met deze functie kunt u zwevende tabellen analyseren en manipuleren volgens uw specifieke behoeften.