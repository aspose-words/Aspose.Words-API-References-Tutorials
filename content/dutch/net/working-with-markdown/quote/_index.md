---
title: Citaat
linktitle: Citaat
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u offertes gebruikt met Aspose.Words voor .NET Stapsgewijze handleiding.
type: docs
weight: 10
url: /nl/net/working-with-markdown/quote/
---

In dit voorbeeld leggen we uit hoe je de aanhalingstekensfunctie met Aspose kunt gebruiken. Woorden voor .NET Quote worden gebruikt om delen van de tekst te markeren door ze te omringen met een speciale rand.

## Stap 1: Een documentgenerator gebruiken

Eerst gebruiken we een documentgenerator om inhoud aan ons document toe te voegen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Stap 2: De standaardcitatiestijl gebruiken

We gebruiken de standaard alineastijl genaamd 'Quote' om citaatopmaak op de tekst toe te passen.

```csharp
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");
```

## Stap 3: Stijlen maken voor geneste niveaus

 We kunnen stijlen voor geneste niveaus maken met behulp van de`Styles.Add` werkwijze van de`Document` voorwerp. In dit voorbeeld maken we een stijl met de naam 'Quote1' om een genest citaatniveau weer te geven.

```csharp
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

### Voorbeeldbroncode voor citaten met Aspose.Words voor .NET


```csharp
// Gebruik een documentbuilder om inhoud aan het document toe te voegen.
DocumentBuilder builder = new DocumentBuilder();

// Standaard slaat een document de blockquote-stijl op voor het eerste niveau.
builder.ParagraphFormat.StyleName = "Quote";
builder.Writeln("Blockquote");

// Creëer stijlen voor geneste niveaus via stijlovererving.
Style quoteLevel2 = builder.Document.Styles.Add(StyleType.Paragraph, "Quote1");
builder.ParagraphFormat.Style = quoteLevel2;
builder.Document.Styles["Quote1"].BaseStyleName = "Quote";
builder.Writeln("1. Nested blockquote");
```

Gefeliciteerd! Je hebt nu geleerd hoe je de citatiefunctie kunt gebruiken met Aspose.Words voor .NET.


### Veelgestelde vragen

#### Vraag: Wat is een citaat in Markdown?

A: Een citaat in Markdown is een manier om tekstpassages uit andere bronnen te markeren of om naar beroemde citaten te verwijzen.

#### Vraag: Hoe gebruik ik aanhalingstekens in Markdown?

A: Om een citaat in Markdown te gebruiken, plaatst u de tekst van het citaat tussen punthaken (`>`). Elke regel van het citaat moet beginnen met een punthaak.

#### Vraag: Ondersteunen Markdown-offertes kenmerken?

A: Markdown-citaten ondersteunen geen specifieke kenmerken. Ze worden eenvoudigweg benadrukt door de opmaak van de geciteerde tekst.

#### Vraag: Kun je offertes insluiten in Markdown?

A: Ja, het is mogelijk om aanhalingstekens in Markdown te nesten door een extra niveau punthaken toe te voegen (`>`).