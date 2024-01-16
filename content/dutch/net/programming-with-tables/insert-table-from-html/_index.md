---
title: Tabel invoegen vanuit HTML
linktitle: Tabel invoegen vanuit HTML
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een tabel uit HTML invoegt in een Word-document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-tables/insert-table-from-html/
---

In deze zelfstudie leren we hoe u vanuit HTML een tabel in een Word-document kunt invoegen met behulp van Aspose.Words voor .NET. We zullen een stapsgewijze handleiding volgen om de code te begrijpen en deze functie te implementeren. Aan het einde van deze zelfstudie kunt u programmatisch tabellen uit HTML in uw Word-documenten invoegen.

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

## Stap 3: De tabel invoegen vanuit HTML
Vervolgens voegen we de tabel in het document in met behulp van HTML-code. Gebruik de volgende code:

```csharp
builder.InsertHtml("<table>" +
"<tr>" +
"<td>Line 1, Cell 1</td>" +
"<td>Line 1, Cell 2</td>" +
"</tr>" +
"<tr>" +
"<td>Line 2, Cell 1</td>" +
"<td>Line 2, Cell 2</td>" +
"</tr>" +
"</table>");
```

 Hier gebruiken wij de`InsertHtml` methode van de documentbouwer om de HTML in te voegen die de tabel bevat. De opgegeven HTML maakt een tabel met twee rijen en twee cellen in elke rij. U kunt de inhoud van de tabel aanpassen door de HTML-code aan uw behoeften aan te passen.

## Stap 4: Het gewijzigde document opslaan
Ten slotte moeten we het gewijzigde document opslaan met de tabel ingevoegd vanuit HTML. Gebruik de volgende code:

```csharp
doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

Zorg ervoor dat u het juiste pad en de juiste bestandsnaam voor het uitvoerdocument opgeeft.

### Voorbeeldbroncode voor Tabel invoegen vanuit HTML met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	// Houd er rekening mee dat AutoFitSettings niet van toepassing is op tabellen die vanuit HTML zijn ingevoegd.
	builder.InsertHtml("<table>" +
					   "<tr>" +
					   "<td>Row 1, Cell 1</td>" +
					   "<td>Row 1, Cell 2</td>" +
					   "</tr>" +
					   "<tr>" +
					   "<td>Row 2, Cell 2</td>" +
					   "<td>Row 2, Cell 2</td>" +
					   "</tr>" +
					   "</table>");
	doc.Save(dataDir + "WorkingWithTables.InsertTableFromHtml.docx");
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u vanuit HTML een tabel in een Word-document kunt invoegen met Aspose.Words voor .NET. Door deze stapsgewijze handleiding te volgen en de meegeleverde C#-code te implementeren, kunt u programmatisch tabellen uit HTML in uw Word-documenten invoegen. Met deze functie kunt u tabelgegevens uit HTML-bronnen converteren en importeren in uw Word-documenten.
