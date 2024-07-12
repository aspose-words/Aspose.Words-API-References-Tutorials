---
title: Inline-code
linktitle: Inline-code
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u code inline kunt plaatsen met Aspose.Words voor .NET Stapsgewijze handleiding.
type: docs
weight: 10
url: /nl/net/working-with-markdown/inline-code/
---

In dit voorbeeld laten we u zien hoe u de inline codefunctie gebruikt met Aspose.Words voor .NET. Inlinecode wordt gebruikt om stukjes code binnen een alinea visueel weer te geven.

## Stap 1: Een documentgenerator gebruiken

Eerst gebruiken we een documentgenerator om inhoud aan ons document toe te voegen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Stap 2: Voeg styling toe voor inline code

 We zullen een aangepaste stijl toevoegen voor de inline code met behulp van de`Styles.Add` werkwijze van de`Document` voorwerp. In dit voorbeeld maken we een stijl met de naam 'InlineCode' voor inline code met een standaard backtick.

```csharp
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
```

## Stap 3: Voeg inlinecode toe

Nu kunnen we inline code toevoegen met behulp van de aangepaste stijl "InlineCode". In dit voorbeeld voegen we twee stukken tekst toe met verschillende aantallen backticks.

```csharp
builder.Writeln("Text with InlineCode style with 1 backtick");
```

```csharp
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backticks");
```


### Voorbeeldbroncode voor inlinecode met Aspose.Words voor .NET

```csharp
// Gebruik een documentbuilder om inhoud aan het document toe te voegen.
DocumentBuilder builder = new DocumentBuilder();

// Het aantal backticks wordt gemist; standaard wordt één backticks gebruikt.
Style inlineCode1BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode");
builder.Font.Style = inlineCode1BackTicks;
builder.Writeln("Text with InlineCode style with 1 backtick");

// Er zullen 3 backticks zijn.
Style inlineCode3BackTicks = builder.Document.Styles.Add(StyleType.Character, "InlineCode.3");
builder.Font.Style = inlineCode3BackTicks;
builder.Writeln("Text with InlineCode style with 3 backtick");
```

Gefeliciteerd! U hebt nu geleerd hoe u inline codefunctionaliteit kunt gebruiken met Aspose.Words voor .NET.


### Veelgestelde vragen

#### Vraag: Hoe kan ik de inlinecode in Aspose.Words gebruiken?

 A: Om inlinecode in Aspose.Words te gebruiken, kunt u de juiste tags gebruiken om de tekst te omringen die moet worden opgemaakt als inlinecode. U kunt bijvoorbeeld gebruik maken van de`<code>` of`<kbd>` tag om tekst te omringen die moet worden opgemaakt als inlinecode.

#### Vraag: Is het mogelijk om het lettertype of de kleur van de inline code op te geven in Aspose.Words?

 A: Ja, u kunt het lettertype of de kleur van de inlinecode opgeven in Aspose.Words. U kunt gebruik maken van de`Font.Name`En`Font.Color` eigenschappen van de`Run` object om het lettertype en de kleur van inline code in te stellen. U kunt bijvoorbeeld gebruiken`run.Font.Name = "Courier New"` om het lettertype voor inline code op te geven en`run.Font.Color = Color.Blue`om de kleur op te geven.

#### Vraag: Kan ik de inlinecode gebruiken in een alinea die andere tekstelementen bevat?

 A: Ja, u kunt de inlinecode gebruiken in een alinea die andere tekstelementen bevat. Je kunt er meerdere maken`Run` objecten om verschillende delen van de alinea weer te geven, en gebruik vervolgens inline codetags om alleen de specifieke delen op te maken als inline code. Vervolgens kunt u ze aan de alinea toevoegen met behulp van de`Paragraph.AppendChild(run)` methode.