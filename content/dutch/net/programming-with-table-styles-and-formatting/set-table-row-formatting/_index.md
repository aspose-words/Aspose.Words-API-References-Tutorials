---
title: Stel de opmaak van de tabelrijen in
linktitle: Stel de opmaak van de tabelrijen in
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het instellen van de opmaak van tabelrijen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-table-styles-and-formatting/set-table-row-formatting/
---

In deze zelfstudie leiden we u stapsgewijs door het proces om de opmaak van tabelrijen in te stellen met Aspose.Words voor .NET. We leggen de gebundelde C#-broncode uit en bieden u een uitgebreide handleiding om u te helpen deze functie te begrijpen en in uw eigen projecten te implementeren. Aan het einde van deze tutorial weet u hoe u de hoogte en opvulling van een tabelrij in uw Word-documenten kunt aanpassen met Aspose.Words voor .NET.

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

## Stap 3: Start een nieuwe tabel en voeg een cel toe
Om te beginnen met het maken van de tabel, gebruiken we de`StartTable()` methode van de documentconstructor, vervolgens voegen we een cel aan de tabel toe met behulp van de`InsertCell()` methode.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
```

## Stap 4: Definieer de lijnopmaak
 Nu kunnen we de rijopmaak instellen door naar het`RowFormat` voorwerp van de`DocumentBuilder` voorwerp. Met de bijbehorende eigenschappen kunnen we de lijnhoogte en de marges (paddings) instellen.

```csharp
RowFormat rowFormat = builder.RowFormat;
rowFormat. Height = 100;
rowFormat.HeightRule = HeightRule.Exactly;
```

## Stap 5: Stel de tabelmarges in
 Vervolgens kunnen we de tabelopvullingen instellen door toegang te krijgen tot de overeenkomstige eigenschappen van de`Table` voorwerp. Deze marges worden toegepast op alle rijen van de tabel.

```csharp
table. LeftPadding = 30;
table. RightPadding = 30;
table. TopPadding = 30;
table. BottomPadding = 30;
```

## Stap 6: Voeg inhoud toe aan de rij
 Ten slotte kunnen we inhoud aan de regel toevoegen met behulp van de documentbuilder`Writeln()` methode.

```csharp
builder.Writeln("I'm a beautifully formatted line.");
```

## Stap 7: Maak de tabel af en sla het document op
In

 Uiteindelijk voltooien we het maken van de tabel met behulp van de`EndRow()` En`EndTable()` methode, dan slaan we het gewijzigde document op in een bestand.

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

### Voorbeeldbroncode voor Set Table Row Formatting met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	RowFormat rowFormat = builder.RowFormat;
	rowFormat.Height = 100;
	rowFormat.HeightRule = HeightRule.Exactly;
	// Deze opmaakeigenschappen worden ingesteld op de tabel en worden toegepast op alle rijen in de tabel.
	table.LeftPadding = 30;
	table.RightPadding = 30;
	table.TopPadding = 30;
	table.BottomPadding = 30;
	builder.Writeln("I'm a wonderful formatted row.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.DocumentBuilderSetTableRowFormatting.docx");
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u de opmaak van tabelrijen kunt instellen met Aspose.Words voor .NET. Door deze stapsgewijze handleiding te volgen, kunt u eenvoudig de hoogte en marges van tabelrijen in uw Word-documenten aanpassen. Aspose.Words biedt een krachtige en flexibele API voor het manipuleren en opmaken van tabellen in uw documenten. Met deze kennis kunt u de visuele indeling van uw tafels aanpassen aan uw specifieke behoeften.