---
title: Axelgränser I Ett Diagram
linktitle: Axelgränser I Ett Diagram
second_title: Aspose.Words Document Processing API
description: Lär dig hur du ställer in gränserna för en axel i ett diagram med Aspose.Words för .NET som kontrollerar intervallet av värden som visas på axeln.
type: docs
weight: 10
url: /sv/net/programming-with-charts/bounds-of-axis/
---

Denna handledning förklarar hur man ställer in gränserna för en axel i ett diagram med Aspose.Words för .NET. Genom att infoga ett diagram, lägga till seriedata och konfigurera axelskalningen kan du definiera minimi- och maxvärden för axeln.

## Förutsättningar
För att följa denna handledning måste du ha följande:

- Aspose.Words för .NET-biblioteket installerat.
- Grundläggande kunskaper i C# och ordbehandling med Word-dokument.

## Steg 1: Konfigurera dokumentkatalogen
 Börja med att ställa in sökvägen till din dokumentkatalog. Byta ut`"YOUR DOCUMENT DIRECTORY"` med den faktiska sökvägen till katalogen där du vill spara dokumentet.

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
	//Sökväg till din dokumentkatalog
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

## Slutsats
den här handledningen har du lärt dig hur du ställer in gränserna för en axel i ett diagram med Aspose.Words för .NET. Genom att följa steg-för-steg-guiden kan du infoga och konfigurera ett diagram, lägga till seriedata och definiera minimi- och maxvärden för axelskalningen. Aspose.Words för .NET tillhandahåller ett kraftfullt och flexibelt API för ordbehandling med Word-dokument, så att du enkelt kan skapa dynamiska och visuellt tilltalande diagram.


### Vanliga frågor

#### Q1. Vad är Aspose.Words för .NET?
Aspose.Words för .NET är ett bibliotek som låter utvecklare arbeta med Word-dokument programmatiskt. Den tillhandahåller ett brett utbud av funktioner och funktioner för att skapa, manipulera och spara Word-dokument.

#### Q2. Hur kan jag installera Aspose.Words för .NET?
För att installera Aspose.Words för .NET kan du använda NuGet-pakethanteraren i Visual Studio. Sök helt enkelt efter "Aspose.Words" i NuGet-pakethanteraren och installera det i ditt projekt.

#### Q3. Kan jag använda Aspose.Words för .NET med andra programmeringsspråk?
Nej, Aspose.Words för .NET är speciellt designat för .NET-applikationer. Det fungerar med programmeringsspråk som C# och VB.NET.

#### Q4. Finns det några andra förutsättningar för att använda Aspose.Words för .NET?
Förutom att installera Aspose.Words för .NET-biblioteket bör du ha grundläggande kunskaper i C#-programmering och ordbehandling med Word-dokument. Bekantskap med .NET-ramverket kommer också att vara till hjälp.
