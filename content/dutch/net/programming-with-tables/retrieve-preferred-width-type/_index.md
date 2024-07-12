---
title: Haal het gewenste breedtetype op
linktitle: Haal het gewenste breedtetype op
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u het type en de gewenste breedtewaarde van een cel in een Word-tabel kunt ophalen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/programming-with-tables/retrieve-preferred-width-type/
---

In deze zelfstudie leren we hoe u het gewenste breedtetype en de waarde ervan kunt ophalen uit een tabelcel in een Word-document met behulp van Aspose.Words voor .NET. We zullen een stapsgewijze handleiding volgen om de code te begrijpen en deze functie te implementeren. Aan het einde van deze zelfstudie kunt u het gewenste breedtetype (absoluut, relatief of automatisch) en de waarde ervan voor een specifieke cel in uw Word-documenttabellen ophalen.

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

## Stap 3: Het gewenste breedtetype en de gewenste waarde ophalen
Vervolgens halen we het gewenste breedtetype en de waarde ervan voor een specifieke tabelcel op. Gebruik de volgende code:

```csharp
// Haal de tabel op
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);

// Automatische tafelaanpassing activeren
table. AllowAutoFit = true;

//Haal de eerste cel van de eerste rij op
Cell firstCell = table.FirstRow.FirstCell;

// Haal het gewenste breedtetype en de waarde ervan op
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

 Hier gebruiken we het document om de eerste tabel op te halen, waarna we automatische tabelaanpassing inschakelen met de`AllowAutoFit` eigendom. Vervolgens halen we de eerste cel van de eerste rij van de tabel op. Vanuit deze cel kunnen we het gewenste breedtetype ophalen met de`PreferredWidth.Type` eigendom en de waarde ervan met de`PreferredWidth.Value` eigendom.

### Voorbeeldbroncode voor het ophalen van het gewenste breedtetype met Aspose.Words voor .NET 

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document(dataDir + "Tables.docx");
Table table = (Table) doc.GetChild(NodeType.Table, 0, true);
table.AllowAutoFit = true;
Cell firstCell = table.FirstRow.FirstCell;
PreferredWidthType type = firstCell.CellFormat.PreferredWidth.Type;
double value = firstCell.CellFormat.PreferredWidth.Value;
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u het gewenste breedtetype en de waarde ervan kunt ophalen uit een tabelcel in een Word-document met behulp van Aspose.Words voor .NET. Door deze stapsgewijze handleiding te volgen en de meegeleverde C#-code te implementeren, kunt u deze informatie voor specifieke cellen in uw Word-documenttabellen ophalen.