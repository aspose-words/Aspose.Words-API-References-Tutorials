---
title: Houd de tafel bij elkaar
linktitle: Houd de tafel bij elkaar
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een tabel bij elkaar houdt in een Word-document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-tables/keep-table-together/
---

In deze tutorial gaan we leren hoe we een tabel bij elkaar kunnen houden in een Word-document met behulp van Aspose.Words voor .NET. We zullen een stapsgewijze handleiding volgen om de code te begrijpen en deze functie te implementeren. Aan het einde van deze zelfstudie kunt u een tabel intact houden zonder dat deze over meerdere pagina's in uw Word-documenten wordt opgesplitst.

## Stap 1: Projectconfiguratie
1. Start Visual Studio en maak een nieuw C#-project.
2. Voeg een verwijzing toe naar de Aspose.Words voor .NET-bibliotheek.

## Stap 2: Het document laden en de tabel ophalen
Om Woordenverwerking met de tabel te starten, moeten we het document laden en de tabel ophalen die we bij elkaar willen houden. Volg deze stappen:

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laad het document
Document doc = new Document(dataDir + "Table spanning two pages.docx");

// Haal de tabel op
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar uw documentenmap.

## Stap 3: Schakel de optie "KeepWithNext" in
Om de tabel bij elkaar te houden en te voorkomen dat deze over meerdere pagina's wordt opgesplitst, moeten we de optie "KeepWithNext" inschakelen voor elke paragraaf in de tabel, behalve voor de laatste paragrafen van de laatste rij van de tabel. Gebruik de volgende code:

```csharp
foreach(Cell cell in table.GetChildNodes(NodeType.Cell, true))
{
cell.EnsureMinimum();
foreach(Paragraph para in cell.Paragraphs)
if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
para.ParagraphFormat.KeepWithNext = true;
}
```

Hier doorlopen we elke cel in de tabel en schakelen we de optie "KeepWithNext" in voor elke alinea in de cel, behalve voor de laatste alinea's van de laatste rij in de tabel.

## Stap 4: Het gewijzigde document opslaan
Ten slotte moeten we het gewijzigde document opslaan met de tabel bij elkaar gehouden. Gebruik de volgende code:

```csharp
doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

Zorg ervoor dat u het juiste pad en de juiste bestandsnaam voor het uitvoerdocument opgeeft.

### Voorbeeldbroncode voor Keep Table Together met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Table spanning two pages.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// We moeten KeepWithNext inschakelen voor elke paragraaf in de tabel om te voorkomen dat deze over een pagina wordt verspreid.
	// behalve de laatste alinea's in de laatste rij van de tabel.
	foreach (Cell cell in table.GetChildNodes(NodeType.Cell, true))
	{
		cell.EnsureMinimum();
		foreach (Paragraph para in cell.Paragraphs)
			if (!(cell.ParentRow.IsLastRow && para.IsEndOfCell))
				para.ParagraphFormat.KeepWithNext = true;
	}
	doc.Save(dataDir + "WorkingWithTables.KeepTableTogether.docx");
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u een tabel bij elkaar kunt houden in een Word-document met behulp van Aspose.Words voor .NET. Door deze stapsgewijze handleiding te volgen en de meegeleverde C#-code te implementeren, kunt u een tabel intact houden en voorkomen dat deze zich over meerdere pagina's in uw documenten opsplitst. Deze functie geeft u meer controle over het uiterlijk en de indeling van uw tabellen in uw documenten.