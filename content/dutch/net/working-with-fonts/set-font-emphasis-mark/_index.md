---
title: Lettertype-nadrukmarkering instellen
linktitle: Lettertype-nadrukmarkering instellen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de nadrukstijl van het lettertype in een Word-document instelt met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-fonts/set-font-emphasis-mark/
---

In deze zelfstudie laten we u zien hoe u de nadrukstijl van het lettertype in een Word-document instelt met behulp van Aspose.Words voor .NET. Lettertypenadruk wordt gebruikt om bepaalde woorden of zinsdelen in de tekst te markeren.

## Vereisten
Zorg ervoor dat u over de volgende items beschikt voordat u begint:
- Een praktische kennis van de programmeertaal C#
- De Aspose.Words-bibliotheek voor .NET die in uw project is geïnstalleerd

## Stap 1: Definieer de documentmap
Begin met het instellen van het mappad naar de locatie van uw Word-document. Vervangen`"YOUR DOCUMENT DIRECTORY"` in de code met het juiste pad.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Stap 2: Maak het document en pas het aan
 Maak een exemplaar van de`Document` klasse en een geassocieerde`DocumentBuilder` om de documentinhoud op te bouwen. Gebruik de`Font.EmphasisMark` eigenschap om de nadrukstijl van het lettertype in te stellen`EmphasisMark.UnderSolidCircle` . Gebruik dan de`Write` En`Writeln` methoden van de`DocumentBuilder` om tekst toe te voegen met de nadruk op het opgegeven lettertype.

```csharp
Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasized text");
builder. Writen();
builder.Font.ClearFormatting();
builder.Write("Simple text");
```

## Stap 3: Sla het document op
 Sla het document op met behulp van de`Save` werkwijze van de`Document` met het juiste pad en de juiste bestandsnaam.

```csharp
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

### Voorbeeldbroncode voor Set Font Emphasis Mark met Aspose.Words voor .NET 

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document document = new Document();
DocumentBuilder builder = new DocumentBuilder(document);
builder.Font.EmphasisMark = EmphasisMark.UnderSolidCircle;
builder.Write("Emphasis text");
builder.Writeln();
builder.Font.ClearFormatting();
builder.Write("Simple text");
document.Save(dataDir + "WorkingWithFonts.SetFontEmphasisMark.docx");
```

## Conclusie
In deze zelfstudie hebt u geleerd hoe u de nadrukstijl van het lettertype in een Word-document kunt instellen met behulp van Aspose.Words voor .NET. Experimenteer met verschillende nadrukstijlen en gebruik deze functie om woorden of zinsdelen in uw documenten te markeren.

### Veelgestelde vragen

#### Vraag: Hoe kan ik accenttekens toevoegen aan een specifiek lettertype in een Word-document met Aspose.Words?

A: Om accenttekens toe te voegen aan een specifiek lettertype in een Word-document met Aspose.Words, kunt u de API gebruiken om naar het gewenste lettertype te navigeren en de juiste accenttekens toe te passen. Hierdoor worden accenttekens toegevoegd aan de tekst met het geselecteerde lettertype.

#### Vraag: Is het mogelijk om de stijl van accenttekens in een Word-document te wijzigen met Aspose.Words?

A: Ja, met Aspose.Words kun je de stijl van accenttekens in een Word-document wijzigen. Met de API kunt u stijleigenschappen aanpassen, zoals kleur, grootte, lijntype, enz., om het uiterlijk van accenttekens aan te passen.

#### Vraag: Hoe kan ik alle accenttekens uit een Word-document verwijderen met Aspose.Words?

A: Om alle accenttekens uit een Word-document te verwijderen met Aspose.Words, kunt u de API gebruiken om door het document te bladeren, bestaande accenttekens te detecteren en deze te verwijderen met behulp van de juiste methoden. Hiermee worden alle nadruktekens uit het document verwijderd.

#### Vraag: Kan ik accenttekens toevoegen aan een specifiek tekstgedeelte in een Word-document?

A: Ja, u kunt accenttekens toevoegen aan een specifiek tekstgedeelte in een Word-document met Aspose.Words. U kunt met behulp van de API het gewenste tekstbereik selecteren en de juiste nadruktekens aan dat deel van de tekst toevoegen.

#### Vraag: Kunnen de accenttekens worden aangepast aan mijn behoeften?

A: Ja, accenttekens kunnen aan uw behoeften worden aangepast met Aspose.Words. U kunt de stijleigenschappen van accenttekens, zoals kleur, grootte, lijntype en meer, aanpassen aan uw opmaakvoorkeuren.