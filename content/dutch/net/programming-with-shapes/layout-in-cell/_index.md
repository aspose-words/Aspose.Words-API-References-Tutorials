---
title: Indeling in cel
linktitle: Indeling in cel
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u de lay-out in cellen instelt met Aspose.Words voor .NET met deze uitgebreide handleiding. Perfect voor ontwikkelaars die Word-documenten willen aanpassen.
type: docs
weight: 10
url: /nl/net/programming-with-shapes/layout-in-cell/
---
## Invoering

Als u ooit de lay-out van uw tabelcellen in Word-documenten programmatisch wilt verfijnen, bent u hier op de juiste plek. Vandaag gaan we dieper in op het instellen van de lay-out in cellen met Aspose.Words voor .NET. We lopen door een praktisch voorbeeld en splitsen het stap voor stap op, zodat u het gemakkelijk kunt volgen.

## Vereisten

Voordat we ingaan op de code, zorgen we ervoor dat je alles hebt wat je nodig hebt:

1.  Aspose.Words voor .NET: Zorg ervoor dat de Aspose.Words voor .NET-bibliotheek is geïnstalleerd. Als je dat nog niet hebt gedaan, kun je dat doen[download het hier](https://releases.aspose.com/words/net/).
2. Ontwikkelomgeving: Je hebt een ontwikkelomgeving nodig die is opgezet met .NET. Visual Studio is een goede keuze als u op zoek bent naar aanbevelingen.
3. Basiskennis van C#: Hoewel ik elke stap zal uitleggen, zal een basiskennis van C# je helpen gemakkelijker te volgen.
4.  Documentmap: bereid een mappad voor waar u uw documenten opslaat. We zullen dit noemen als`YOUR DOCUMENT DIRECTORY`.

## Naamruimten importeren

Zorg er om te beginnen voor dat u de benodigde naamruimten in uw project importeert:

```csharp
using System;
using System.Drawing;
using Aspose.Words;
using Aspose.Words.Drawing;
using Aspose.Words.Tables;
```

Laten we het proces opsplitsen in beheersbare stappen.

## Stap 1: Maak een nieuw document

 Eerst maken we een nieuw Word-document en initialiseren we een`DocumentBuilder` bezwaar maken om ons te helpen onze inhoud te construeren.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Stap 2: Start een tabel en stel de rijopmaak in

We beginnen met het construeren van een tabel en specificeren de hoogte- en hoogteregel voor de rijen.

```csharp
builder.StartTable();
builder.RowFormat.Height = 100;
builder.RowFormat.HeightRule = HeightRule.Exactly;
```

## Stap 3: cellen invoegen en inhoud vullen

Vervolgens maken we een lus om cellen in de tabel in te voegen. Voor elke zeven cellen beëindigen we de rij om een nieuwe te maken.

```csharp
for (int i = 0; i < 31; i++)
{
    if (i != 0 && i % 7 == 0) builder.EndRow();
    builder.InsertCell();
    builder.Write("Cell contents");
}
builder.EndTable();
```

## Stap 4: Voeg een watermerkvorm toe

 Laten we nu een watermerk aan ons document toevoegen. We maken een`Shape` object en stel de eigenschappen ervan in.

```csharp
Shape watermark = new Shape(doc, ShapeType.TextPlainText)
{
    RelativeHorizontalPosition = RelativeHorizontalPosition.Page,
    RelativeVerticalPosition = RelativeVerticalPosition.Page,
    IsLayoutInCell = true, // Geef de vorm buiten de tabelcel weer als deze in een cel wordt geplaatst.
    Width = 300,
    Height = 70,
    HorizontalAlignment = HorizontalAlignment.Center,
    VerticalAlignment = VerticalAlignment.Center,
    Rotation = -40
};
```

## Stap 5: Pas de weergave van het watermerk aan

We zullen het uiterlijk van het watermerk verder aanpassen door de kleur- en teksteigenschappen in te stellen.

```csharp
watermark.FillColor = Color.Gray;
watermark.StrokeColor = Color.Gray;
watermark.TextPath.Text = "watermarkText";
watermark.TextPath.FontFamily = "Arial";
watermark.Name = $"WaterMark_{Guid.NewGuid()}";
watermark.WrapType = WrapType.None;
```

## Stap 6: Voeg een watermerk in het document in

We zoeken de laatste run in het document en voegen het watermerk op die positie in.

```csharp
Run run = doc.GetChildNodes(NodeType.Run, true)[doc.GetChildNodes(NodeType.Run, true).Count - 1] as Run;
builder.MoveTo(run);
builder.InsertNode(watermark);
```

## Stap 7: Document optimaliseren voor Word 2010

Om compatibiliteit te garanderen, optimaliseren we het document voor Word 2010.

```csharp
doc.CompatibilityOptions.OptimizeFor(MsWordVersion.Word2010);
```

## Stap 8: Bewaar het document

Ten slotte slaan we ons document op in de opgegeven map.

```csharp
doc.Save(dataDir + "WorkingWithShapes.LayoutInCell.docx");
```

## Conclusie

En daar heb je het! U hebt met succes een Word-document gemaakt met een aangepaste tabelindeling en een watermerk toegevoegd met Aspose.Words voor .NET. Deze tutorial was bedoeld om u een duidelijke, stapsgewijze handleiding te bieden waarmee u elk onderdeel van het proces kunt begrijpen. Met deze vaardigheden kunt u nu programmatisch geavanceerdere en aangepaste Word-documenten maken.

## Veelgestelde vragen

### Kan ik een ander lettertype gebruiken voor de watermerktekst?
 Ja, u kunt het lettertype wijzigen door de`watermark.TextPath.FontFamily` eigenschap naar het gewenste lettertype.

### Hoe pas ik de positie van het watermerk aan?
 U kunt de`RelativeHorizontalPosition`, `RelativeVerticalPosition`, `HorizontalAlignment` , En`VerticalAlignment` eigenschappen om de positie van het watermerk aan te passen.

### Is het mogelijk om een afbeelding in plaats van tekst voor het watermerk te gebruiken?
 Absoluut! U kunt een`Shape` met de soort`ShapeType.Image` en stel de afbeelding in met behulp van de`ImageData.SetImage` methode.

### Kan ik tabellen maken met verschillende rijhoogtes?
Ja, u kunt voor elke rij verschillende hoogtes instellen door de`RowFormat.Height` eigenschap voordat u cellen in die rij invoegt.

### Hoe verwijder ik een watermerk uit het document?
 U kunt het watermerk verwijderen door het in de vormenverzameling van het document te zoeken en het bestand`Remove` methode.