---
title: Volledige tabel klonen
linktitle: Volledige tabel klonen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een volledige tabel naar een Word-document kunt klonen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-tables/clone-complete-table/
---

In deze zelfstudie leren we hoe u Aspose.Words voor .NET kunt gebruiken om een volledige tabel naar een Word-document te klonen. We zullen een stapsgewijze handleiding volgen om de code te begrijpen en deze functie te implementeren. Aan het einde van deze zelfstudie kunt u tabellen programmatisch naar uw Word-documenten klonen.

## Stap 1: Projectconfiguratie
1. Start Visual Studio en maak een nieuw C#-project.
2. Voeg een verwijzing toe naar de Aspose.Words voor .NET-bibliotheek.

## Stap 2: Het document laden en toegang krijgen tot de tabel
Om Woordenverwerking met de tabel te starten, moeten we het document laden dat de tabel bevat en er toegang toe hebben. Volg deze stappen:

```csharp
// Pad naar uw documentenmap
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Laad het document
Document doc = new Document(dataDir + "Tables.docx");

// Toegang tot de array
Table table = (Table)doc.GetChild(NodeType.Table, 0, true);
```

Zorg ervoor dat u "UW DOCUMENTENMAP" vervangt door het daadwerkelijke pad naar uw documentenmap.

## Stap 3: Volledige array-kloon
Vervolgens klonen we de hele tabel en voegen deze na het origineel in het document in. Gebruik de volgende code:

```csharp
// Kloon de array
Table tableClone = (Table)table.Clone(true);

//Plaats de gekloonde tabel na het origineel in het document
table.ParentNode.InsertAfter(tableClone, table);

// Voeg een lege alinea in tussen de twee tabellen
// Anders worden ze bij het opslaan gecombineerd tot één (dit komt door documentvalidatie)
table.ParentNode.InsertAfter(new Paragraph(doc), table);
```

 Hier gebruiken we de`Clone` methode om een volledige kopie van de array te maken. Dan gebruiken wij`InsertAfter` om de gekloonde tabel in het document in te voegen, na de originele tabel. We voegen ook een lege paragraaf toe tussen de twee tabellen om te voorkomen dat ze bij het opslaan worden samengevoegd.

## Stap 4: Het gewijzigde document opslaan
Ten slotte moeten we het gewijzigde document opslaan met de gekloonde tabel. Gebruik de volgende code:

```csharp
// Sla het gewijzigde document op
doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

Zorg ervoor dat u het juiste pad en de juiste bestandsnaam voor het uitvoerdocument opgeeft.
  
### Voorbeeldbroncode voor Clone Complete Table met Aspose.Words voor .NET 

```csharp
	// Pad naar uw documentmap
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document(dataDir + "Tables.docx");
	Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
	// Kloon de tabel en plaats deze na het origineel in het document.
	Table tableClone = (Table) table.Clone(true);
	table.ParentNode.InsertAfter(tableClone, table);
	// Voeg een lege alinea in tussen de twee tabellen,
	// anders worden ze bij het opslaan tot één samengevoegd. Dit heeft te maken met documentvalidatie.
	table.ParentNode.InsertAfter(new Paragraph(doc), table);
	doc.Save(dataDir + "WorkingWithTables.CloneCompleteTable.docx");
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe we een volledige tabel naar een Word-document kunnen klonen met Aspose.Words voor .NET. Door deze stapsgewijze handleiding te volgen en de meegeleverde C#-code te implementeren, kunt u tabellen in uw Word-documenten programmatisch klonen. Met deze functie kunt u geavanceerde manipulaties op arrays uitvoeren om aan uw specifieke behoeften te voldoen.