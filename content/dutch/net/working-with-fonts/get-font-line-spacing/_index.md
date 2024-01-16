---
title: Regelafstand lettertype verkrijgen
linktitle: Regelafstand lettertype verkrijgen
second_title: Aspose.Words-API voor documentverwerking
description: In deze zelfstudie leert u hoe u de regelafstand van lettertypen in een Word-document kunt verkrijgen met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-fonts/get-font-line-spacing/
---
In deze zelfstudie gaan we u vertellen hoe u de regelafstand van het lettertype in een Word-document kunt verkrijgen met behulp van de Aspose.Words-bibliotheek voor .NET. De regelafstand van het lettertype definieert de verticale ruimte tussen tekstregels. We nemen u stap voor stap mee om u te helpen de code in uw .NET-project te begrijpen en te implementeren.

## Vereisten
Zorg ervoor dat u over de volgende items beschikt voordat u begint:
- Een praktische kennis van de programmeertaal C#
- De Aspose.Words-bibliotheek voor .NET die in uw project is geïnstalleerd

## Stap 1: Maak een nieuw document en een documentgenerator
 Eerst zullen we een nieuw document maken door het`Document` klasse en een documentbouwer door het`DocumentBuilder` klas.

```csharp
// Maak een nieuw document
Document doc = new Document();

//Maak een documentgenerator
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 2: Configureer het lettertype
 Vervolgens zullen we het lettertype configureren door de`Name` eigendom van de documentgenerator.

```csharp
// Configureer het lettertype
builder.Font.Name = "Calibri";
```

## Stap 3: Voeg tekst toe aan het document
We zullen nu de documentgenerator gebruiken om opgemaakte tekst aan het document toe te voegen.

```csharp
// Voeg tekst toe aan het document
builder. Writen("qText");
```

## Stap 4: Verkrijg de regelafstand van het lettertype
 Nu zullen we toegang krijgen tot de`Font` object van de eerste alinea van het document en haal de waarde op van de`LineSpacing` eigendom.

```csharp
// Verkrijg de regelafstand van het lettertype
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

### Voorbeeldbroncode voor Get Font Line Spacing met Aspose.Words voor .NET 
```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
builder.Font.Name = "Calibri";
builder.Writeln("qText");
Font font = builder.Document.FirstSection.Body.FirstParagraph.Runs[0].Font;
Console.WriteLine($"lineSpacing = {font.LineSpacing}");
```

## Conclusie
In deze tutorial hebben we gezien hoe je de regelafstand van het lettertype in een Word-document kunt krijgen met Aspose.Words voor .NET. De regelafstand van het lettertype is belangrijk voor het regelen van de verticale afstand tussen tekstregels. U kunt deze functie gerust gebruiken om de weergave van uw tekst in uw documenten aan te passen.

### Veelgestelde vragen

#### Vraag: Hoe kan ik de regelafstand van specifieke tekst in een Word-document wijzigen?

A: Met Aspose.Words kunt u eenvoudig de regelafstand van specifieke tekst in een Word-document wijzigen. Gebruik de API om de gewenste tekst te selecteren en de afstand tussen de regels aan te passen door de juiste waarde op te geven.

#### Vraag: Is het mogelijk om exacte afstanden tussen regels toe te passen in een Word-document?

A: Ja, met Aspose.Words kunt u de exacte afstand tussen regels in een Word-document toepassen. Met behulp van de API kunt u een precieze waarde voor de regelafstand opgeven.

#### Vraag: Hoe kan ik de regelafstand voor het hele Word-document aanpassen?

A: Met Aspose.Words kunt u eenvoudig de regelafstand voor het hele Word-document aanpassen. Gebruik de methoden van de API om de gewenste regelafstand voor het hele document op te geven.

#### Vraag: Ondersteunt Aspose.Words meerdere regelafstanden?

A: Ja, Aspose.Words ondersteunt meerdere regelafstanden in Word-documenten. U kunt meerdere spaties instellen, zoals 1,5 keer of 2 keer de normale spatiëring, voor de regels van uw tekst.

#### Vraag: Hoe kan ik problemen met lijnoverlap voorkomen bij het aanpassen van de regelafstand?

A: Om problemen met lijnoverlap te voorkomen bij het aanpassen van de afstand tussen lijnen, moet u ervoor zorgen dat u de juiste afstandswaarden kiest. Test ook de uiteindelijke weergave van uw document om er zeker van te zijn dat de tekst leesbaar en goed opgemaakt blijft.