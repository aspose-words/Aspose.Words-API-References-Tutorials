---
title: Ruimte tussen Aziatische en Latijnse tekst in Word-document
linktitle: Ruimte tussen Aziatische en Latijnse tekst in Word-document
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de ruimte tussen Aziatische en Latijnse tekst in een Word-document automatisch kunt aanpassen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/document-formatting/space-between-asian-and-latin-text/
---
In deze zelfstudie laten we u zien hoe u de functie Ruimte tussen Aziatische en Latijnse tekst in Word-documenten gebruikt met Aspose.Words voor .NET. Volg de onderstaande stappen om de broncode te begrijpen en de wijzigingen toe te passen.

## Stap 1: Het document aanmaken en configureren

Maak om te beginnen een nieuw document en een bijbehorend DocumentBuilder-object. Hier is hoe:

```csharp
// Pad naar de documentenmap.
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 2: De ruimte tussen Aziatische en Latijnse tekst instellen

We gaan nu de ruimte tussen Aziatische en Latijnse tekst configureren met behulp van de eigenschappen van het ParagraphFormat-object. Hier is hoe:

```csharp
ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

builder.Writeln("Auto adjust space between Asian and Latin text");
builder.Writeln("Auto adjust space between Asian text and numbers");
```

## Stap 3: Het document opslaan

 Nadat u het tekstinvoerformulierveld hebt ingevoegd, slaat u het document op de gewenste locatie op met behulp van de`Save` methode. Zorg ervoor dat u het juiste bestandspad opgeeft:

```csharp
doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
```

### Voorbeeldbroncode voor ruimte tussen Aziatische en Latijnse tekst met Aspose.Words voor .NET

Hier is de volledige broncode voor de functie Ruimte tussen Aziatische en Latijnse tekst met Aspose.Words voor .NET:


```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);

ParagraphFormat paragraphFormat = builder.ParagraphFormat;
paragraphFormat.AddSpaceBetweenFarEastAndAlpha = true;
paragraphFormat.AddSpaceBetweenFarEastAndDigit = true;

builder.Writeln("Automatically adjust space between Asian and Latin text");
builder.Writeln("Automatically adjust space between Asian text and numbers");

doc.Save(dataDir + "DocumentFormatting.SpaceBetweenAsianAndLatinText.docx");
```

Met deze code kunt u automatisch de ruimte tussen Aziatische en Latijnse tekst in uw document aanpassen met behulp van Aspose.Words voor .NET.

## Conclusie

In deze zelfstudie hebben we het proces van het gebruik van de spatiefunctie onderzocht om de afstand tussen Aziatische en Latijnse tekst in een Word-document aan te passen met Aspose.Words voor .NET. Door de beschreven stappen te volgen, kunt u zorgen voor de juiste spatiëring en uitlijning, wat vooral handig is als u te maken heeft met gemengde Aziatische en Latijnse inhoud.

### Veelgestelde vragen

#### Vraag: Wat is de spatiefunctie tussen Aziatische en Latijnse tekst in een Word-document?

A: De functie Ruimte tussen Aziatische en Latijnse tekst in een Word-document verwijst naar de mogelijkheid om automatisch de afstand aan te passen tussen tekst die in verschillende scripts is geschreven, zoals Aziatisch (bijvoorbeeld Chinees, Japans) en Latijn (bijvoorbeeld Engels).

#### Vraag: Waarom is het belangrijk om de ruimte tussen Aziatische en Latijnse tekst aan te passen?

A: Het aanpassen van de ruimte tussen Aziatische en Latijnse tekst is van cruciaal belang om ervoor te zorgen dat verschillende scripts harmonieus in het document passen. Een juiste spatiëring verbetert de leesbaarheid en het algehele visuele uiterlijk, waardoor wordt voorkomen dat tekst er te krap of verspreid uitziet.

#### Vraag: Kan ik de ruimte-aanpassingen tussen verschillende scripts aanpassen?

 A: Ja, u kunt de ruimte-aanpassingen tussen verschillende scripts aanpassen met behulp van de`AddSpaceBetweenFarEastAndAlpha` En`AddSpaceBetweenFarEastAndDigit` eigenschappen. Door deze eigenschappen in of uit te schakelen, kunt u de ruimte tussen Aziatische en Latijnse tekst, en tussen Aziatische tekst en cijfers, beheren.

#### Vraag: Ondersteunt Aspose.Words voor .NET andere documentopmaakfuncties?

A: Ja, Aspose.Words voor .NET biedt uitgebreide ondersteuning voor verschillende documentopmaakfuncties. Het bevat functionaliteiten voor lettertypestijlen, alinea's, tabellen, afbeeldingen en meer. U kunt uw Word-documenten effectief programmatisch manipuleren en opmaken.

#### Vraag: Waar kan ik aanvullende bronnen en documentatie vinden voor Aspose.Words voor .NET?

 A: Ga voor uitgebreide bronnen en documentatie over het gebruik van Aspose.Words voor .NET naar[Aspose.Words API-referentie](https://reference.aspose.com/words/net/). Daar vindt u gedetailleerde handleidingen, tutorials, codevoorbeelden en API-referenties om u te helpen effectief gebruik te maken van de krachtige functies van Aspose.Words voor .NET.