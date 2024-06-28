---
title: Geef lijstniveau op
linktitle: Geef lijstniveau op
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u het lijstniveau in een Word-document kunt opgeven met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-list/specify-list-level/
---

In deze stapsgewijze zelfstudie laten we u zien hoe u het lijstniveau in een Word-document kunt opgeven met behulp van Aspose.Words voor .NET. We leggen de meegeleverde C#-broncode uit en laten u zien hoe u deze in uw eigen projecten kunt implementeren.

 Zorg er om te beginnen voor dat Aspose.Words voor .NET is geïnstalleerd en geconfigureerd in uw ontwikkelomgeving. Als u dat nog niet heeft gedaan, downloadt en installeert u de bibliotheek van[Aspose.Releases]https://releases.aspose.com/words/net/.

## Stap 1: Het creëren van de Document- en Documentgenerator

Maak eerst een nieuw document en een bijbehorende documentgenerator:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 2: Een genummerde lijst maken en toepassen

Maak vervolgens een genummerde lijst op basis van een van de lijstsjablonen van Microsoft Word en pas deze toe op de huidige alinea in de documentbuilder:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);
```

## Stap 3: Lijstniveauspecificatie

 Gebruik die van de documentbuilder`ListLevelNumber` eigenschap om het lijstniveau op te geven en tekst aan de alinea toe te voegen:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

Herhaal deze stappen om lijstniveaus op te geven en op elk niveau tekst toe te voegen.

## Stap 4: Een lijst met opsommingstekens maken en toepassen

U kunt ook een lijst met opsommingstekens maken en toepassen met behulp van een van de lijstsjablonen van Microsoft Word:

```csharp
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);
```

## Stap 5: Tekst toevoegen aan lijstniveaus met opsommingstekens

 Gebruik de`ListLevelNumber` eigenschap opnieuw om het niveau van de lijst met opsommingstekens op te geven en tekst toe te voegen:

```csharp
for (int i = 0; i < 9; i++)
{
     builder.ListFormat.ListLevelNumber = i;
     builder.Writeln("Level " + i);
}
```

## Stap 6: Stop met het opmaken van de lijst

 Om het opmaken van de lijst te stoppen, stelt u in`null` naar de`List`eigenschap van de documentgenerator:

```csharp
builder. ListFormat. List = null;
```

## Stap 7: Het gewijzigde document opslaan

Sla het gewijzigde document op:

```csharp
builder.Document.Save(dataDir + "SpecifyListLevel.docx");
```

Dus ! U hebt met succes het lijstniveau in een Word-document opgegeven met Aspose.Words voor .NET.

### Voorbeeldbroncode om lijstniveau op te geven

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

// Maak een genummerde lijst op basis van een van de Microsoft Word-lijstsjablonen.
//en pas het toe op de huidige paragraaf van de documentbouwer.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.NumberArabicDot);

// Er zijn negen niveaus in deze lijst, laten we ze allemaal proberen.
for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// Maak een lijst met opsommingstekens op basis van een van de Microsoft Word-lijstsjablonen.
//en pas het toe op de huidige paragraaf van de documentbouwer.
builder.ListFormat.List = doc.Lists.Add(ListTemplate.BulletDiamonds);

for (int i = 0; i < 9; i++)
{
	builder.ListFormat.ListLevelNumber = i;
	builder.Writeln("Level " + i);
}

// Dit is een manier om de lijstopmaak te stoppen.
builder.ListFormat.List = null;

builder.Document.Save(dataDir + "WorkingWithList.SpecifyListLevel.docx");
            
```

### Veelgestelde vragen

#### Vraag: Hoe kan ik het lijstniveau opgeven in Aspose.Words?

 A: Om het lijstniveau in Aspose.Words te specificeren, moet u een exemplaar van de`List` klasse en geef deze een genummerde lijst. Dan kun je gebruik maken van de`Paragraph.ListFormat.ListLevelNumber` eigenschap om het niveau van elk lijstitem op te geven. U kunt deze lijst aan een sectie van uw document koppelen, zodat de lijstitems het gewenste niveau hebben.

#### Vraag: Is het mogelijk om het nummeringsformaat van lijstitems in Aspose.Words te wijzigen?

 A: Ja, u kunt het nummeringsformaat van lijstitems in Aspose.Words wijzigen. De`ListLevel` class biedt hiervoor verschillende eigenschappen, zoals`ListLevel.NumberFormat`, `ListLevel.NumberStyle`, `ListLevel.NumberPosition`, enz. U kunt deze eigenschappen gebruiken om het nummeringsformaat in te stellen voor lijstitems, zoals Arabische cijfers, Romeinse cijfers, letters, enz.

#### Vraag: Kan ik extra niveaus toevoegen aan een genummerde lijst in Aspose.Words?

 A: Ja, het is mogelijk om extra niveaus toe te voegen aan een genummerde lijst in Aspose.Words. De`ListLevel`Met class kunt u opmaakeigenschappen instellen voor elk niveau van de lijst. U kunt opties instellen zoals voorvoegsel, achtervoegsel, uitlijning, inspringing, enz. Hiermee kunt u lijsten maken met meerdere hiërarchieniveaus.


