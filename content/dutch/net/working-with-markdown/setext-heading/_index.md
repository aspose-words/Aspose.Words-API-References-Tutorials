---
title: Setex-rubriek
linktitle: Setex-rubriek
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u Setext-koppen kunt gebruiken om uw documenten op te maken met Aspose.Words voor .NET Stapsgewijze handleiding.
type: docs
weight: 10
url: /nl/net/working-with-markdown/setext-heading/
---

In deze zelfstudie laten we u zien hoe u de Setext Heading-functie gebruikt met Aspose.Words voor .NET. Setext Heading is een alternatieve methode voor het opmaken van titels in Markdown-documenten.

## Stap 1: Een documentgenerator gebruiken

Eerst gebruiken we een documentgenerator om inhoud aan ons document toe te voegen.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
DocumentBuilder builder = new DocumentBuilder();
```

## Stap 2: Gebruik de Setext-kopstijl

We gaan de standaard alineastijl 'Kop 1' gebruiken om een kop op niveau 1 in ons document te maken.

```csharp
builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");
```

## Stap 3: Stijlen opnieuw instellen

We hebben eerder toegepaste lettertypestijlen opnieuw ingesteld om ongewenste combinaties van stijlen tussen alinea's te voorkomen.

```csharp
builder.Font.Bold = false;
builder.Font.Italic = false;
```

## Stap 4: Setext-kopniveaus aanpassen

We kunnen Setext-kopniveaus aanpassen door nieuwe alineastijlen toe te voegen op basis van bestaande kopstijlen. In dit voorbeeld maken we een stijl "SetextHeading1" op basis van de stijl "Heading 1" om een kop van niveau 1 in het Setext-formaat weer te geven.

```csharp
Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Title Setext level 1");
```

## Stap 5: Het document opslaan

Ten slotte kunnen we het document in het gewenste formaat opslaan.

```csharp
builder.Document.Save(dataDir + "Test.md");
```

### Voorbeeldbroncode voor Setext-titels met Aspose.Words voor .NET

```csharp
// Het pad naar de documentenmap.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Gebruik een documentbuilder om inhoud aan het document toe te voegen.
DocumentBuilder builder = new DocumentBuilder();

builder.ParagraphFormat.StyleName = "Heading 1";
builder.Writeln("This is an H1 tag");

// Stijlen uit de vorige alinea opnieuw instellen om stijlen tussen alinea's niet te combineren.
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading1 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading1");
builder.ParagraphFormat.Style = setexHeading1;
builder.Document.Styles["SetextHeading1"].BaseStyleName = "Heading 1";
builder.Writeln("Setext Heading level 1");

builder.ParagraphFormat.Style = builder.Document.Styles["Heading 3"];
builder.Writeln("This is an H3 tag");

// Stijlen uit de vorige alinea opnieuw instellen om stijlen tussen alinea's niet te combineren.
builder.Font.Bold = false;
builder.Font.Italic = false;

Style setexHeading2 = builder.Document.Styles.Add(StyleType.Paragraph, "SetextHeading2");
builder.ParagraphFormat.Style = setexHeading2;
builder.Document.Styles["SetextHeading2"].BaseStyleName = "Heading 3";

// Het Setex-kopniveau wordt opnieuw ingesteld op 2 als de basisparagraaf een kopniveau groter dan 2 heeft.
builder.Writeln("Setext Heading level 2");


builder.Document.Save(dataDir + "Test.md");
```

### Veelgestelde vragen

#### Vraag: Wat is een Setext Markdown-header?

A: Een Setext Markdown-header is een alternatieve manier om koppen in een Markdown-document te maken. Er worden onderstrepingstekens (= of -) gebruikt om verschillende niveaus van koppen aan te geven.

#### Vraag: Hoe gebruik ik Setext Markdown-headers?

A: Om Setext Markdown-koppen te gebruiken, plaatst u onderstrepingstekens onder de titeltekst. Gebruik gelijktekens (=) voor een koptekst van niveau 1 en koppeltekens (-) voor een koptekst van niveau 2.

#### Vraag: Zijn er beperkingen bij het gebruik van Setext Markdown-headers?

A: Setext Markdown-koppen hebben beperkingen wat betreft de kophiërarchie en zijn niet zo visueel verschillend als standaard Markdown-koppen.

#### Vraag: Kan ik het uiterlijk van Setext Markdown-headers aanpassen?

A: In standaard Markdown is het niet mogelijk om het uiterlijk van Setext Markdown-headers aan te passen. Ze hebben een vooraf gedefinieerd uiterlijk op basis van de gebruikte onderstrepingstekens.

#### Vraag: Worden Setext Markdown-headers ondersteund door alle Markdown-editors?

A: Ondersteuning voor Setext Markdown-headers kan variëren tussen Markdown-editors. Controleer voor de zekerheid de specifieke documentatie van uw uitgever.