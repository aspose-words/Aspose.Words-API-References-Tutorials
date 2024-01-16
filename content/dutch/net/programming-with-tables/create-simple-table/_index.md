---
title: Maak een eenvoudige tabel
linktitle: Maak een eenvoudige tabel
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een eenvoudige tabel in een Word-document kunt maken met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-tables/create-simple-table/
---

In deze zelfstudie leren we hoe u een eenvoudige tabel in een Word-document kunt maken met Aspose.Words voor .NET. We zullen een stapsgewijze handleiding volgen om de code te begrijpen en deze functie te implementeren. Aan het einde van deze zelfstudie kunt u programmatisch aangepaste tabellen in uw Word-documenten maken.

## Stap 1: Projectconfiguratie
1. Start Visual Studio en maak een nieuw C#-project.
2. Voeg een verwijzing toe naar de Aspose.Words voor .NET-bibliotheek.

## Stap 2: Het document aanmaken en de documentgenerator initialiseren
Om te beginnen met het bouwen van de tabel, moeten we een nieuw document maken en de documentbouwer initialiseren. Volg deze stappen:

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Maak het document en initialiseer de documentgenerator
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar uw documentenmap.

## Stap 3: De array bouwen
Vervolgens bouwen we de tabel met behulp van de methoden van de documentbouwer. Gebruik de volgende code:

```csharp
// Begin met de constructie van de array
builder. StartTable();

// Constructie van de eerste cel van de eerste rij
builder. InsertCell();
builder.Write("Contents of cell 1 of row 1.");

// Constructie van de tweede cel van de eerste rij
builder. InsertCell();
builder.Write("Contents of cell 2 of row 1.");

//Roep de volgende methode aan om de eerste regel te beëindigen en een nieuwe regel te beginnen
builder. EndRow();

// Constructie van de eerste cel van de tweede rij
builder. InsertCell();
builder.Write("Contents of cell 1 of row 2.");

// Constructie van de tweede cel van de tweede rij
builder. InsertCell();
builder.Write("Contents of cell 2 of row 2.");

// Roep de volgende methode aan om de tweede regel te beëindigen
builder. EndRow();

// Indicatie dat de constructie van de tafel is voltooid
builder. EndTable();
```

 Hier gebruiken we de documentbuilder om de tabel stap voor stap op te bouwen. Wij beginnen met bellen`StartTable()` om de tabel te initialiseren en gebruik vervolgens`InsertCell()` cellen invoegen en`Write()` om inhoud aan elke cel toe te voegen. Wij gebruiken ook`EndRow()` om een rij te beëindigen en een nieuwe rij te beginnen. Tenslotte bellen wij`EndTable()` om aan te geven dat de tafelconstructie voltooid is.

## Stap 4: Sla het document op
Tenslotte moeten we sparen

  het document met de gemaakte tabel. Gebruik de volgende code:

```csharp
// Bewaar het document
doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

Zorg ervoor dat u het juiste pad en de juiste bestandsnaam voor het uitvoerdocument opgeeft.

### Voorbeeldbroncode voor Create Simple Table met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Begin met het bouwen van de tafel.
	builder.StartTable();
	builder.InsertCell();
	builder.Write("Row 1, Cell 1 Content.");
	// Bouw de tweede cel.
	builder.InsertCell();
	builder.Write("Row 1, Cell 2 Content.");
	// Roep de volgende methode aan om de rij te beëindigen en een nieuwe rij te beginnen.
	builder.EndRow();
	// Bouw de eerste cel van de tweede rij.
	builder.InsertCell();
	builder.Write("Row 2, Cell 1 Content");
	// Bouw de tweede cel.
	builder.InsertCell();
	builder.Write("Row 2, Cell 2 Content.");
	builder.EndRow();
	//Geef aan dat we klaar zijn met het bouwen van de tafel.
	builder.EndTable();
	doc.Save(dataDir + "WorkingWithTables.CreateSimpleTable.docx");
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u een eenvoudige tabel in een Word-document kunt maken met Aspose.Words voor .NET. Door deze stapsgewijze handleiding te volgen en de meegeleverde C#-code te implementeren, kunt u programmatisch aangepaste tabellen in uw Word-documenten maken. Met deze functie kunt u uw gegevens op een gestructureerde en duidelijke manier opmaken en ordenen.