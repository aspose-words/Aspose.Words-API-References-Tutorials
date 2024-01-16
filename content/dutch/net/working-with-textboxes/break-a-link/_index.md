---
title: Voorwaartse link in Word-document doorbreken
linktitle: Voorwaartse link in Word-document doorbreken
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u voorwaartse koppelingen in een Word-document kunt verbreken met Aspose.Words voor .NET.
type: docs
weight: 10
url: /nl/net/working-with-textboxes/break-a-link/
---

Aspose.Words voor .NET is een krachtige bibliotheek die verschillende functies biedt voor woordverwerking met Microsoft Word-documenten programmatisch. Een van de handige functies is de mogelijkheid om links in een Word-document door te sturen. In deze zelfstudie verkennen we de broncode in C#, waarin wordt gedemonstreerd hoe u een voorwaartse link in een Word-document kunt doorbreken met behulp van Aspose.Words voor .NET.

## Stap 1: Voorbeeld van C#-broncode

De meegeleverde C#-broncode richt zich op de "Break A Link"-functie van Aspose.Words voor .NET. Het laat zien hoe u een koppeling in een TextBox-vorm in een document kunt verbreken. De code presenteert verschillende scenario's voor het verbreken van koppelingen en geeft duidelijke instructies over hoe u de gewenste resultaten kunt bereiken.

## Stap 2: Het document instellen en een TextBox-vorm maken

 Om te beginnen moeten we het document instellen en een TextBox-vorm maken. De volgende code initialiseert een nieuw exemplaar van het`Document` class en maakt een tekstvakvorm:

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;
```

## Stap 3: Verbreek de voorwaartse link in TextBox

 Om een voorwaartse link in de TextBox te verbreken, kunnen we de`BreakForwardLink()` methode. Deze methode verbreekt de link naar de volgende vorm in de reeks. De volgende code laat zien hoe u een voorwaartse link verbreekt:

```csharp
textBox.BreakForwardLink();
```

## Stap 4: Verbreek een voorwaartse link door een nulwaarde in te stellen

 Als alternatief kunnen we een voorwaartse link verbreken door de TextBox's in te stellen`Next`eigendom aan`null`. Hierdoor wordt de verbinding met de volgende vorm effectief verwijderd. De volgende code demonstreert deze aanpak:

```csharp
textBox. Next = null;
```

## Stap 5: Verbreek een link die naar de TextBox leidt

 In sommige gevallen moeten we een link verbreken die naar de TextBox-vorm leidt. Dit kunnen wij bereiken door te bellen naar de`BreakForwardLink()` methode op de`Previous` formulier, dat de link naar de TextBox verbreekt. Hier is een voorbeeld van hoe je zo’n link kunt verbreken:

```csharp
textBox.Previous?.BreakForwardLink();
```

### Voorbeeldbroncode voor het verbreken van een koppeling met Aspose.Words voor .NET

```csharp
Document doc = new Document();
Shape shape = new Shape(doc, ShapeType.TextBox);
TextBox textBox = shape.TextBox;

// Voorwaartse link verbreken.
textBox.BreakForwardLink();

// Verbreek een voorwaartse link door een nulwaarde in te stellen.
textBox. Next = null;

// Verbreek een link die naar dit tekstvak leidt.
textBox.Previous?.BreakForwardLink();
```

## Conclusie

Gefeliciteerd! U hebt nu geleerd hoe u omleidingskoppelingen in een Word-document kunt verbreken met behulp van de Aspose.Words-bibliotheek voor .NET. Door de stappen in deze handleiding te volgen, kon u het document instellen, een TextBox-vorm maken en de omleidingslinks op verschillende manieren verbreken.

### Veelgestelde vragen over de break forward-link in een Word-document

#### Vraag: Welke bibliotheek wordt gebruikt om omleidingskoppelingen in een Word-document te verbreken met behulp van Aspose.Words voor .NET?

A: Om omleidingskoppelingen in een Word-document te verbreken met behulp van Aspose.Words voor .NET, is de gebruikte bibliotheek Aspose.Words voor .NET.

#### Vraag: Hoe kan ik een omleidingslink in een TextBox verbreken?

 A: Om een voorwaartse link in een TextBox te verbreken, kunt u de`BreakForwardLink()` methode. Deze methode verbreekt de link naar de volgende vorm in de reeks.

#### Vraag: Hoe kan ik een omleidingslink verbreken door een nulwaarde in te stellen?

A: Als alternatief kunt u een omleidingslink verbreken door de`Next` eigenschap van de TextBox to`null`. Hierdoor wordt de verbinding met de volgende vorm effectief verwijderd.

#### Vraag: Hoe verbreek ik een link die naar de TextBox leidt?

 A: In sommige gevallen moet u een link verbreken die naar de TextBox leidt. Dit kunt u bereiken door te bellen met de`BreakForwardLink()` methode op de`Previous` formulier, dat de link naar de TextBox verbreekt.

#### Vraag: Kunnen we omleidingslinks op andere elementen dan TextBoxen verbreken?

A: Ja, met Aspose.Words voor .NET is het mogelijk om omleidingslinks te verbreken voor verschillende elementen, zoals alinea's, tabellen, afbeeldingen, enz. Het proces kan variëren, afhankelijk van het specifieke item waarvoor u de link wilt verbreken.