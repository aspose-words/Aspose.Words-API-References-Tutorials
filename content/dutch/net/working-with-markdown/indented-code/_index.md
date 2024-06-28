---
title: Ingesprongen code
linktitle: Ingesprongen code
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u ingesprongen code kunt gebruiken met Aspose.Words voor .NET Stapsgewijze handleiding.
type: docs
weight: 10
url: /nl/net/working-with-markdown/indented-code/
---

In dit voorbeeld leggen we uit hoe u de ingesprongen codefunctie gebruikt met Aspose.Words voor .NET. Ingesprongen code wordt gebruikt om codeblokken visueel weer te geven met een specifieke opmaak.

## Stap 1: Een documentgenerator gebruiken

Eerst gebruiken we een documentgenerator om inhoud aan ons document toe te voegen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Stap 2: Voeg styling toe voor de opgegeven code

We zullen een aangepaste stijl toevoegen voor de ingesprongen code met behulp van de`Styles.Add` werkwijze van de`Document` voorwerp. In dit voorbeeld maken we een stijl met de naam "IndentedCode" voor ingesprongen code.

```csharp
Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
```

## Stap 3: Voeg de opgegeven code toe

Nu kunnen we een ingesprongen codeblok toevoegen met behulp van de aangepaste stijl "IndentedCode".

```csharp
builder.Writeln("This is an indented code block");
```

### Voorbeeldbroncode voor ingesprongen code met Aspose.Words voor .NET

```csharp
// Gebruik een documentbuilder om inhoud aan het document toe te voegen.
DocumentBuilder builder = new DocumentBuilder();

Style indentedCode = builder.Document.Styles.Add(StyleType.Paragraph, "IndentedCode");
builder.ParagraphFormat.Style = indentedCode;
builder.Writeln("This is an indented code");
```

Gefeliciteerd! U hebt nu geleerd hoe u de ingesprongen codefunctie kunt gebruiken met Aspose.Words voor .NET.


### Veelgestelde vragen

#### Vraag: Wat is de opgegeven code in Markdown?

A: Ingesprongen code in Markdown is een opmaakmethode die wordt gebruikt om code in een Markdown-document weer te geven. Het bestaat uit het inspringen van elke regel code met spaties of tabs.

#### Vraag: Hoe gebruik ik ingesprongen code in Markdown?

A: Om ingesprongen code in Markdown te gebruiken, laat u elke regel code inspringen met spaties of tabs.

#### Vraag: Wat zijn de voordelen van ingesprongen code in Markdown?

A: Ingesprongen code in Markdown verbetert de leesbaarheid van de code en maakt het voor lezers gemakkelijker om deze te begrijpen.

#### Vraag: Wat is het verschil tussen ingesprongen code en codeblokken in Markdown?

A: Ingesprongen code wordt gebruikt voor kleine codefragmenten die in tekst worden ingevoegd, terwijl codeblokken worden gebruikt om grotere stukjes code in afzonderlijke opmaak weer te geven.

#### Vraag: Wordt ingesprongen code in Markdown ondersteund door alle Markdown-editors?

A: Ondersteuning voor ingesprongen code in Markdown kan variëren per Markdown-editor. Controleer voor de zekerheid de specifieke documentatie van uw uitgever.