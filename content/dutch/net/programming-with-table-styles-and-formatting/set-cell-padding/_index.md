---
title: Celopvulling instellen
linktitle: Celopvulling instellen
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het instellen van tabelcelmarges met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-table-styles-and-formatting/set-cell-padding/
---

In deze zelfstudie leiden we u stapsgewijs door het proces om de tabelcelmarges in te stellen met Aspose.Words voor .NET. We leggen de gebundelde C#-broncode uit en bieden u een uitgebreide handleiding om u te helpen deze functie te begrijpen en in uw eigen projecten te implementeren. Aan het einde van deze zelfstudie weet u hoe u de linker-, boven-, rechter- en ondermarges (ruimte) van de celinhoud in uw tabellen in uw Word-documenten kunt aanpassen met Aspose.Words voor .NET .

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
builder. StartTable();
builder. InsertCell();
```

## Stap 4: Stel celmarges in
 Nu kunnen we de celmarges instellen met behulp van de`SetPaddings()` werkwijze van de`CellFormat` voorwerp. Marges worden gedefinieerd in punten en gespecificeerd in de volgorde links, boven, rechts en onder.

```csharp
builder.CellFormat.SetPaddings(30, 50, 30, 50);
```

## Stap 5: Voeg inhoud toe aan de cel
 Vervolgens kunnen we inhoud aan de cel toevoegen met behulp van de documentbouwer`Writeln()` methode.

```csharp
builder.Writeln("I'm a beautifully formatted cell.");
```

## Stap 6: Maak de tabel af en sla het document op
 Ten slotte voltooien we het maken van de tabel met behulp van de`EndRow()` methode en`EndTable()`, vervolgens slaan we het gewijzigde document op in een bestand.

```csharp
builder. EndRow();
builder. EndTable();
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetCellPadding.docx");
```
 
### Voorbeeldbroncode voor Set Cell Padding met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	builder.StartTable();
	builder.InsertCell();
	// Stelt de hoeveelheid ruimte (in punten) in die moet worden toegevoegd aan de linker-/boven-/rechts-/onderkant van de celinhoud.
	builder.CellFormat.SetPaddings(30, 50, 30, 50);
	builder.Writeln("I'm a wonderful formatted cell.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.SetCellPadding.docx");
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u de marges van een tabelcel kunt instellen met Aspose.Words voor .NET. Door deze stapsgewijze handleiding te volgen, kunt u eenvoudig de celmarges aanpassen om spaties links, boven, rechts en onderaan de inhoud in uw tabellen in uw Word-documenten te creëren. Aspose.Words biedt een krachtige en flexibele API voor het manipuleren en opmaken van tabellen in uw documenten. Met deze kennis kunt u de opmaak van uw tabellen aanpassen aan uw specifieke behoeften.