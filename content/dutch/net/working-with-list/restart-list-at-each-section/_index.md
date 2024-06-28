---
title: Herstart de lijst bij elke sectie
linktitle: Herstart de lijst bij elke sectie
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een genummerde lijst opnieuw instelt voor elke sectie in een Word-document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-list/restart-list-at-each-section/
---

In deze stapsgewijze zelfstudie laten we u zien hoe u een genummerde lijst voor elke sectie in een Word-document opnieuw kunt instellen met behulp van Aspose.Words voor .NET. We leggen de meegeleverde C#-broncode uit en laten u zien hoe u deze in uw eigen projecten kunt implementeren.

 Zorg er om te beginnen voor dat Aspose.Words voor .NET is geïnstalleerd en geconfigureerd in uw ontwikkelomgeving. Als u dat nog niet heeft gedaan, downloadt en installeert u de bibliotheek van[Aspose.Releases]https://releases.aspose.com/words/net/.

## Stap 1: Het document en de lijst maken

Maak eerst een nieuw document en voeg een standaard genummerde lijst toe:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;
```

## Stap 2: Items aan de lijst toevoegen

 Gebruik dan een`DocumentBuilder` om items aan de lijst toe te voegen. U kunt een lus gebruiken om meerdere items aan de lijst toe te voegen:

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
     builder.Writeln($"List item {i}");

     if (i == 15)
         builder.InsertBreak(BreakType.SectionBreakNewPage);
}
```

In dit voorbeeld voegen we een sectie-einde in na het 15e lijstitem om het hernummeren te illustreren.

## Stap 3: Sla het gewijzigde document op

Sla ten slotte het gewijzigde document op:

```csharp
OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);
```

Dus ! U hebt met succes een genummerde lijst voor elke sectie in een Word-document opnieuw ingesteld met behulp van Aspose.Words voor .NET.

### Voorbeeldbroncode voor het opnieuw instellen van de lijst bij elke sectie

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();

doc.Lists.Add(ListTemplate.NumberDefault);

List list = doc.Lists[0];
list. IsRestartAtEachSection = true;

DocumentBuilder builder = new DocumentBuilder(doc);
builder.ListFormat.List = list;

for (int i = 1; i < 45; i++)
{
	 builder.Writeln($"List item {i}");

	 if (i == 15)
		 builder.InsertBreak(BreakType.SectionBreakNewPage);
}

OoxmlSaveOptions options = new OoxmlSaveOptions { Compliance = OoxmlCompliance.Iso29500_2008_Transitional };

doc.Save(dataDir + "ResetListAtEachSection.docx", options);

```

U kunt deze code gerust in uw eigen projecten gebruiken en aanpassen aan uw specifieke behoeften.

### Veelgestelde vragen

#### Vraag: Hoe kan ik een lijst in elke sectie in Aspose.Words opnieuw starten?

 A: Om een lijst bij elke sectie in Aspose.Words opnieuw te starten, moet u een exemplaar van de`List`klasse en wijs er een genummerde lijst aan toe. Dan kun je gebruik maken van de`List.IsRestartAtEachSection` eigenschap om aan te geven dat de nummering bij elke sectie opnieuw moet worden gestart. U kunt deze lijst koppelen aan één of meerdere secties van uw document, zodat de nummering bij elke sectie correct opnieuw wordt gestart.

#### Vraag: Kan ik het nummeringsformaat van lijsten in Aspose.Words aanpassen?

 A: Ja, u kunt het nummeringsformaat van lijsten in Aspose.Words aanpassen. De`List` class biedt hiervoor verschillende eigenschappen, zoals`List.ListFormat.ListType`, `List.ListLevels`, `ListLevel.NumberFormat`, enz. U kunt deze eigenschappen gebruiken om het lijsttype (genummerd, met opsommingstekens, enz.), de nummeringsnotatie (Arabische cijfers, Romeinse cijfers, letters, enz.) en andere opmaakopties voor nummering in te stellen.

#### Vraag: Is het mogelijk om extra niveaus toe te voegen aan een genummerde lijst in Aspose.Words?

 A: Ja, het is mogelijk om extra niveaus toe te voegen aan een genummerde lijst in Aspose.Words. De`ListLevel`Met class kunt u opmaakeigenschappen instellen voor elk niveau van de lijst. U kunt opties instellen zoals voorvoegsel, achtervoegsel, uitlijning, inspringing, enz. Hiermee kunt u lijsten maken met meerdere hiërarchieniveaus.