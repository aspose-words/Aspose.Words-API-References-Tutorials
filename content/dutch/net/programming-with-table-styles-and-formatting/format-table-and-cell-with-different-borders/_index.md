---
title: Formatteer tabel en cel met verschillende randen
linktitle: Formatteer tabel en cel met verschillende randen
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u tabellen en cellen met verschillende randen opmaakt met Aspose.Words voor .NET. Verbeter uw Word-documenten met aangepaste tabelstijlen en celarcering.
type: docs
weight: 10
url: /nl/net/programming-with-table-styles-and-formatting/format-table-and-cell-with-different-borders/
---
## Invoering

Heeft u ooit geprobeerd uw Word-documenten er professioneler uit te laten zien door de randen van tabellen en cellen aan te passen? Zo niet, dan staat je een traktatie te wachten! Deze tutorial begeleidt u bij het opmaken van tabellen en cellen met verschillende randen met behulp van Aspose.Words voor .NET. Stelt u zich eens voor dat u de mogelijkheid heeft om het uiterlijk van uw tabellen te veranderen met slechts een paar regels code. Gefascineerd? Laten we erin duiken en ontdekken hoe u dit gemakkelijk kunt bereiken.

## Vereisten

Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
- Basiskennis van programmeren in C#.
- Visual Studio is op uw computer geïnstalleerd.
-  Aspose.Words voor .NET-bibliotheek. Als je het nog niet hebt geïnstalleerd, kun je het downloaden[hier](https://releases.aspose.com/words/net/).
-  Een geldige Aspose-licentie. U kunt een gratis proefversie of een tijdelijke licentie krijgen van[hier](https://purchase.aspose.com/temporary-license/).

## Naamruimten importeren

Om met Aspose.Words voor .NET te werken, moet u de benodigde naamruimten in uw project importeren. Voeg het volgende toe met behulp van richtlijnen bovenaan uw codebestand:

```csharp
using Aspose.Words;
using Aspose.Words.Tables;
using System.Drawing;
```

## Stap 1: Initialiseer Document en DocumentBuilder

Eerst moet u een nieuw document maken en de DocumentBuilder initialiseren, die helpt bij het opbouwen van de documentinhoud. 

```csharp
// Pad naar uw documentmap
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 2: Begin met het maken van een tabel

Gebruik vervolgens de DocumentBuilder om een tabel te maken en de eerste cel in te voegen.

```csharp
Table table = builder.StartTable();
builder.InsertCell();
```

## Stap 3: stel de tabelranden in

Stel de randen in voor de hele tafel. Deze stap zorgt ervoor dat alle cellen in de tabel een consistente randstijl hebben, tenzij anders aangegeven.

```csharp
// Stel de randen in voor de hele tafel.
table.SetBorders(LineStyle.Single, 2.0, Color.Black);
```

## Stap 4: Pas celschaduw toe

Breng schaduw aan op de cellen om ze visueel verschillend te maken. In dit voorbeeld stellen we de achtergrondkleur van de eerste cel in op rood.


```csharp
// Stel de celarcering voor deze cel in.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Red;
builder.Writeln("Cell #1");
```

## Stap 5: Voeg nog een cel in met verschillende arcering

Plaats de tweede cel en pas een andere arceringskleur toe. Dit maakt de tabel kleurrijker en gemakkelijker leesbaar.

```csharp
builder.InsertCell();
// Geef een andere celarcering op voor de tweede cel.
builder.CellFormat.Shading.BackgroundPatternColor = Color.Green;
builder.Writeln("Cell #2");
builder.EndRow();
```

## Stap 6: Celopmaak wissen

Wis de celopmaak van eerdere bewerkingen om ervoor te zorgen dat de volgende cellen niet dezelfde stijlen overnemen.


```csharp
// Wis de celopmaak van eerdere bewerkingen.
builder.CellFormat.ClearFormatting();
```

## Stap 7: Pas randen aan voor specifieke cellen

Pas de randen van specifieke cellen aan, zodat ze opvallen. Hier stellen we grotere randen in voor de eerste cel van de nieuwe rij.

```csharp
builder.InsertCell();
// Maak grotere randen voor de eerste cel van deze rij. Dit zal anders zijn
// vergeleken met de randen die voor de tafel zijn ingesteld.
builder.CellFormat.Borders.Left.LineWidth = 4.0;
builder.CellFormat.Borders.Right.LineWidth = 4.0;
builder.CellFormat.Borders.Top.LineWidth = 4.0;
builder.CellFormat.Borders.Bottom.LineWidth = 4.0;
builder.Writeln("Cell #3");
```

## Stap 8: Plaats de laatste cel

Voeg de laatste cel in en zorg ervoor dat de opmaak ervan is gewist, zodat de standaardstijlen van de tabel worden gebruikt.

```csharp
builder.InsertCell();
builder.CellFormat.ClearFormatting();
builder.Writeln("Cell #4");
```

## Stap 9: Sla het document op

Sla het document ten slotte op in de opgegeven map.

```csharp
doc.Save(dataDir + "WorkingWithTableStylesAndFormatting.FormatTableAndCellWithDifferentBorders.docx");
```

## Conclusie

En daar heb je het! U hebt zojuist geleerd hoe u tabellen en cellen met verschillende randen kunt opmaken met Aspose.Words voor .NET. Door tabelranden en celarcering aan te passen, kunt u de visuele aantrekkingskracht van uw documenten aanzienlijk verbeteren. Experimenteer dus met verschillende stijlen en zorg ervoor dat uw documenten opvallen!

## Veelgestelde vragen

### Kan ik voor elke cel verschillende randstijlen gebruiken?
 Ja, u kunt voor elke cel verschillende randstijlen instellen met behulp van de`CellFormat.Borders` eigendom.

### Hoe kan ik alle randen van een tabel verwijderen?
 U kunt alle randen verwijderen door de randstijl in te stellen op`LineStyle.None`.

### Is het mogelijk om voor elke cel verschillende randkleuren in te stellen?
 Absoluut! U kunt de randkleur voor elke cel aanpassen met behulp van de`CellFormat.Borders.Color` eigendom.

### Kan ik afbeeldingen gebruiken als celachtergronden?
Hoewel Aspose.Words afbeeldingen niet rechtstreeks als celachtergrond ondersteunt, kunt u een afbeelding in een cel invoegen en de grootte ervan aanpassen om het celgebied te bedekken.

### Hoe voeg ik cellen in een tabel samen?
 Je kunt cellen samenvoegen met behulp van de`CellFormat.HorizontalMerge`En`CellFormat.VerticalMerge` eigenschappen.