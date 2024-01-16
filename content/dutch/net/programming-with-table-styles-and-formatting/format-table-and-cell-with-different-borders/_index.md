---
title: Formatteer tabel en cel met verschillende randen
linktitle: Formatteer tabel en cel met verschillende randen
second_title: Aspose.Words-API voor documentverwerking
description: Stapsgewijze handleiding voor het opmaken van tabellen en cellen met verschillende randen met behulp van Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-table-styles-and-formatting/format-table-and-cell-with-different-borders/
---

In deze zelfstudie leiden we u stapsgewijs door het proces voor het opmaken van een tabel en een cel met verschillende randen met behulp van Aspose.Words voor .NET. We leggen de gebundelde C#-broncode uit en bieden u een uitgebreide handleiding om u te helpen deze functie te begrijpen en in uw eigen projecten te implementeren. Aan het einde van deze zelfstudie weet u hoe u aangepaste randen kunt toepassen op specifieke tabellen en cellen in uw Word-documenten met behulp van Aspose.Words voor .NET.

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

## Stap 3: Start een nieuwe tabel en voeg cellen toe
Om te beginnen met het maken van de tabel, gebruiken we de`StartTable()` methode van de documentbouwer, vervolgens voegen we cellen aan de tabel toe met behulp van de`InsertCell()` methode en we schrijven de inhoud van de cellen naar de met behulp van de`Writeln()` methode.

```csharp
Table table = builder. StartTable();
builder. InsertCell();
// Stel randen in voor de hele tafel.
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
// Stel de opvulling voor deze cel in.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
builder. InsertCell();
// Geef een andere celopvulling op voor de tweede cel.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder. EndRow();
// Wis celopmaak van eerdere bewerkingen.
builder.CellFormat.ClearFormatting();
builder. InsertCell();
// Maak dikkere randen voor de eerste cel in deze rij. Het zal anders zijn
// ten opzichte van de randen die voor de tabel zijn gedefinieerd.
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
builder.Writeln("Cell #3");
builder. InsertCell();
builder.CellFormat.ClearFormatting();
builder.Writeln("Cell #4");
```

## Stap 4: Sla het document op

  gewijzigd
Sla het gewijzigde document ten slotte op in een bestand. U kunt een geschikte naam en locatie voor het uitvoerdocument kiezen.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

Gefeliciteerd! U hebt nu een tabel en een cel met verschillende randen opgemaakt met Aspose.Words voor .NET.

### Voorbeeldbroncode voor het opmaken van tabel en cel met verschillende randen met behulp van Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	//Stel de randen in voor de hele tafel.
	table.SetBorders(LineStyle.Single, 2.0, Color.Black);
	// Stel de celarcering voor deze cel in.
	builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
	builder.Writeln("Cell #1");
	builder.InsertCell();
	// Geef een andere celarcering op voor de tweede cel.
	builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
	builder.Writeln("Cell #2");
	builder.EndRow();
	// Wis de celopmaak van eerdere bewerkingen.
	builder.CellFormat.ClearFormatting();
	builder.InsertCell();
	// Maak grotere randen voor de eerste cel van deze rij. Dit zal anders zijn
	// vergeleken met de randen die voor de tafel zijn ingesteld.
	builder.CellFormat.Borders.Left.LineWidth = 4.0;
	builder.CellFormat.Borders.Right.LineWidth = 4.0;
	builder.CellFormat.Borders.Top.LineWidth = 4.0;
	builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
	builder.Writeln("Cell #3");
	builder.InsertCell();
	builder.CellFormat.ClearFormatting();
	builder.Writeln("Cell #4");
	doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe we een tabel en een cel met verschillende randen kunnen opmaken met behulp van Aspose.Words voor .NET. Door deze stapsgewijze handleiding te volgen, kunt u eenvoudig uw tabel- en celranden in uw Word-documenten aanpassen. Aspose.Words biedt een krachtige en flexibele API voor het manipuleren en opmaken van tabellen in uw documenten. Met deze kennis kunt u de visuele presentatie van uw Word-documenten verbeteren en aan specifieke behoeften voldoen.