---
title: Omheinde code
linktitle: Omheinde code
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u afgeschermde code en informatiereeksen aan Word-documenten kunt toevoegen met Aspose.Words voor .NET. Stap-voor-stap handleiding inbegrepen. Verbeter uw vaardigheden op het gebied van documentopmaak.
type: docs
weight: 10
url: /nl/net/working-with-markdown/fenced-code/
---
## Invoering

Hallo daar, mede-codeur! Vandaag duiken we in de wereld van Aspose.Words voor .NET om de kunst onder de knie te krijgen van het toevoegen van afgeschermde code en afgeschermde code met inforeeksen aan uw Word-documenten. Stel je je Word-document voor als een canvas en jij, de kunstenaar, staat op het punt te schilderen met de precisie van een doorgewinterde ontwikkelaar. Met Aspose.Words krijgt u de mogelijkheid om uw documenten programmatisch te verbeteren met gestructureerde, opgemaakte codeblokken, waardoor uw technische documenten professionaliteit en duidelijkheid uitstralen.

## Vereisten

Voordat we verder gaan met de tutorial, zorgen we ervoor dat je alles hebt wat je nodig hebt:

- Basiskennis van C#: Een algemeen begrip van C# zal u helpen de concepten snel te begrijpen.
-  Aspose.Words voor .NET: Aspose.Words voor .NET moet geïnstalleerd zijn. Als je het nog niet hebt, pak het dan[hier](https://releases.aspose.com/words/net/).
- Ontwikkelomgeving: Visual Studio of een andere C# IDE waarmee u vertrouwd bent.

## Naamruimten importeren

Allereerst moet u de benodigde naamruimten importeren. Dit is hetzelfde als het verzamelen van al uw gereedschap voordat u aan een project begint.

```csharp
using Aspose.Words;
using Aspose.Words.Style;
```

Laten we het proces nu stap voor stap opsplitsen.

## Stap 1: Uw project opzetten

Voordat we mooie, opgemaakte codeblokken in ons Word-document kunnen maken, moeten we een nieuw project opzetten in Visual Studio.

1. Maak een nieuw project: Open Visual Studio en maak een nieuwe C#-consoletoepassing.
2. Aspose.Words toevoegen Referentie: Installeer Aspose.Words via NuGet Package Manager. U kunt dit doen door met de rechtermuisknop op uw project te klikken in Solution Explorer, 'NuGet-pakketten beheren' te selecteren en te zoeken naar Aspose.Words.

## Stap 2: Initialiseer DocumentBuilder

Nu uw project is ingesteld, gaan we de DocumentBuilder initialiseren, wat ons belangrijkste hulpmiddel zal zijn voor het toevoegen van inhoud aan het Word-document.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Stap 3: Creëer een stijl voor omheinde code

Om omheinde code toe te voegen, moeten we eerst een stijl maken. Zie dit als het instellen van het thema voor ons codeblok.

```csharp
Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
fencedCode.Font.Name = "Courier New";
fencedCode.Font.Size = 10;
fencedCode.ParagraphFormat.LeftIndent = 20;
fencedCode.ParagraphFormat.RightIndent = 20;
fencedCode.ParagraphFormat.Shading.BackgroundPatternColor = Color.LightGray;
```

## Stap 4: Voeg omheinde code toe aan het document

Nu onze stijl gereed is, kunnen we nu een omheind codeblok aan het document toevoegen.

```csharp
builder.ParagraphFormat.Style = fencedCode;
builder.Writeln("This is a fenced code block");
```

## Stap 5: Maak een stijl voor omheinde code met Info String

Soms wilt u misschien de programmeertaal specificeren of extra informatie aan uw codeblok toevoegen. Laten we daar een stijl voor creëren.

```csharp
Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
fencedCodeWithInfo.Font.Name = "Courier New";
fencedCodeWithInfo.Font.Size = 10;
fencedCodeWithInfo.ParagraphFormat.LeftIndent = 20;
fencedCodeWithInfo.ParagraphFormat.RightIndent = 20;
fencedCodeWithInfo.ParagraphFormat.Shading.BackgroundPatternColor = Color.LightGray;
```

## Stap 6: Voeg omheinde code met inforeeks toe aan het document

Laten we nu een omheind codeblok toevoegen met een infotekenreeks om aan te geven dat het C#-code is.

```csharp
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code block with info string - C#");
```

## Conclusie

Gefeliciteerd! U hebt zojuist afgeschermde codeblokken en afgeschermde code met informatiereeksen aan uw Word-documenten toegevoegd met behulp van Aspose.Words voor .NET. Dit is slechts het topje van de ijsberg. Met Aspose.Words kunt u uw documentverwerking naar nieuwe hoogten automatiseren en verbeteren. Blijf ontdekken en veel codeerplezier!

## Veelgestelde vragen

### Wat is Aspose.Words voor .NET?
Aspose.Words voor .NET is een krachtige bibliotheek waarmee ontwikkelaars Word-documenten programmatisch kunnen maken, manipuleren en converteren.

### Kan ik Aspose.Words met andere programmeertalen gebruiken?
Aspose.Words ondersteunt voornamelijk .NET-talen, maar er zijn versies beschikbaar voor Java, Python en andere talen.

### Is Aspose.Words gratis te gebruiken?
 Aspose.Words is een commercieel product, maar u kunt een gratis proefversie downloaden[hier](https://releases.aspose.com/)om de kenmerken ervan te verkennen.

### Hoe kan ik ondersteuning krijgen voor Aspose.Words?
 U kunt ondersteuning krijgen van de Aspose-community en ontwikkelaars[hier](https://forum.aspose.com/c/words/8).

### Welke andere functies biedt Aspose.Words?
Aspose.Words biedt een breed scala aan functies, waaronder documentconversie, op sjablonen gebaseerde documentgeneratie, rapportage en nog veel meer.