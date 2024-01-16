---
title: Lijstopmaak op meerdere niveaus in Word-document
linktitle: Lijstopmaak op meerdere niveaus in Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een lijst met meerdere niveaus maakt en aangepaste opmaak toepast in een Word-document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/document-formatting/multilevel-list-formatting/
---
In deze zelfstudie laten we u zien hoe u de lijstopmaak op meerdere niveaus in de Word-documentfunctie gebruikt met Aspose.Words voor .NET. Volg de onderstaande stappen om de broncode te begrijpen en de wijzigingen toe te passen.

## Stap 1: Het document aanmaken en configureren

Maak om te beginnen een nieuw document en een bijbehorend DocumentBuilder-object. Hier is hoe:

```csharp
// Pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 2: De lijst met meerdere niveaus opmaken

We zullen nu de lijstopmaak met meerdere niveaus toepassen met behulp van de methoden die beschikbaar zijn in het DocumentBuilder-object. Hier is hoe:

```csharp
builder.ListFormat.ApplyNumberDefault();
builder. Writen("Element 1");
builder. Writen("Element 2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.1");
builder.Writeln("Element 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Element 2.2.1");
builder.Writeln("Element 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Element 3");

builder.ListFormat.RemoveNumbers();
```

## Stap 3: Het document opslaan

 Nadat u het tekstinvoerformulierveld hebt ingevoegd, slaat u het document op de gewenste locatie op met behulp van de`Save` methode. Zorg ervoor dat u het juiste bestandspad opgeeft:

```csharp
doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");
```

### Voorbeeldbroncode voor Multilevel List Formatting met Aspose.Words voor .NET

Hier is de volledige broncode voor de functie voor lijstopmaak op meerdere niveaus met Aspose.Words voor .NET:


```csharp

// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

builder.ListFormat.ApplyNumberDefault();
builder.Writeln("Item 1");
builder.Writeln("Item 2");

builder.ListFormat.ListIndent();
builder.Writeln("Item 2.1");
builder.Writeln("Item 2.2");

builder.ListFormat.ListIndent();
builder.Writeln("Item 2.2.1");
builder.Writeln("Item 2.2.2");

builder.ListFormat.ListOutdent();
builder.Writeln("Item 2.3");

builder.ListFormat.ListOutdent();
builder.Writeln("Item 3");

builder.ListFormat.RemoveNumbers();

doc.Save(dataDir + "DocumentFormatting.MultilevelListFormatting.docx");

```

Met deze code kunt u een lijst met meerdere niveaus maken en de juiste opmaak op elk niveau toepassen met behulp van Aspose.Words voor .NET.


## Conclusie

In deze zelfstudie hebben we het proces onderzocht van het gebruik van de functie voor lijstopmaak op meerdere niveaus in een Word-document met Aspose.Words voor .NET. Door de beschreven stappen te volgen, kunt u overzichtelijke lijsten met meerdere niveaus maken, waardoor de structuur en leesbaarheid van uw documenten worden verbeterd.

### Veelgestelde vragen

#### Vraag: Wat is een lijst met meerdere niveaus in een Word-document?

A: Een lijst met meerdere niveaus in een Word-document is een hiërarchische lijst waarmee u items kunt indelen in verschillende niveaus van subitems. Het helpt informatie op een gestructureerde manier te presenteren, waardoor het voor lezers gemakkelijker wordt om de inhoud te begrijpen.

#### Vraag: Kan ik het uiterlijk van de lijst met meerdere niveaus aanpassen?

A: Ja, u kunt het uiterlijk van de lijst met meerdere niveaus in uw Word-document aanpassen. Door verschillende stijlen toe te passen, zoals opsommingstekens, cijfers of letters, en de inspringing en spatiëring aan te passen, kunt u een visueel aantrekkelijke en overzichtelijke lijst maken.

#### Vraag: Ondersteunt Aspose.Words voor .NET andere lijstopmaakopties?

A: Ja, Aspose.Words voor .NET biedt een uitgebreide reeks functies voor het opmaken van lijsten. Het ondersteunt verschillende lijsttypen, waaronder lijsten met opsommingstekens, genummerde lijsten en lijsten met meerdere niveaus. U kunt de opmaak van lijsten manipuleren, items toevoegen of verwijderen en het uiterlijk ervan aanpassen.

#### Vraag: Kan ik Aspose.Words voor .NET gebruiken om met andere documentelementen te werken?

A: Ja, Aspose.Words voor .NET biedt uitgebreide mogelijkheden voor het werken met verschillende documentelementen, zoals alinea's, tabellen, afbeeldingen en meer. Hiermee kunt u Word-documenten programmatisch maken, wijzigen en converteren, waardoor documentverwerkingstaken worden gestroomlijnd.