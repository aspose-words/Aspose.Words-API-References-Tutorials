---
title: Dölj diagramaxel
linktitle: Dölj diagramaxel
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du döljer diagramaxeln i ett dokument med Aspose.Words för .NET. Dölj axeln för en renare och mer fokuserad sjökortsvisning.
type: docs
weight: 10
url: /sv/net/programming-with-charts/hide-chart-axis/
---

Denna handledning förklarar hur man använder Aspose.Words för .NET för att dölja diagramaxeln i ett dokument. Den medföljande källkoden visar hur man skapar ett diagram, lägger till seriedata och döljer diagramaxeln.

## Steg 1: Konfigurera projektet

Se till att du har följande förutsättningar:

- Aspose.Words för .NET-biblioteket installerat. Du kan ladda ner den från den officiella Aspose-webbplatsen eller använda NuGet-pakethanteraren för att installera den.
- En sökväg till dokumentkatalogen där utdatadokumentet kommer att sparas.

## Steg 2: Skapa ett nytt dokument och infoga ett diagram

 Skapa en ny`Document` föremål och ett`DocumentBuilder` att bygga dokumentet.

```csharp
// Sökväg till din dokumentkatalog
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
DocumentBuilder builder = new DocumentBuilder(doc);
```

 Infoga sedan ett diagram i dokumentet med hjälp av`InsertChart` metod för`DocumentBuilder`. I det här exemplet infogar vi ett kolumndiagram.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Steg 3: Lägg till seriedata i diagrammet

Lägg till seriedata i diagrammet. I det här exemplet lägger vi till fem objekt och deras motsvarande värden.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Steg 4: Dölj diagramaxeln

 För att dölja sjökortsaxeln, gå till`AxisY` egenskapen för diagrammet och ställ in`Hidden` egendom till`true`.

```csharp
chart.AxisY.Hidden = true;
```

I det här exemplet döljer vi diagrammets Y-axel.

## Steg 5: Spara dokumentet

 Slutligen sparar du dokumentet i den angivna katalogen med hjälp av`Save` metod för`Document` objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```

Detta slutför implementeringen av att dölja diagramaxeln med Aspose.Words för .NET.

### Exempel på källkod för Hide Chart Axis med Aspose.Words för .NET 

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
	chart.AxisY.Hidden = true;
	doc.Save(dataDir + "WorkingWithCharts.HideChartAxis.docx");
```