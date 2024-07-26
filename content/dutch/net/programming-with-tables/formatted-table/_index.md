---
title: Opgemaakte tabel
linktitle: Opgemaakte tabel
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een opgemaakte tabel in een Word-document maakt met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-tables/formatted-table/
---

In deze zelfstudie leren we hoe u een opgemaakte tabel in een Word-document kunt maken met behulp van Aspose.Words voor .NET. We zullen een stapsgewijze handleiding volgen om de code te begrijpen en deze functie te implementeren. Aan het einde van deze zelfstudie kunt u programmatisch tabellen met aangepaste opmaak in uw Word-documenten maken.

## Stap 1: Projectconfiguratie
1. Start Visual Studio en maak een nieuw C#-project.
2. Voeg een verwijzing toe naar de Aspose.Words voor .NET-bibliotheek.

## Stap 2: Het document aanmaken en de documentgenerator initialiseren
Om te beginnen met het bouwen van de opgemaakte tabel, moeten we een nieuw document maken en de documentgenerator initialiseren. Volg deze stappen:

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//Maak het document en initialiseer de documentgenerator
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar uw documentenmap.

## Stap 3: De opgemaakte tabel bouwen
Vervolgens bouwen we de opgemaakte tabel met behulp van de methoden van de documentbouwer. Gebruik de volgende code:

```csharp
// Begin met de constructie van de array
Table table = builder. StartTable();

// Constructie van de tabelkoprij
builder. InsertCell();
table. LeftIndent = 20.0;
builder.RowFormat.Height = 40.0;
builder.RowFormat.HeightRule = HeightRule.AtLeast;
builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
builder.Font.Size = 16;
builder.Font.Name = "Arial";
builder.Font.Bold = true;
builder.CellFormat.Width = 100.0;
builder.Write("Header Row,\n Cell 1");

builder. InsertCell();
builder.Write("Header Row,\n Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Header Row,\n Cell 3");

builder. EndRow();

// Constructie van het arraylichaam
builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
builder.CellFormat.Width = 100.0;
builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
builder.RowFormat.Height = 30.0;
builder.RowFormat.HeightRule = HeightRule.Auto;

builder. InsertCell();
builder.Font.Size = 12;
builder.Font.Bold = false;
builder.Write("Content Line 1, Cell 1");

builder. InsertCell();
builder.Write("Content Line 1, Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Content Line 1, Cell

3");

builder. EndRow();

builder. InsertCell();
builder.CellFormat.Width = 100.0;
builder.Write("Content Line 2, Cell 1");

builder. InsertCell();
builder.Write("Content Line 2, Cell 2");

builder. InsertCell();
builder.CellFormat.Width = 200.0;
builder.Write("Content Line 2, Cell 3");

builder. EndRow();

// Einde van de array-constructie
builder. EndTable();
```

 Hier gebruiken we de documentbuilder om de tabel stap voor stap op te bouwen. Wij beginnen met bellen`StartTable()` om de tabel te initialiseren. Dan gebruiken wij`InsertCell()` cellen invoegen en`Write()` om inhoud aan elke cel toe te voegen. We gebruiken ook verschillende opmaakeigenschappen om de opmaak van tabelrijen, cellen en tekst te definiëren.

## Stap 4: Sla het document op
Ten slotte moeten we het document opslaan dat de opgemaakte tabel bevat. Gebruik de volgende code:

```csharp
// Bewaar het document
doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

Zorg ervoor dat u het juiste pad en de juiste bestandsnaam voor het uitvoerdocument opgeeft.

### Voorbeeldbroncode voor opgemaakte tabel met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Table table = builder.StartTable();
	builder.InsertCell();
	// Tabelbrede opmaak moet worden toegepast nadat ten minste één rij in de tabel aanwezig is.
	table.LeftIndent = 20.0;
	// Stel de hoogte in en definieer de hoogteregel voor de koprij.
	builder.RowFormat.Height = 40.0;
	builder.RowFormat.HeightRule = HeightRule.AtLeast;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.FromArgb(198, 217, 241);
	builder.ParagraphFormat.Alignment = ParagraphAlignment.Center;
	builder.Font.Size = 16;
	builder.Font.Name = "Arial";
	builder.Font.Bold = true;
	builder.CellFormat.Width = 100.0;
	builder.Write("Header Row,\n Cell 1");
	// We hoeven de breedte van deze cel niet op te geven, omdat deze is overgenomen van de vorige cel.
	builder.InsertCell();
	builder.Write("Header Row,\n Cell 2");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Header Row,\n Cell 3");
	builder.EndRow();
	builder.CellFormat.Shading.BackgroundPatternColor = Color.White;
	builder.CellFormat.Width = 100.0;
	builder.CellFormat.VerticalAlignment = CellVerticalAlignment.Center;
	// Stel de hoogte opnieuw in en definieer een andere hoogteregel voor het tabellichaam.
	builder.RowFormat.Height = 30.0;
	builder.RowFormat.HeightRule = HeightRule.Auto;
	builder.InsertCell();
	// Lettertypeopmaak opnieuw instellen.
	builder.Font.Size = 12;
	builder.Font.Bold = false;
	builder.Write("Row 1, Cell 1 Content");
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Row 1, Cell 3 Content");
	builder.EndRow();
	builder.InsertCell();
	builder.CellFormat.Width = 100.0;
	builder.Write("Row 2, Cell 1 Content");
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content");
	builder.InsertCell();
	builder.CellFormat.Width = 200.0;
	builder.Write("Row 2, Cell 3 Content.");
	builder.EndRow();
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.FormattedTable.docx");
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u een opgemaakte tabel in een Word-document kunt maken met Aspose.Words voor .NET. Door deze stapsgewijze handleiding te volgen en de meegeleverde C#-code te implementeren, kunt u programmatisch aangepaste tabellen met specifieke opmaak in uw Word-documenten maken. Met deze functie kunt u uw gegevens op een visueel aantrekkelijke en georganiseerde manier presenteren en structureren.