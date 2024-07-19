---
title: Cursieve tekst
linktitle: Cursieve tekst
second_title: Aspose.Words-API voor documentverwerking
description: Leer hoe u tekst cursief maakt met Aspose.Words voor .NET Stapsgewijze handleiding.
type: docs
weight: 10
url: /nl/net/working-with-markdown/italic-text/
---

In dit voorbeeld laten we u zien hoe u de cursieve tekstfunctie gebruikt met Aspose.Words voor .NET. Cursieve tekst wordt gebruikt om bepaalde delen van een document te benadrukken.

## Stap 1: Een documentgenerator gebruiken

Eerst gebruiken we een documentgenerator om inhoud aan ons document toe te voegen.

```csharp
DocumentBuilder builder = new DocumentBuilder();
```

## Stap 2: Tekst cursief maken

 We kunnen tekst cursief maken door het lettertype in te stellen`Italic`eigendom aan`true`.

```csharp
builder.Font.Italic = true;
builder.Writeln("This text will be in italics");
```

### Voorbeeldbroncode voor cursieve tekst met Aspose.Words voor .NET


```csharp
// Gebruik een documentbuilder om inhoud aan het document toe te voegen.
DocumentBuilder builder = new DocumentBuilder();

// Maak de tekst cursief.
builder.Font.Italic = true;
builder.Writeln("This text will be Italic");
```

Gefeliciteerd! U hebt nu geleerd hoe u de cursieve tekstfunctie kunt gebruiken met Aspose.Words voor .NET.


### Veelgestelde vragen

#### Vraag: Hoe kan ik tekst cursief maken in Aspose.Words?

 A: Om tekst in Aspose.Words cursief te maken, kunt u de`Font.Italic` eigendom van de`Run`voorwerp. U kunt deze eigenschap instellen op`true` om specifieke tekst cursief te maken. U kunt bijvoorbeeld gebruiken`run.Font.Italic=true` om de tekst in de tekst cursief te maken`Run` voorwerp.

#### Vraag: Is het mogelijk om meerdere stukken tekst in dezelfde alinea cursief te maken?

 A: Ja, u kunt meerdere stukken tekst in één alinea cursief maken met behulp van meerdere`Run` voorwerpen. Je kunt er meerdere maken`Run` objecten en stel de in`Font.Italic`eigendom aan`true`voor elk object om de gewenste delen van de tekst cursief te maken. Vervolgens kunt u ze aan de alinea toevoegen met behulp van de`Paragraph.AppendChild(run)` methode.

#### Vraag: Kan ik tekst in een tabel of cel in Aspose.Words cursief maken?

 A: Ja, u kunt tekst in een tabel of cel in Aspose.Words cursief maken. U kunt met de juiste methoden naar de gewenste cel of alinea navigeren en vervolgens cursieve opmaak toepassen met behulp van de`Font.Italic` eigendom van de`Run` of`Paragraph` voorwerp.