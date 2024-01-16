---
title: Rijopmaak Schakel het verdelen over pagina's uit
linktitle: Rijopmaak Schakel het verdelen over pagina's uit
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u regeleinde voor een tabel op meerdere pagina's in een Word-document kunt uitschakelen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-tables/row-format-disable-break-across-pages/
---

In deze zelfstudie gaan we leren hoe u regeleinde van een tabel met meerdere pagina's in een Word-document kunt uitschakelen met behulp van Aspose.Words voor .NET. We zullen een stapsgewijze handleiding volgen om de code te begrijpen en deze functie te implementeren. Aan het einde van deze zelfstudie kunt u regelafbrekingen uitschakelen voor alle rijen in uw tabel in uw Word-documenten.

## Stap 1: Projectconfiguratie
1. Start Visual Studio en maak een nieuw C#-project.
2. Voeg een verwijzing toe naar de Aspose.Words voor .NET-bibliotheek.

## Stap 2: Het document laden
Volg deze stappen om de tekstverwerking met het document te starten:

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laad het document
Document doc = new Document(dataDir + "Table spanning two pages.docx");
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar uw documentenmap en geef de juiste bestandsnaam op.

## Stap 3: Schakel het einde van de tabelrij uit
Vervolgens schakelen we het afbreken van rijen uit voor alle rijen in de tabel. Gebruik de volgende code:

```csharp
// Haal de tabel op
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// Schakel rij-einde uit voor alle rijen in de tabel
foreach(Row row in table.Rows)
row.RowFormat.AllowBreakAcrossPages = false;
```

 Hier gebruiken we het document om de eerste tabel op te halen en vervolgens door alle rijen in de tabel te itereren met behulp van een foreach-lus. Binnen de lus schakelen we het breken van rijen voor elke rij uit door de`RowFormat.AllowBreakAcrossPages`eigendom aan`false`.

## Stap 4: Het gewijzigde document opslaan
Ten slotte moeten we het gewijzigde document opslaan met het tabelregeleinde uitgeschakeld. Gebruik de volgende code:

```csharp
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

Zorg ervoor dat u het juiste pad en de juiste bestandsnaam voor het uitvoerdocument opgeeft.

### Voorbeeldbroncode voor rij-indeling Schakel Break Across Pages uit met Aspose.Words voor .NET 

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Table spanning two pages.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
// Schakel het opsplitsen van pagina's uit voor alle rijen in de tabel.
foreach (Row row in table.Rows)
	row.RowFormat.AllowBreakAcrossPages = false;
doc.Save(dataDir + "WorkingWithTables.RowFormatDisableBreakAcrossPages.docx");
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u regeleinde van een tabel met meerdere pagina's in een Word-document kunt uitschakelen met behulp van Aspose.Words voor .NET. Door deze stapsgewijze handleiding te volgen en de meegeleverde C#-code te implementeren, kunt u deze uitschakeling toepassen op uw tabellen in uw Word-documenten.