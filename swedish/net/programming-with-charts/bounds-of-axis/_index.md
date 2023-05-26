---
title: Axelgränser
linktitle: Axelgränser
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du ställer in gränserna för en axel i ett diagram med Aspose.Words för .NET som kontrollerar intervallet av värden som visas på axeln.
type: docs
weight: 10
url: /sv/net/programming-with-charts/bounds-of-axis/
---

Denna handledning förklarar hur man ställer in gränserna för en axel i ett diagram med Aspose.Words för .NET. Genom att infoga ett diagram, lägga till seriedata och konfigurera axelskalningen kan du definiera minimi- och maxvärden för axeln.

## Förutsättningar
För att följa denna handledning måste du ha följande:

- Aspose.Words för .NET-biblioteket installerat.
- Grundläggande kunskaper i C# och att arbeta med Word-dokument.

## Steg 1: Konfigurera dokumentkatalogen
 Börja med att ställa in sökvägen till din dokumentkatalog. Byta ut`"YOUR DOCUMENT DIRECTORY"`med den faktiska sökvägen till katalogen där du vill spara dokumentet.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Skapa ett nytt dokument och DocumentBuilder
 Skapa en ny instans av`Document` klass och a`DocumentBuilder` objekt för att arbeta med dokumentet.

```csharp
Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

## Steg 3: Infoga och konfigurera ett diagram
 Infoga ett diagram i dokumentet med hjälp av`InsertChart` metod för`DocumentBuilder` objekt. Ställ in önskad diagramtyp och dimensioner.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Steg 4: Lägg till seriedata
Rensa alla befintliga serier i diagrammet och lägg till nya seriedata. I det här exemplet lägger vi till en serie med etiketter "Artikel 1" till "Artikel 5" och motsvarande värden.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Steg 5: Ställ in gränserna för axeln
 Konfigurera skalningen av Y-axeln genom att ställa in lägsta och maximala värden med hjälp av`Scaling.Minimum` och`Scaling.Maximum` axelns egenskaper.

```csharp
chart.AxisY.Scaling.Minimum = new AxisBound(0);
chart.AxisY.Scaling.Maximum = new AxisBound(6);
```

## Steg 6: Spara dokumentet
 Spara dokumentet i den angivna katalogen med hjälp av`Save` metod. Ange önskat filnamn med lämplig filtillägg. I det här exemplet sparar vi dokumentet som "WorkingWithCharts.BoundsOfAxis.docx".

```csharp
doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

### Exempel på källkod för Bounds Of Axis med Aspose.Words för .NET 

```csharp
	// Sökväg till din dokumentkatalog
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	Document doc = new Document();
	DocumentBuilder builder = new DocumentBuilder(doc);
	Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
	Chart chart = shape.Chart;
	chart.Series.Clear();
	chart.Series.Add("Aspose Series 1",
		new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
		new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
	chart.AxisY.Scaling.Minimum = new AxisBound(0);
	chart.AxisY.Scaling.Maximum = new AxisBound(6);
	doc.Save(dataDir + "WorkingWithCharts.BoundsOfAxis.docx");
```

Det är allt! Du har framgångsrikt angett gränserna för en axel i ett diagram med Aspose.Words för .NET.