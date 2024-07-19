---
title: Omheinde code
linktitle: Omheinde code
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de afgeschermde codefunctie gebruikt met Aspose.Words voor .NET Stapsgewijze handleiding.
type: docs
weight: 10
url: /nl/net/working-with-markdown/fenced-code/
---

In dit voorbeeld laten we u zien hoe u de afgeschermde codefunctie gebruikt met Aspose.Words voor .NET. omheinde code wordt gebruikt om codeblokken met een specifieke opmaak weer te geven.

## Stap 1: Een documentgenerator gebruiken

Eerst gebruiken we een documentgenerator om inhoud aan ons document toe te voegen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Stap 2: Een stijl toevoegen voor omheinde code

 We zullen een aangepaste stijl toevoegen voor de omheinde code met behulp van de`Styles.Add` werkwijze van de`Document` voorwerp. In dit voorbeeld maken we een stijl met de naam 'FencedCode' voor de afgeschermde code.

```csharp
Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
```

## Stap 3: Omheinde code toevoegen zonder info

Nu kunnen we een omheind codeblok zonder informatiereeks toevoegen met behulp van de aangepaste stijl "FencedCode".

```csharp
builder.Writeln("This is an fenced code");
```

## Stap 4: Voeg omheinde code toe met inforeeks

We kunnen ook een omheind codeblok toevoegen met een reeks informatie met behulp van een andere aangepaste stijl. In dit voorbeeld maken we een stijl met de naam "FencedCode.C#" om een blok C#-code weer te geven.

```csharp
Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### Voorbeeldbroncode voor omheinde code met Aspose.Words voor .NET

```csharp
// Gebruik een documentbuilder om inhoud aan het document toe te voegen.
DocumentBuilder builder = new DocumentBuilder();

Style fencedCode = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode");
builder.ParagraphFormat.Style = fencedCode;
builder.Writeln("This is an fenced code");

Style fencedCodeWithInfo = builder.Document.Styles.Add(StyleType.Paragraph, "FencedCode.C#");
builder.ParagraphFormat.Style = fencedCodeWithInfo;
builder.Writeln("This is a fenced code with info string");
```

### Veelgestelde vragen

#### Vraag: Wat is gescheiden code in Markdown?

A: Gescheiden code in Markdown is een opmaakmethode die wordt gebruikt om code in een Markdown-document weer te geven. Het bestaat uit het inlijsten van de code met specifieke scheidingstekens.

#### Vraag: Wat zijn de voordelen van gescheiden code in Markdown?

A: Gescheiden code in Markdown verbetert de leesbaarheid van de code en maakt het voor lezers gemakkelijker om deze te begrijpen. Het maakt het ook mogelijk om syntaxisaccentuering in sommige Markdown-editors te behouden.

#### Vraag: Wat is het verschil tussen code met scheidingstekens en ingesprongen code in Markdown?

A: Gescheiden code gebruikt specifieke scheidingstekens om de code te omsluiten, terwijl ingesprongen code inhoudt dat elke regel code wordt ingesprongen met spaties of tabs.

#### Vraag: Wordt de code met scheidingstekens in Markdown ondersteund door alle Markdown-editors?

A: Ondersteuning voor gescheiden code in Markdown kan variëren per Markdown-editor. Controleer voor de zekerheid de specifieke documentatie van uw uitgever.

