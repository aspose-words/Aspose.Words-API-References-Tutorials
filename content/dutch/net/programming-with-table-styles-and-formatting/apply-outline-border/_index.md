---
title: Omtrekrand toepassen
linktitle: Omtrekrand toepassen
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het toepassen van een omtrekrand op een tabel met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-table-styles-and-formatting/apply-outline-border/
---

In deze zelfstudie leiden we u stapsgewijs door het proces om een omtrekrand op een tabel toe te passen met behulp van Aspose.Words voor .NET. We leggen de gebundelde C#-broncode uit en bieden u een uitgebreide handleiding om u te helpen deze functie te begrijpen en in uw eigen projecten te implementeren. Aan het einde van deze tutorial heeft u een duidelijk inzicht in hoe u tabelranden in uw Word-documenten kunt manipuleren met Aspose.Words voor .NET.

## Stap 1: Definieer de documentmap
Eerst moet u het pad naar uw documentenmap instellen. Dit is waar uw Word-document wordt opgeslagen. Vervang "UW DOCUMENTENDIRECTORY" door het juiste pad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Upload het document
 Vervolgens moet u het Word-document in een exemplaar van het`Document` klas.

```csharp
Document doc = new Document(dataDir + "Tables.docx");
```

## Stap 3: Ga naar de tabel
 Om een omtrekrand toe te passen, hebben we toegang tot de tabel in het document nodig. De`Table` klasse vertegenwoordigt een tabel in Aspose.Words.

```csharp
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

## Stap 4: Lijn de tabel uit met het midden van de pagina
 Nu kunnen we de tabel uitlijnen op het midden van de pagina met behulp van de`Alignment` eigendom van de tafel.

```csharp
table. Alignment = Table Alignment. Center;
```

## Stap 5: Wis bestaande tabelranden
Om met een nieuwe omtrekrand te beginnen, moeten we eerst alle bestaande randen uit de tabel wissen. Dit kan gedaan worden met behulp van de`ClearBorders()` methode.

```csharp
table. ClearBorders();
```

## Stap 6: Definieer een groene rand rond de tafel
 We kunnen nu een groene rand rond de tafel plaatsen met behulp van de`SetBorder()` methode voor elke kant van de tafel. In dit voorbeeld gebruiken we een rand van het type "Enkel" met een dikte van 1,5 punten en een groene kleur.

```csharp
table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
```

## Stap 7: Vul de cellen met een achtergrondkleur
Om de visuele presentatie van de tabel te verbeteren, kunnen we de cellen vullen met een grondachtergrondkleur

idee. In dit voorbeeld gebruiken we een lichtgroene kleur.

```csharp
table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
```

## Stap 8: Sla het gewijzigde document op
Ten slotte slaan we het gewijzigde document op in een bestand. U kunt een geschikte naam en locatie voor het uitvoerdocument kiezen.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

Gefeliciteerd! U hebt nu een omtrekrand op een tabel toegepast met behulp van Aspose.Words voor .NET.

### Voorbeeldbroncode voor Apply Outline Border met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Lijn de tabel uit met het midden van de pagina.
	table.Alignment = TableAlignment.Center;
	//Verwijder eventuele bestaande randen uit de tabel.
	table.ClearBorders();
	// Plaats een groene rand rond de tafel, maar niet binnenin.
	table.SetBorder(BorderType.Left, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Right, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Top, LineStyle.Single, 1.5, Color.Green, true);
	table.SetBorder(BorderType.Bottom, LineStyle.Single, 1.5, Color.Green, true);
	// Vul de cellen met een lichtgroene effen kleur.
	table.SetShading(TextureIndex.TextureSolid, Color.LightGreen, Color.Empty);
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.ApplyOutlineBorder.docx");
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u een omtrekrand op een tabel kunt toepassen met behulp van Aspose.Words voor .NET. Door deze stapsgewijze handleiding te volgen, kunt u deze functionaliteit eenvoudig integreren in uw C#-projecten. Het manipuleren van tabelopmaak is een essentieel aspect van documentverwerking, en Aspose.Words biedt een krachtige en flexibele API om dit te bereiken. Met deze kennis kunt u de visuele presentatie van uw Word-documenten verbeteren en aan specifieke eisen voldoen.