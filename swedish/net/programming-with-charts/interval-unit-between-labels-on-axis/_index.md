---
title: Intervallenhet mellan etiketter på axeln
linktitle: Intervallenhet mellan etiketter på axeln
second_title: Aspose.Words för .NET API Referens
description: Lär dig hur du ställer in intervallenheten mellan etiketter på axeln i ett diagram med Aspose.Words för .NET.
type: docs
weight: 10
url: /sv/net/programming-with-charts/interval-unit-between-labels-on-axis/
---

Denna handledning förklarar hur man använder Aspose.Words för .NET för att ställa in intervallenheten mellan etiketterna på axeln i ett diagram. Den medföljande källkoden visar hur man skapar ett diagram, lägger till seriedata och anpassar axeletiketterna.

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

 Använd sedan`InsertChart` metod för`DocumentBuilder` för att infoga ett kolumndiagram i dokumentet.

```csharp
Shape shape = builder.InsertChart(ChartType.Column, 432, 252);
Chart chart = shape.Chart;
```

## Steg 3: Lägg till seriedata i diagrammet

Lägg till seriedata i diagrammet. I det här exemplet lägger vi till fem objekt med motsvarande värden.

```csharp
chart.Series.Clear();
chart.Series.Add("Aspose Series 1",
    new string[] { "Item 1", "Item 2", "Item 3", "Item 4", "Item 5" },
    new double[] { 1.2, 0.3, 2.1, 2.9, 4.2 });
```

## Steg 4: Anpassa axeletiketterna

 För att ställa in intervallenheten mellan etiketter på X-axeln, gå till`AxisX` egenskapen för diagrammet och ställ in`TickLabelSpacing` egendom till önskat värde. I det här exemplet ställer vi in avståndet till 2.

```csharp
chart.AxisX.TickLabelSpacing = 2;
```

## Steg 5: Spara dokumentet

 Slutligen sparar du dokumentet i den angivna katalogen med hjälp av`Save` metod för`Document` objekt.

```csharp
doc.Save(dataDir + "WorkingWithCharts.IntervalUnitBetweenLabelsOnAxis.docx");
```

Detta slutför implementeringen av att ställa in intervallenheten mellan etiketter på axeln med Aspose.Words för .NET.

### Exempel på källkod för Interval Unit Between Labels On Axis med Aspose.Words för .NET 

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
	chart.AxisX.TickLabelSpacing = 2;
	doc.Save(dataDir + "WorkingWithCharts.IntervalUnitBetweenLabelsOnAxis.docx");
```