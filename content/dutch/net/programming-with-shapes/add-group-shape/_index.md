---
title: Groepsvorm toevoegen
linktitle: Groepsvorm toevoegen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u groepsvormen aan Word-documenten kunt toevoegen met Aspose.Words voor .NET met deze uitgebreide, stapsgewijze zelfstudie.
type: docs
weight: 10
url: /nl/net/programming-with-shapes/add-group-shape/
---
## Invoering

Het maken van complexe documenten met rijke visuele elementen kan soms een hele klus zijn, vooral als het om groepsvormen gaat. Maar vrees niet! Aspose.Words voor .NET vereenvoudigt dit proces, waardoor het heel eenvoudig wordt. In deze zelfstudie leiden we u door de stappen om groepsvormen aan uw Word-documenten toe te voegen. Klaar om erin te duiken? Laten we beginnen!

## Vereisten

Voordat we beginnen, zorg ervoor dat u over het volgende beschikt:

1.  Aspose.Words voor .NET: Je kunt het downloaden van de[Aspose-releasespagina](https://releases.aspose.com/words/net/).
2. Ontwikkelomgeving: Visual Studio of een andere IDE die compatibel is met .NET.
3. Basiskennis van C#: Bekendheid met programmeren in C# is een pluspunt.

## Naamruimten importeren

Om te beginnen moeten we de benodigde naamruimten in ons project importeren. Deze naamruimten bieden toegang tot de klassen en methoden die nodig zijn voor het manipuleren van Word-documenten met Aspose.Words.

```csharp
using System;
using Aspose.Words;
using Aspose.Words.Drawing;
```

## Stap 1: Initialiseer het document

Laten we eerst een nieuw Word-document initialiseren. Zie dit als het maken van een leeg canvas waar we onze groepsvormen aan toevoegen.

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.EnsureMinimum();
```

 Hier,`EnsureMinimum()` voegt een minimale set knooppunten toe die nodig zijn voor het document.

## Stap 2: Maak het GroupShape-object

 Vervolgens moeten we een`GroupShape`voorwerp. Dit object zal dienen als container voor andere vormen, waardoor we ze kunnen groeperen.

```csharp
GroupShape groupShape = new GroupShape(doc);
```

## Stap 3: Vormen toevoegen aan de GroupShape

 Laten we nu individuele vormen aan onze toevoegen`GroupShape` houder. We beginnen met een accentrandvorm en voegen vervolgens een actieknopvorm toe.

### Een accentrandvorm toevoegen

```csharp
Shape accentBorderShape = new Shape(doc, ShapeType.AccentBorderCallout1)
{
    Width = 100,
    Height = 100
};
groupShape.AppendChild(accentBorderShape);
```

 Dit codefragment creëert een accentrandvorm met een breedte en hoogte van 100 eenheden en voegt deze toe aan de`GroupShape`.

### Een actieknopvorm toevoegen

```csharp
Shape actionButtonShape = new Shape(doc, ShapeType.ActionButtonBeginning)
{
    Left = 100,
    Width = 100,
    Height = 200
};
groupShape.AppendChild(actionButtonShape);
```

 Hier maken we een vorm van een actieknop, plaatsen deze en voegen deze toe aan onze`GroupShape`.

## Stap 4: Definieer de GroupShape-afmetingen

 Om ervoor te zorgen dat onze vormen goed binnen de groep passen, moeten we de afmetingen van de`GroupShape`.

```csharp
groupShape.Width = 200;
groupShape.Height = 200;
groupShape.CoordSize = new Size(200, 200);
```

 Dit definieert de breedte en hoogte van de`GroupShape` als 200 eenheden en stelt de coördinatengrootte dienovereenkomstig in.

## Stap 5: Plaats de GroupShape in het document

 Laten we nu onze`GroupShape` in het document gebruiken`DocumentBuilder`.

```csharp
DocumentBuilder builder = new DocumentBuilder(doc);
builder.InsertNode(groupShape);
```

`DocumentBuilder` biedt een eenvoudige manier om knooppunten, inclusief vormen, aan het document toe te voegen.

## Stap 6: Sla het document op

Sla het document ten slotte op in de door u opgegeven map.

```csharp
doc.Save(dataDir + "WorkingWithShapes.AddGroupShape.docx");
```

En daar heb je het! Je document met groepsvormen is klaar.

## Conclusie

Het toevoegen van groepsvormen aan uw Word-documenten hoeft geen ingewikkeld proces te zijn. Met Aspose.Words voor .NET kunt u eenvoudig vormen maken en manipuleren, waardoor uw documenten visueel aantrekkelijker en functioneler worden. Volg de stappen in deze tutorial en je bent binnen de kortste keren een professional!

## Veelgestelde vragen

### Kan ik meer dan twee vormen aan een GroupShape toevoegen?
 Ja, u kunt zoveel vormen toevoegen als u nodig heeft`GroupShape` . Gebruik gewoon de`AppendChild` methode voor elke vorm.

### Is het mogelijk om de vormen binnen een GroupShape te stylen?
 Absoluut! Elke vorm kan individueel worden gestyled met behulp van de eigenschappen die beschikbaar zijn in de`Shape` klas.

### Hoe positioneer ik de GroupShape binnen het document?
 U kunt de`GroupShape` door het instellen van zijn`Left`En`Top` eigenschappen.

### Kan ik tekst toevoegen aan de vormen binnen de GroupShape?
 Ja, u kunt tekst aan vormen toevoegen met behulp van de`AppendChild` methode om een toe te voegen`Paragraph` bevattend`Run` knooppunten met tekst.

### Is het mogelijk om vormen dynamisch te groeperen op basis van gebruikersinvoer?
Ja, u kunt dynamisch vormen maken en groeperen op basis van gebruikersinvoer door de eigenschappen en methoden dienovereenkomstig aan te passen.