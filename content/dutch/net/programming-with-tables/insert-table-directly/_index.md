---
title: Tabel rechtstreeks invoegen
linktitle: Tabel rechtstreeks invoegen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een tabel rechtstreeks in een Word-document kunt invoegen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-tables/insert-table-directly/
---

In deze zelfstudie leren we hoe u een tabel rechtstreeks in een Word-document kunt invoegen met Aspose.Words voor .NET. We zullen een stapsgewijze handleiding volgen om de code te begrijpen en deze functie te implementeren. Aan het einde van deze zelfstudie kunt u tabellen programmatisch rechtstreeks in uw Word-documenten invoegen.

## Stap 1: Projectconfiguratie
1. Start Visual Studio en maak een nieuw C#-project.
2. Voeg een verwijzing toe naar de Aspose.Words voor .NET-bibliotheek.

## Stap 2: Het document en de tabel maken
Om Words Processing met de array te starten, moeten we een nieuw document maken en de array initialiseren. Volg deze stappen:

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Documentcreatie
Document doc = new Document();

//Maak de array
Table table = new Table(doc);
doc.FirstSection.Body.AppendChild(table);
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar uw documentenmap.

## Stap 3: De array bouwen
Vervolgens bouwen we de tabel door rijen en cellen toe te voegen. Gebruik de volgende code als voorbeeld:

```csharp
// Maak de eerste rij
Row row = new Row(doc);
row.RowFormat.AllowBreakAcrossPages = true;
table.AppendChild(row);

// Maak de eerste cel
Cell cell = new Cell(doc);
cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
cell.CellFormat.Width = 80;
cell.AppendChild(new Paragraph(doc));
cell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 1"));
row.AppendChild(cell);

// Dupliceer de cel voor de tweede cel in de rij
row.AppendChild(cell.Clone(false));
row.LastCell.AppendChild(new Paragraph(doc));
row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Text in row 1, cell 2"));
```

 Hier maken we een rij met de`AllowBreakAcrossPages` eigenschap ingesteld`true` om het afbreken van pagina's tussen rijen mogelijk te maken. Vervolgens maken we een cel met een gekleurde achtergrond, een vaste breedte en een opgegeven tekstinhoud. Vervolgens dupliceren we deze cel om de tweede cel in de rij te maken.

## Stap 4: Auto Fit-tabel
We kunnen automatische aanpassingen aan de tabel toepassen om deze correct op te maken. Gebruik de volgende code:

```csharp
table. AutoFit(AutoFitBehavior.FixedColumnWidths);
```

Deze coderegel past een automatische aanpassing toe op basis van vaste kolombreedtes.

## Stap 5: Registreren van de

  gewijzigd document
Ten slotte moeten we het gewijzigde document opslaan met de tabel rechtstreeks ingevoegd. Gebruik de volgende code:

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

Zorg ervoor dat u het juiste pad en de juiste bestandsnaam voor het uitvoerdocument opgeeft.

### Voorbeeldbroncode voor Tabel rechtstreeks invoegen met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	// We beginnen met het maken van het tabelobject. Merk op dat we het documentobject moeten doorgeven
	//naar de constructor van elk knooppunt. Dit komt omdat elk knooppunt dat we creëren erbij moet horen
	// naar een of ander document.
	Table table = new Table(doc);
	doc.FirstSection.Body.AppendChild(table);
	// Hier kunnen we VerzekerMinimum bellen om de rijen en cellen voor ons te maken. Deze methode wordt gebruikt
	// om ervoor te zorgen dat het opgegeven knooppunt geldig is. In dit geval moet een geldige tabel minimaal één rij en één cel bevatten.
	// In plaats daarvan zullen we zelf de rij en tabel maken.
	// Dit zou de beste manier zijn om dit te doen als we een tabel binnen een algoritme zouden maken.
	Row row = new Row(doc);
	row.RowFormat.AllowBreakAcrossPages = true;
	table.AppendChild(row);
	// We kunnen nu alle instellingen voor automatisch aanpassen toepassen.
	table.AutoFit(AutoFitBehavior.FixedColumnWidths);
	Cell cell = new Cell(doc);
	cell.CellFormat.Shading.BackgroundPatternColor = Color.LightBlue;
	cell.CellFormat.Width = 80;
	cell.AppendChild(new Paragraph(doc));
	cell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 1 Text"));
	row.AppendChild(cell);
	// Vervolgens herhaalden we het proces voor de andere cellen en rijen in de tabel.
	// We kunnen de zaken ook versnellen door bestaande cellen en rijen te klonen.
	row.AppendChild(cell.Clone(false));
	row.LastCell.AppendChild(new Paragraph(doc));
	row.LastCell.FirstParagraph.AppendChild(new Run(doc, "Row 1, Cell 2 Text"));
	doc.Save(dataDir + "WorkingWithTables.InsertTableDirectly.docx");
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u een tabel rechtstreeks in een Word-document kunt invoegen met Aspose.Words voor .NET. Door deze stapsgewijze handleiding te volgen en de meegeleverde C#-code te implementeren, kunt u tabellen rechtstreeks programmatisch in uw Word-documenten invoegen. Met deze functie kunt u tabellen maken en aanpassen aan uw specifieke behoeften.