---
title: Bouw een tafel met stijl
linktitle: Bouw een tafel met stijl
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het bouwen van een tabel met een aangepaste stijl met behulp van Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-table-styles-and-formatting/build-table-with-style/
---

In deze zelfstudie begeleiden we u stapsgewijs door het proces voor het bouwen van een opgemaakte tabel met Aspose.Words voor .NET. We leggen de gebundelde C#-broncode uit en bieden u een uitgebreide handleiding om u te helpen deze functie te begrijpen en in uw eigen projecten te implementeren. Aan het einde van deze zelfstudie weet u hoe u een tabel met een aangepaste stijl in uw Word-documenten kunt maken met behulp van Aspose.Words voor .NET.

## Stap 1: Definieer de documentmap
Eerst moet u het pad naar uw documentenmap instellen. Dit is de locatie waar u uw bewerkte Word-document wilt opslaan. Vervang "UW DOCUMENTENDIRECTORY" door het juiste pad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Maak een nieuw document en een documentbuilder
 Vervolgens moet u een nieuw exemplaar van de`Document` klasse en een documentconstructor voor dat document.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 3: Start een nieuwe tabel en voeg een cel in
 Om te beginnen met het bouwen van de tafel, gebruiken we de`StartTable()` methode van de documentbouwer, vervolgens voegen we een cel in de tabel in met behulp van de`InsertCell()` methode.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## Stap 4: Definieer de stijl van de tabel
 Nu kunnen we de tabelstijl instellen met behulp van de`StyleIdentifier` eigendom. In dit voorbeeld gebruiken we de stijl "MediumShading1Accent1".

```csharp
table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
```

## Stap 5: Pas stijlopties toe op de tabel
 We kunnen specificeren welke kenmerken moeten worden opgemaakt door de stijl met behulp van de`StyleOptions`eigenschap van de array. In dit voorbeeld passen we de volgende opties toe: "FirstColumn", "RowBands" en "FirstRow".

```csharp
table.StyleOptions = TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
```

## Stap 6: Pas de tafelgrootte automatisch aan
 Om de grootte van de array automatisch aan te passen op basis van de inhoud, gebruiken we de`AutoFit()` methode met de`AutoFitBehavior.AutoFitToContents` gedrag.

```csharp
table. AutoFit(AutoFitBehavior.AutoFitToContents);
```

## Stap 7: Voeg inhoud toe aan cellen
 Nu kunnen we inhoud aan cellen toevoegen met behulp van de`Writeln()`En`InsertCell()` methoden van de documentbouwer. In dit voorbeeld voegen we de kopteksten toe voor 'Artikel' en 'Aantal (

kg)" en de bijbehorende gegevens.

```csharp
builder.Writeln("Item");
builder.CellFormat.RightPadding = 40;
builder. InsertCell();
builder. Writen("Quantity (kg)");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Apples");
builder. InsertCell();
builder.Writeln("20");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Bananas");
builder. InsertCell();
builder. Writen("40");
builder. EndRow();
builder. InsertCell();
builder.Writeln("Carrots");
builder. InsertCell();
builder.Writeln("50");
builder. EndRow();
```

## Stap 8: Sla het gewijzigde document op
Ten slotte slaan we het gewijzigde document op in een bestand. U kunt een geschikte naam en locatie voor het uitvoerdocument kiezen.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

Gefeliciteerd! U hebt nu een op maat gemaakte tabel gebouwd met Aspose.Words voor .NET.

### Voorbeeldbroncode voor Build Table With Style met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	// We moeten eerst minimaal één rij invoegen voordat we de tabelopmaak instellen.
	builder.InsertCell();
	// Stel de gebruikte tabelstijl in op basis van de unieke stijl-ID.
	table.StyleIdentifier = StyleIdentifier.MediumShading1Accent1;
	// Pas toe welke functies moeten worden opgemaakt door de stijl.
	table.StyleOptions =
		TableStyleOptions.FirstColumn | TableStyleOptions.RowBands | TableStyleOptions.FirstRow;
	table.AutoFit(AutoFitBehavior.AutoFitToContents);
	builder.Writeln("Item");
	builder.CellFormat.RightPadding = 40;
	builder.InsertCell();
	builder.Writeln("Quantity (kg)");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Apples");
	builder.InsertCell();
	builder.Writeln("20");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Bananas");
	builder.InsertCell();
	builder.Writeln("40");
	builder.EndRow();
	builder.InsertCell();
	builder.Writeln("Carrots");
	builder.InsertCell();
	builder.Writeln("50");
	builder.EndRow();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.BuildTableWithStyle.docx");
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u een opgemaakte tabel kunt bouwen met Aspose.Words voor .NET. Door deze stapsgewijze handleiding te volgen, kunt u eenvoudig de stijl van uw tabellen in uw Word-documenten aanpassen. Aspose.Words biedt een krachtige en flexibele API voor het manipuleren en opmaken van tabellen in uw documenten. Met deze kennis kunt u de visuele presentatie van uw Word-documenten verbeteren en aan specifieke behoeften voldoen.