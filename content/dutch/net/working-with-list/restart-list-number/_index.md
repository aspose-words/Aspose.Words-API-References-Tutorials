---
title: Lijstnummer opnieuw starten
linktitle: Lijstnummer opnieuw starten
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u het nummer van een lijst in een Word-document opnieuw kunt instellen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-list/restart-list-number/
---
In deze stapsgewijze zelfstudie laten we u zien hoe u het nummer van een lijst in een Word-document opnieuw kunt instellen met Aspose.Words voor .NET. We leggen de meegeleverde C#-broncode uit en laten u zien hoe u deze in uw eigen projecten kunt implementeren.

 Zorg er om te beginnen voor dat Aspose.Words voor .NET is geïnstalleerd en geconfigureerd in uw ontwikkelomgeving. Als u dat nog niet heeft gedaan, downloadt en installeert u de bibliotheek van[Aspose.Releases]https://releases.aspose.com/words/net/.

## Stap 1: Het creëren van de Document- en Documentgenerator

Maak eerst een nieuw document en een bijbehorende documentgenerator:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 2: De eerste lijst maken en aanpassen

Maak vervolgens een lijst op basis van een bestaande sjabloon en pas vervolgens de niveaus aan:

```csharp
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;
```

## Stap 3: Items toevoegen aan de eerste lijst

Gebruik de documentbuilder om items aan de eerste lijst toe te voegen en lijstnummers te verwijderen:

```csharp
builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## Stap 4: De tweede lijst maken en aanpassen

Als u de eerste lijst opnieuw wilt gebruiken door het nummer opnieuw in te stellen, maakt u een kopie van de originele lijstindeling:

```csharp
List list2 = doc.Lists.AddCopy(list1);
list2.ListLevels[0].StartAt = 10;
```

Indien nodig kunt u ook aanvullende wijzigingen aanbrengen in de tweede lijst.

## Stap 5: Items toevoegen aan de tweede lijst

Gebruik de documentbuilder opnieuw om items aan de tweede lijst toe te voegen en de lijstnummers te verwijderen:

```csharp
builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder. Writen("Element 1");
builder. Writen("Element 2");
builder.ListFormat.RemoveNumbers();
```

## Stap 6: Sla het gewijzigde document op

Sla ten slotte het gewijzigde document op:

```csharp
builder.Document.Save(dataDir + "ResetListNumber.docx");
```

Dus ! U hebt met succes het nummer van een lijst in een Word-document opnieuw ingesteld met behulp van Aspose.Words voor .NET.

### Voorbeeldbroncode voor het opnieuw instellen van lijstnummers

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Maak een lijst op basis van een sjabloon.
List list1 = doc.Lists.Add(ListTemplate.NumberArabicParenthesis);
list1.ListLevels[0].Font.Color = Color.Red;
list1.ListLevels[0].Alignment = ListLevelAlignment.Right;

builder.Writeln("List 1 starts below:");
builder.ListFormat.List = list1;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

// Om de eerste lijst opnieuw te gebruiken, moeten we de nummering opnieuw starten door een kopie van de originele lijstopmaak te maken.
List list2 = doc.Lists.AddCopy(list1);

// We kunnen de nieuwe lijst op welke manier dan ook aanpassen, inclusief het instellen van een nieuw startnummer.
list2.ListLevels[0].StartAt = 10;

builder.Writeln("List 2 starts below:");
builder.ListFormat.List = list2;
builder.Writeln("Item 1");
builder.Writeln("Item 2");
builder.ListFormat.RemoveNumbers();

builder.Document.Save(dataDir + "WorkingWithList.RestartListNumber.docx");
            
```

### Veelgestelde vragen

#### Vraag: Hoe kan ik de nummering van een lijst in Aspose.Words opnieuw starten?

 A: Om de nummering van een lijst in Aspose.Words opnieuw te starten, kunt u de`ListRestartAtNumber` werkwijze van de`List` klas. Met deze methode kunt u een nieuwe belwaarde instellen van waaruit de lijst opnieuw moet worden gestart. U kunt bijvoorbeeld gebruiken`list.ListRestartAtNumber(1)` om de nummering opnieuw te starten vanaf 1.

#### Vraag: Is het mogelijk om het voor- en achtervoegsel van opnieuw gestarte lijstnummering in Aspose.Words aan te passen?

 A: Ja, u kunt het voor- en achtervoegsel van opnieuw opgestarte lijstnummering aanpassen in Aspose.Words. De`ListLevel` klasse biedt eigenschappen zoals`ListLevel.NumberPrefix` En`ListLevel.NumberSuffix` waarmee u het voor- en achtervoegsel voor elk niveau in de lijst kunt opgeven. U kunt deze eigenschappen gebruiken om het voor- en achtervoegsel indien nodig aan te passen.

#### Vraag: Hoe kan ik een specifieke nummeringswaarde opgeven van waaruit de lijst opnieuw moet worden gestart?

A: Om een specifieke getalswaarde op te geven vanaf waar de lijst opnieuw moet worden opgestart, kunt u de`ListRestartAtNumber` methode die de gewenste waarde als argument doorgeeft. Als u bijvoorbeeld de nummering opnieuw wilt starten vanaf 5, kunt u gebruiken`list.ListRestartAtNumber(5)`.

#### Vraag: Is het mogelijk om de lijstnummering op meerdere niveaus opnieuw te starten in Aspose.Words?

 A: Ja, Aspose.Words ondersteunt hernummering van meerdere lijstniveaus. U kunt de`ListRestartAtNumber` methode op elk lijstniveau om de nummering afzonderlijk te herstarten. U kunt bijvoorbeeld gebruiken`list.Levels[0].ListRestartAtNumber(1)` om het eerste lijstniveau opnieuw te starten vanaf 1, en`list.Levels[1].ListRestartAtNumber(1)` om de lijst op het tweede niveau opnieuw te starten vanaf 1, enzovoort.



