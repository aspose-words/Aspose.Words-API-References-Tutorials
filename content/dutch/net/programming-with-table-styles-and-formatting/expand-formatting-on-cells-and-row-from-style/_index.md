---
title: Vouw de opmaak van cellen en rij uit stijl uit
linktitle: Vouw de opmaak van cellen en rij uit stijl uit
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding om de opmaak uit te breiden naar cellen en rijen vanuit een tabelstijl met behulp van Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-table-styles-and-formatting/expand-formatting-on-cells-and-row-from-style/
---

In deze zelfstudie leiden we u stapsgewijs door het proces om de opmaak uit te breiden naar cellen en rijen vanuit een stijl met behulp van Aspose.Words voor .NET. We leggen de gebundelde C#-broncode uit en bieden u een uitgebreide handleiding om u te helpen deze functie te begrijpen en in uw eigen projecten te implementeren. Aan het einde van deze zelfstudie weet u hoe u de opmaak van tabelstijlen kunt toepassen op specifieke cellen en rijen in uw Word-documenten met behulp van Aspose.Words voor .NET.


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

## Stap 3: Ga naar de eerste cel van de eerste tabel
 Om te beginnen moeten we naar de eerste cel van de eerste tabel in het document navigeren. Wij gebruiken de`GetChild()` En`FirstRow.FirstCell` methoden om de verwijzing naar de eerste cel te verkrijgen.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
Cell firstCell = table.FirstRow.FirstCell;
```

## Stap 4: Toon initiële celopmaak
Voordat we de stijlen van de tabel uitvouwen, geven we de huidige achtergrondkleur van de cel weer. Dit moet leeg zijn omdat de huidige opmaak wordt opgeslagen in de stijl van de tabel.

```csharp
Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("Shading cell before style expansion: " + cellShadingBefore);
```

## Stap 5: Vouw Tabelstijlen uit naar Directe opmaak
 Nu breiden we de tabelstijlen uit naar directe opmaak met behulp van die van het document`ExpandTableStylesToDirectFormatting()` methode.

```csharp
doc.ExpandTableStylesToDirectFormatting();
```

## Stap 6: Toon celopmaak na stijluitbreiding
Nu geven we de achtergrondkleur van de cel weer na het uitvouwen van de tabelstijlen. Er moet een blauwe achtergrondkleur worden toegepast vanuit de tabelstijl.

```csharp
Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
Console.WriteLine("

Shading the cell after style expansion: " + cellShadingAfter);
```

### Voorbeeldbroncode voor het uitbreiden van de opmaak van cellen en rijen vanuit stijl met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	// Haal de eerste cel van de eerste tabel in het document op.
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	Cell firstCell = table.FirstRow.FirstCell;
	// Druk eerst de kleur van de celarcering af.
	// Dit moet leeg zijn omdat de huidige arcering in de tabelstijl wordt opgeslagen.
	Color cellShadingBefore = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading before style expansion: " + cellShadingBefore);
	doc.ExpandTableStylesToDirectFormatting();
	// Druk nu de celarcering af na het uitvouwen van de tabelstijlen.
	// Er had een blauwe achtergrondpatroonkleur moeten worden toegepast vanuit de tabelstijl.
	Color cellShadingAfter = firstCell.CellFormat.Shading.BackgroundPatternColor;
	Console.WriteLine("Cell shading after style expansion: " + cellShadingAfter);
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u de opmaak kunt uitbreiden naar cellen en rijen vanuit een tabelstijl met behulp van Aspose.Words voor .NET. Door deze stapsgewijze handleiding te volgen, kunt u eenvoudig de opmaak van tabelstijlen toepassen op specifieke cellen en rijen in uw Word-documenten. Aspose.Words biedt een krachtige en flexibele API voor het manipuleren en opmaken van tabellen in uw documenten. Met deze kennis kunt u de lay-out en presentatie van uw Word-documenten verder aanpassen.