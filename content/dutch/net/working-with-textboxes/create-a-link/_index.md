---
title: Maak een link in Word
linktitle: Maak een link in Word
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u een link in Word kunt maken tussen tekstvakken in een Word-document met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-textboxes/create-a-link/
---
In deze stapsgewijze handleiding wordt uitgelegd hoe u in Word een koppeling kunt maken tussen twee tekstvakken in een Word-document met behulp van de Aspose.Words-bibliotheek voor .NET. U leert hoe u het document configureert, de tekstvakvormen maakt, toegang krijgt tot de tekstvakken, de geldigheid van het linkdoel controleert en uiteindelijk de link zelf maakt.

## Stap 1: Het document instellen en TextBox-vormen maken

 Om te beginnen moeten we het document instellen en twee TextBox-vormen maken. De volgende code initialiseert een nieuw exemplaar van het`Document` class en maakt twee tekstvakvormen:

```csharp
Document doc = new Document();
Shape shape1 = new Shape(doc, ShapeType.TextBox);
Shape shape2 = new Shape(doc, ShapeType.TextBox);

TextBox textBox1 = shape1.TextBox;
TextBox textBox2 = shape2.TextBox;
```

## Stap 2: Een koppeling maken tussen tekstvakken

We zullen nu een link maken tussen de twee TextBoxen met behulp van de`IsValidLinkTarget()` methode en de`Next` eigenschap van het eerste TextBox.

```csharp
if (textBox1.IsValidLinkTarget(textBox2))
     textBox1. Next = textBox2;
```

 De`IsValidLinkTarget()` methode controleert of het tweede TextBox een geldig doel kan zijn voor de link van het eerste TextBox. Als de validatie slaagt, wordt de`Next` eigenschap van het eerste TextBox wordt ingesteld op het tweede TextBox, waardoor er een link tussen de twee ontstaat.

### Voorbeeldbroncode om te koppelen met Aspose.Words voor .NET

```csharp
Document doc = new Document();
Shape shape1 = new Shape(doc, ShapeType.TextBox);
Shape shape2 = new Shape(doc, ShapeType.TextBox);

TextBox textBox1 = shape1.TextBox;
TextBox textBox2 = shape2.TextBox;

if (textBox1.IsValidLinkTarget(textBox2))
     textBox1. Next = textBox2;
```
## Conclusie

Gefeliciteerd! U hebt nu geleerd hoe u een koppeling kunt maken tussen twee tekstvakken in een Word-document met behulp van de Aspose.Words-bibliotheek voor .NET. Met behulp van deze stapsgewijze handleiding kon u het document instellen, de tekstvakvormen maken, toegang krijgen tot de tekstvakken, de geldigheid van het linkdoel controleren en uiteindelijk de link zelf maken.

### Veelgestelde vragen over het maken van een link in Word

#### Vraag: Wat is de bibliotheek die wordt gebruikt om tekstvakken in Word te koppelen met Aspose.Words voor .NET?

A: Om tekstvakken in Word te koppelen met Aspose.Words voor .NET, is de gebruikte bibliotheek Aspose.Words voor .NET.

#### Vraag: Hoe controleer ik of het linkdoel geldig is voordat de link wordt gemaakt?

 A: Voordat u de koppeling tussen tekstvakken maakt, kunt u de`IsValidLinkTarget()` methode om te controleren of het linkdoel geldig is. Deze methode valideert of het tweede tekstvak een geldig doel kan zijn voor de link uit het eerste tekstvak.

#### Vraag: Hoe maak ik een link tussen twee tekstvakken?

 A: Om een link tussen twee tekstvakken te maken, moet u de`Next` eigenschap van het eerste tekstvak naar het tweede tekstvak. Zorg ervoor dat u vooraf de geldigheid van het linkdoel heeft gecontroleerd met behulp van de`IsValidLinkTarget()` methode.

#### Vraag: Is het mogelijk om koppelingen te maken tussen andere elementen dan tekstvakken?

A: Ja, met behulp van de Aspose.Words-bibliotheek voor .NET is het mogelijk om koppelingen te maken tussen verschillende elementen, zoals alinea's, tabellen, afbeeldingen, enz. Het proces zal variëren afhankelijk van het specifieke item dat u wilt koppelen.

#### Vraag: Welke andere functionaliteit kan worden toegevoegd aan tekstvakken in Word met Aspose.Words voor .NET?

A: Met Aspose.Words voor .NET kunt u vele andere functies aan tekstvakken toevoegen, zoals tekstopmaak, afbeeldingen toevoegen, stijlen wijzigen, enz. U kunt de Aspose.Words voor .NET-documentatie verkennen om alle functies te ontdekken. beschikbaar.