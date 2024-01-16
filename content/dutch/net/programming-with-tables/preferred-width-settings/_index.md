---
title: Voorkeursbreedte-instellingen
linktitle: Voorkeursbreedte-instellingen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de gewenste tabelcelbreedtes in een Word-document instelt met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-tables/preferred-width-settings/
---

In deze zelfstudie leren we hoe u de voorkeursbreedte-instellingen voor tabelcellen in een Word-document kunt instellen met behulp van Aspose.Words voor .NET. We zullen een stapsgewijze handleiding volgen om de code te begrijpen en deze functie te implementeren. Aan het einde van deze zelfstudie kunt u verschillende voorkeursbreedten opgeven voor uw tabelcellen in uw Word-documenten.

## Stap 1: Projectconfiguratie
1. Start Visual Studio en maak een nieuw C#-project.
2. Voeg een verwijzing toe naar de Aspose.Words voor .NET-bibliotheek.

## Stap 2: Het document aanmaken en de documentgenerator initialiseren
Volg deze stappen om Woordenverwerking te starten met de document- en documentgenerator:

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Documentcreatie
Document doc = new Document();

// Initialiseer de documentgenerator
DocumentBuilder builder = new DocumentBuilder(doc);
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar uw documentenmap.

## Stap 3: Bouw de tafel met gewenste breedtes
Vervolgens bouwen we een tabel met drie cellen met verschillende voorkeursbreedten. Gebruik de volgende code:

```csharp
// Begin van de tafel
builder. StartTable();

// Voeg een cel van absolute grootte in
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
builder.Writeln("Cell with a width of 40 points");

// Voeg een cel van relatieve grootte in (in percentage)
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
builder.Writeln("Cell with 20% width");

// Voeg een cel met automatische grootte in
builder. InsertCell();
builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
builder.Writeln("Auto-size cell. The size of this cell is calculated from the preferred width of the table. In this case, the cell will fill the rest of the available space.");

// Einde van tafel
builder. EndTable();
```

Hier gebruiken we de documentbuilder om een tabel met drie cellen te bouwen. De eerste cel heeft een voorkeursbreedte van 40 punten, de tweede cel heeft een voorkeursbreedte van 20% van de tabelbreedte en de derde cel heeft een automatische voorkeursbreedte die wordt aangepast

  afhankelijk van de beschikbare ruimte.

## Stap 4: Het gewijzigde document opslaan
Ten slotte moeten we het gewijzigde document opslaan met de voorkeursbreedte-instellingen die voor de tabelcellen zijn gedefinieerd. Gebruik de volgende code:

```csharp
doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

Zorg ervoor dat u het juiste pad en de juiste bestandsnaam voor het uitvoerdocument opgeeft.

### Voorbeeldbroncode voor voorkeursbreedte-instellingen met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Voeg een tabelrij in die bestaat uit drie cellen met verschillende voorkeursbreedten.
	builder.StartTable();
	// Voeg een cel van absolute grootte in.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPoints(40);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightYellow;
	builder.Writeln("Cell at 40 points width");
	// Voeg een cel met relatieve grootte (percentage) in.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.FromPercent(20);
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	builder.Writeln("Cell at 20% width");
	// Voeg een cel met automatische grootte in.
	builder.InsertCell();
	builder.CellFormat.PreferredWidth = PreferredWidth.Auto;
	builder.CellFormat.Shading.BackgroundPatternColor = Color.LightGreen;
	builder.Writeln(
		"Cell automatically sized. The size of this cell is calculated from the table preferred width.");
	builder.Writeln("In this case the cell will fill up the rest of the available space.");
	doc.Save(dataDir + "WorkingWithTables.PreferredWidthSettings.docx");
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u de voorkeursbreedte-instellingen voor tabelcellen in een Word-document kunt instellen met behulp van Aspose.Words voor .NET. Door deze stapsgewijze handleiding te volgen en de meegeleverde C#-code te implementeren, kunt u de celbreedtes van uw tabel aanpassen aan uw specifieke behoeften in uw Word-documenten.