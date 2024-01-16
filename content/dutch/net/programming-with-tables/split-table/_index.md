---
title: Tabel splitsen
linktitle: Tabel splitsen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een tabel in een Word-document kunt splitsen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-tables/split-table/
---

In deze zelfstudie leren we hoe u een tabel in een Word-document kunt splitsen met Aspose.Words voor .NET. We zullen een stapsgewijze handleiding volgen om de code te begrijpen en deze functie te implementeren. Aan het einde van deze tutorial kunt u een tabel uit een bepaalde rij in uw Word-documenten splitsen.

## Stap 1: Projectconfiguratie
1. Start Visual Studio en maak een nieuw C#-project.
2. Voeg een verwijzing toe naar de Aspose.Words voor .NET-bibliotheek.

## Stap 2: Het document laden
Volg deze stappen om de tekstverwerking met het document te starten:

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laad het document
Document doc = new Document(dataDir + "Tables.docx");
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar uw documentenmap en geef de juiste bestandsnaam op.

## Stap 3: De tafel verdelen
Vervolgens splitsen we de tabel van een bepaalde rij. Gebruik de volgende code:

```csharp
// Haal de eerste tabel op
Table firstTable = (Table)doc.GetChild(NodeType.Table, 0, true);

// Bepaling van de lijn van waaruit de tafel moet worden verdeeld
Row row = firstTable.Rows[2];

// Maak een nieuwe container voor de gesplitste tabel
Table table = (Table)firstTable.Clone(false);

// Plaats de container na de originele tafel
firstTable.ParentNode.InsertAfter(table, firstTable);

// Voeg een bufferparagraaf toe om de afstand tussen de tabellen te behouden
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);

// Verplaats rijen van de oorspronkelijke tabel naar de gesplitste tabel
Row currentRow;
do
{
currentRow = firstTable.LastRow;
table. PrependChild(currentRow);
} while (currentRow != row);
```

Hier gebruiken we het document om de eerste tabel uit het documentknooppunt op te halen. Vervolgens bepalen we de rij waarvan we de tabel willen splitsen, in dit voorbeeld is dat de derde rij (index 2). Vervolgens maken we een nieuwe container door de originele tabel te klonen en deze vervolgens na de originele tabel in te voegen. We voegen ook een bufferparagraaf toe om de afstand tussen de twee tabellen te behouden. Vervolgens verplaatsen we rijen van de oorspronkelijke tabel naar de gesplitste tabel met behulp van een do-while-lus totdat we de opgegeven rij bereiken.

## Stap 4: Het gewijzigde document opslaan
Ten slotte moeten we de

  document gewijzigd met de gesplitste tabel. Gebruik de volgende code:

```csharp
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

Zorg ervoor dat u het juiste pad en de juiste bestandsnaam voor het uitvoerdocument opgeeft.

### Voorbeeldbroncode voor Split Table met Aspose.Words voor .NET 

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table firstTable = (Table) doc.GetChild(NodeType.Table, 0, true);
// We splitsen de tafel op de derde rij (inclusief).
Row row = firstTable.Rows[2];
// Maak een nieuwe container voor de gesplitste tabel.
Table table = (Table) firstTable.Clone(false);
// Plaats de container na het origineel.
firstTable.ParentNode.InsertAfter(table, firstTable);
// Voeg een bufferparagraaf toe om ervoor te zorgen dat de tabellen uit elkaar blijven.
firstTable.ParentNode.InsertAfter(new Paragraph(doc), firstTable);
Row currentRow;
do
{
	currentRow = firstTable.LastRow;
	table.PrependChild(currentRow);
} while (currentRow != row);
doc.Save(dataDir + "WorkingWithTables.SplitTable.docx");
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u een tabel in een Word-document kunt splitsen met Aspose.Words voor .NET. Door deze stapsgewijze handleiding te volgen en de meegeleverde C#-code te implementeren, kunt u eenvoudig tabellen van een bepaalde regel in uw Word-documenten splitsen.